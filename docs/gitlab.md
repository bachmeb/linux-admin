# gitlab

## References
* https://github.com/gitlabhq/gitlab-recipes/blob/master/install/centos/README.md

*This doc is a copy and edit of the install doc provided in the gitlabhq project called gitlab-recipies*

```
Distribution      : CentOS 6.8 Minimal
GitLab version    : 8.9
Web Server        : Apache, Nginx
Init system       : sysvinit
Database          : MySQL, PostgreSQL
Contributors      : @nielsbasjes, @axilleas, @mairin, @ponsjuh, @yorn, @psftw, @etcet, @mdirkse, @nszceta, @herkalurk, @mjmaenpaa
Additional Notes  : In order to get a proper Ruby & Git setup we build them from source
```

## Overview

Please read [requirements.md](https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/install/requirements.md) for hardware and platform requirements.

#### Security

Many setup guides of Linux software simply state: "disable selinux and firewall".
This guide does not disable any of them, we simply configure them as they were intended.
[Stop disabling SELinux](http://stopdisablingselinux.com/).

- - -

The GitLab installation consists of setting up the following components:

1. Install the base operating system (CentOS 6.8 Minimal) and Packages / Dependencies
1. Ruby
1. Go
1. System Users
1. Database
1. Redis
1. GitLab
1. Web server
1. Firewall

----------

## 1. Installing the operating system (CentOS 6.8 Minimal)
* https://github.com/bachmeb/linux-admin/blob/master/docs/centos/6.7/x86_64/install.md

## Updating and adding basic software and services

### Add EPEL repository
##### Download the GPG key for EPEL repository from [fedoraproject][keys] and install it on your system:
```
wget -O /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-6 https://getfedora.org/static/0608B895.txt
rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-6
```

##### Verify that the key got installed successfully:
```
rpm -qa gpg*
gpg-pubkey-0608b895-4bd22942
```

##### Install the `epel-release-6-8.noarch` package, which will enable EPEL repository on your system:
```
rpm -Uvh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
```
**Note:** Don't mind the `x86_64`, if you install on a i686 system you can use the same commands.

### Add Remi's RPM repository
##### Download the GPG key for Remi's repository and install it on your system:
```
wget -O /etc/pki/rpm-gpg/RPM-GPG-KEY-remi http://rpms.famillecollet.com/RPM-GPG-KEY-remi
rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-remi
```

##### Verify that the key got installed successfully:
```
rpm -qa gpg*
gpg-pubkey-00f97f56-467e318a
```

##### Install the `remi-release-6` package, which will enable remi-safe repository on your system:
```
rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
```

##### Verify that the EPEL and remi-safe repositories are enabled as shown below:
```
yum repolist
```
```
repo id        repo name                                                       status
base           CentOS-6 - Base                                                  6696
epel           Extra Packages for Enterprise Linux 6 - x86_64                  12125
extras         CentOS-6 - Extras                                                  61
remi-safe      Safe Remi's RPM repository for Enterprise Linux 6 - x86_64        827
updates        CentOS-6 - Updates                                                137
repolist: 19846
```

##### If you can't see them listed, use the folowing command (from `yum-utils` package) to enable them:
```
yum-config-manager --enable epel --enable remi-safe
```

### Install the required tools for GitLab
```
sudo yum update
```
```
sudo yum groupinstall 'Development Tools'
```
```
sudo yum install readline readline-devel ncurses-devel gdbm-devel glibc-devel tcl-devel openssl-devel curl-devel expat-devel db4-devel byacc sqlite-devel libyaml libyaml-devel libffi libffi-devel libxml2 libxml2-devel libxslt libxslt-devel libicu libicu-devel system-config-firewall-tui redis sudo wget crontabs logwatch logrotate perl-Time-HiRes git cmake libcom_err-devel.i686 libcom_err-devel.x86_64 nodejs
```

##### For reStructuredText markup language support, install required package:
```
sudo yum install python-docutils
```

**RHEL Notes**

If some packages (eg. gdbm-devel, libffi-devel and libicu-devel) are NOT installed,
add the rhel6 optional packages repo to your server to get those packages:
```
sudo yum-config-manager --enable rhel-6-server-optional-rpms
```

Tip taken from [here](https://github.com/gitlabhq/gitlab-recipes/issues/62).

### Install mail server

In order to receive mail notifications, make sure to install a
mail server. The recommended one is postfix and you can install it with:
```
sudo yum install postfix
```

* To use and configure sendmail instead of postfix see [Advanced Email Configurations](https://github.com/gitlabhq/gitlab-recipes/blob/master/e-mail/configure_email.md).

### Configure the default editor

During this installation some files will need to be edited manually.
You can choose between editors such as nano, vi, vim, etc.

In this case we will use vim as the default editor for consistency.
If you are familiar with vim set it as default editor with the commands below.
```
sudo yum install vim-enhanced
sudo ln -s /usr/bin/vim /usr/bin/editor
```

##### To remove this alias in the future:
```
rm -i /usr/bin/editor
```

### Install Git from Source

##### Make sure Git is version 2.7.4 or higher
```
git --version
```

##### If not, install it from source. First remove the system Git:
```
sudo yum remove git
```

Install the pre-requisite files for Git compilation:
```
sudo yum install zlib-devel perl-CPAN gettext curl-devel expat-devel gettext-devel openssl-devel
```

##### Download and extract it:
```
mkdir /tmp/git && cd /tmp/git
curl --progress https://www.kernel.org/pub/software/scm/git/git-2.9.0.tar.gz | tar xz
cd git-2.9.0
sudo ./configure
sudo make
sudo make prefix=/usr/local install
```
Make sure Git is in your `$PATH`:
```
which git
```
##### You might have to logout and login again for the `$PATH` to take effect.
```
exit
```

**Note:** When editing `config/gitlab.yml` (step 7), change the git `bin_path` to `/usr/local/bin/git`.

----------

## 2. Ruby

The use of ruby version managers such as [RVM](http://rvm.io/), [rbenv](https://github.com/sstephenson/rbenv) or [chruby](https://github.com/postmodern/chruby) with GitLab in production frequently leads to hard to diagnose problems. Version managers are not supported and we strongly advise everyone to follow the instructions below to use a system ruby.

Remove the old Ruby 1.8 package if present. GitLab only supports the Ruby 2.1 release series:
```
sudo yum list installed | grep ruby
ruby
yum remove ruby
```

##### Remove any other Ruby build if it is still present:
```
cd <your-ruby-source-path>
make uninstall
```

Download Ruby and compile it:
```
mkdir /tmp/ruby && cd /tmp/ruby
curl --progress https://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.9.tar.gz | tar xz
cd ruby-2.1.9
sudo ./configure --disable-install-rdoc
sudo make
sudo make prefix=/usr/local install
```

Install the Bundler Gem:
```
sudo /usr/local/bin/gem install bundler --no-doc
```

Logout and login again for the `$PATH` to take effect. Check that ruby is properly
installed with:
```
exit
which ruby
```
```
/usr/local/bin/ruby
```
```
ruby -v
```
```
# ruby 2.1.10p492 (2016-04-01 revision 54464) [x86_64-linux]
```


----------

## 3. Go

Since GitLab 8.0, Git HTTP requests are handled by gitlab-workhorse (formerly gitlab-git-http-server). This is a small daemon written in Go. To install gitlab-workhorse we need a Go compiler.
```
sudo yum install golang golang-bin golang-src
```

----------

## 4. System Users

Create a `git` user for Gitlab:
```
sudo adduser --system --shell /bin/bash --comment 'GitLab' --create-home --home-dir /home/git/ git
```

**Important:** In order to include `/usr/local/bin` to git user's PATH, one way is to edit the sudoers file. As root run:
```
sudo visudo
```

##### Then search for this line:
```
Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin
```

##### and append `/usr/local/bin` like so:
```
Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin:/usr/local/bin
```
##### Save and exit.

----------

## 5. Database

### 5.1 PostgreSQL (recommended)

NOTE: because we need to make use of extensions we need at least pgsql 9.1 and the default 8.x on centos will not work.  We need to get the PGDG repositories enabled

If there are any previous versions remove them:
```
yum list installed | grep postgresql
```
```
yum remove postgresql
```
Install the pgdg repositories:
```
sudo rpm -Uvh http://yum.postgresql.org/9.3/redhat/rhel-6-x86_64/pgdg-centos93-9.3-2.noarch.rpm
```

##### Install `postgresql93-server`, `postgreqsql93-devel` and the `postgresql93-contrib` libraries:
```
sudo yum install postgresql93-server 
sudo yum install postgresql93-devel 
sudo yum install postgresql93-contrib
sudo yum install postgresql93-libs
sudo yum install postgresql93-debuginfo
```

##### Rename the service script:
```
ls -la /etc/init.d/postg*
sudo mv /etc/init.d/{postgresql-9.3,postgresql}
ls -la /etc/init.d/postg*
```

Initialize the database:
```
sudo ls /var/lib/pgsql/9.3/data 
sudo /sbin/service postgresql initdb
sudo ls /var/lib/pgsql/9.3/data 
```

Start the service and configure service to start on boot:
```
sudo /sbin/service postgresql start
chkconfig
sudo chkconfig postgresql on
chkconfig
```
##### Switch to the postgres user
```
sudo su - postgres
```

##### Connect to the postgres db using the default template db
```
psql -d template1
```
```
# psql (9.4.3)
# Type "help" for help.
```
##### Create a user called git
```
template1=# CREATE USER git CREATEDB;
```
```
# CREATE ROLE
```
##### Create the gitlab db and make git the owner
```
template1=# CREATE DATABASE gitlabhq_production OWNER git;
```
```
CREATE DATABASE
```
##### Create the pg-trgm extension
```
template1=# CREATE EXTENSION IF NOT EXISTS pg_trgm;
```
```
# CREATE EXTENSION
```

##### Check if the `pg_trgm` extension is enabled:
```
SELECT true AS enabled
FROM pg_available_extensions
WHERE name = 'pg_trgm'
AND installed_version IS NOT NULL;
```

##### Quit postgresql
```
template1=# \q
```

##### exit uid=postgres, return to your linux user account
```
exit
whoami
```

##### Attempt to log in to Postgres as the git linux user:
```
sudo su -l git
psql -d gitlabhq_production
```

##### If you see the following, your password has been accepted successfully
```
gitlabhq_production=>
```

##### Check if the `pg_trgm` extension is enabled:
```
SELECT true AS enabled
FROM pg_available_extensions
WHERE name = 'pg_trgm'
AND installed_version IS NOT NULL;
```

If the extension is enabled this will produce the following output:
```
enabled
---------
 t
 (1 row)
```
##### If the extension is not enabled, quit postgres, switch to the postgres linux account, connect to the gitlabhq_production database, and enable the extension
```
\q
exit
sudo su -l postgres
psql -d gitlabhq_production
CREATE EXTENSION IF NOT EXISTS pg_trgm;
```
##### Then quit postgres, exit the postgres linux account, switch to the git linux account, connect to the gitlabhq_production database and see again if the extension is enabled

Ensure you are using the right settings in your `/var/lib/pgsql/9.3/data/pg_hba.conf`
to not get ident issues (you can use trust over ident):
```
host    all             all             127.0.0.1/32            trust
```

Check the official [documentation][psql-doc-auth] for more information on
authentication methods.

----------

## 6. Redis

GitLab requires at least Redis 2.8.

Remove old version:
```
sudo yum list installed | grep redis
sudo yum remove redis
```

Install new version from Remi's RPM repository:
```
sudo yum search redis
sudo yum --enablerepo=remi,remi-test install redis
```

Make sure redis is started on boot:
```
chkconfig
sudo chkconfig redis on
chkconfig | grep redis
```

Configure redis to use sockets:
```
cp /etc/redis.conf /etc/redis.conf.orig
```

Disable Redis listening on TCP by setting 'port' to 0:
```
less /etc/redis.conf.orig
/
port
q
sed 's/^port .*/port 0/' /etc/redis.conf.orig | sudo tee /etc/redis.conf
```

Enable Redis socket for default CentOS path:
```
cat /etc/redis.conf
echo 'unixsocket /var/run/redis/redis.sock' | sudo tee -a /etc/redis.conf
echo -e 'unixsocketperm 0770' | sudo tee -a /etc/redis.conf
```

Create the directory which contains the socket
```
sudo mkdir /var/run/redis
ls -la /var/run/redis
sudo chown redis:redis /var/run/redis
sudo chmod 755 /var/run/redis
ls -la /var/run/redis
```

Persist the directory which contains the socket, if applicable

```
if [ -d /etc/tmpfiles.d ]; then
 echo 'd  /var/run/redis  0755  redis  redis  10d  -' | sudo tee -a /etc/tmpfiles.d/redis.conf
fi
```

Activate the changes to redis.conf:
```
sudo /sbin/service redis restart
```
```
# Stopping redis-server: Could not connect to Redis at 127.0.0.1:0: Connection refused
# Could not connect to Redis at 127.0.0.1:0: Connection refused
#                                                            [  OK  ]
#Starting redis-server:                                     [  OK  ]
```

Add git to the redis group:
```
sudo usermod -aG redis git
```

------

## 7. GitLab
##### We'll install GitLab into home directory of the user "git"
```
sudo su -l git
whoami
cd ~
```

### Clone the Source
##### Clone GitLab repository
```
git clone https://gitlab.com/gitlab-org/gitlab-ce.git -b 8-9-stable gitlab
```

**Note:** You can change `8-9-stable` to `master` if you want the *bleeding edge* version, but do so with caution!

### Configure it

##### Go to GitLab installation folder
```
cd /home/git/gitlab
```

#### Copy the example GitLab config
```
cp config/gitlab.yml.example config/gitlab.yml
```

##### Update GitLab config file, follow the directions at top of file
```
editor config/gitlab.yml
```
```yml
# # # # # # # # # # # # # # # # # #
# GitLab application config file  #
# # # # # # # # # # # # # # # # # #
#
###########################  NOTE  #####################################
# This file should not receive new settings. All configuration options #
# * are being moved to ApplicationSetting model!                       #
# If a setting requires an application restart say so in that screen.  #
# If you change this file in a Merge Request, please also create       #
# a MR on https://gitlab.com/gitlab-org/omnibus-gitlab/merge_requests  #
########################################################################
#
#
# How to use:
# 1. Copy file as gitlab.yml
# 2. Update gitlab -> host with your fully qualified domain name
# 3. Update gitlab -> email_from
# 4. If you installed Git from source, change git -> bin_path to /usr/local/bin/git
#    IMPORTANT: If Git was installed in a different location use that instead.
#    You can check with `which git`. If a wrong path of Git is specified, it will
#     result in various issues such as failures of GitLab CI builds.
# 5. Review this configuration file for other settings you may want to adjust

production: &base
  #
  # 1. GitLab app settings
  # ==========================

  ## GitLab settings
  gitlab:
    ## Web server settings (note: host is the FQDN, do not include http://)
    host: localhost
    port: 80 # Set to 443 if using HTTPS, see installation.md#using-https for additional HTTPS configuration details
    https: false # Set to true if using HTTPS, see installation.md#using-https for additional HTTPS configuration details

    # Uncommment this line below if your ssh host is different from HTTP/HTTPS one
    # (you'd obviously need to replace ssh.host_example.com with your own host).
    # Otherwise, ssh host will be set to the `host:` value above
    # ssh_host: ssh.host_example.com

    # Relative URL support
    # WARNING: We recommend using an FQDN to host GitLab in a root path instead
    # of using a relative URL.
    # Documentation: http://doc.gitlab.com/ce/install/relative_url.html
    # Uncomment and customize the following line to run in a non-root path
    #
    # relative_url_root: /gitlab

    # Trusted Proxies
    # Customize if you have GitLab behind a reverse proxy which is running on a different machine.
    # Add the IP address for your reverse proxy to the list, otherwise users will appear signed in from that address.
    trusted_proxies:
      # Examples:
      #- 192.168.1.0/24
      #- 192.168.2.1
      #- 2001:0db8::/32

    # Uncomment and customize if you can't use the default user to run GitLab (default: 'git')
    # user: git

    ## Date & Time settings
    # Uncomment and customize if you want to change the default time zone of GitLab application.
    # To see all available zones, run `bundle exec rake time:zones:all RAILS_ENV=production`
    # time_zone: 'UTC'

    ## Email settings
    # Uncomment and set to false if you need to disable email sending from GitLab (default: true)
    # email_enabled: true
    # Email address used in the "From" field in mails sent by GitLab
    email_from: example@example.com
    email_display_name: GitLab
    email_reply_to: noreply@example.com

    # Email server smtp settings are in config/initializers/smtp_settings.rb.sample

    # default_can_create_group: false  # default: true
    # username_changing_enabled: false # default: true - User can change her username/namespace
    ## Default theme ID
    ##   1 - Graphite
    ##   2 - Charcoal
    ##   3 - Green
    ##   4 - Gray
    ##   5 - Violet
    ##   6 - Blue
    # default_theme: 2 # default: 2

    ## Automatic issue closing
    # If a commit message matches this regular expression, all issues referenced from the matched text will be closed.
    # This happens when the commit is pushed or merged into the default branch of a project.
    # When not specified the default issue_closing_pattern as specified below will be used.
    # Tip: you can test your closing pattern at http://rubular.com.
    # issue_closing_pattern: '((?:[Cc]los(?:e[sd]?|ing)|[Ff]ix(?:e[sd]|ing)?|[Rr]esolv(?:e[sd]?|ing))(:?) +(?:(?:issues? +)?%{issue_ref}(?:(?:, *| +and +)?)|([A-Z][A-Z0-9_]+-\d+))+)'

    ## Default project features settings
    default_projects_features:
      issues: true
      merge_requests: true
      wiki: true
      snippets: false
      builds: true
      container_registry: true

    ## Webhook settings
    # Number of seconds to wait for HTTP response after sending webhook HTTP POST request (default: 10)
    # webhook_timeout: 10

    ## Repository downloads directory
    # When a user clicks e.g. 'Download zip' on a project, a temporary zip file is created in the following directory.
    # The default is 'tmp/repositories' relative to the root of the Rails app.
    # repository_downloads_path: tmp/repositories


  ## Reply by email
  # Allow users to comment on issues and merge requests by replying to notification emails.
  # For documentation on how to set this up, see http://doc.gitlab.com/ce/incoming_email/README.html
  incoming_email:
    enabled: false

    # The email address including the `%{key}` placeholder that will be replaced to reference the item being replied to.
    # The placeholder can be omitted but if present, it must appear in the "user" part of the address (before the `@`).
    address: "gitlab-incoming+%{key}@gmail.com"

    # Email account username
    # With third party providers, this is usually the full email address.
    # With self-hosted email servers, this is usually the user part of the email address.
    user: "gitlab-incoming@gmail.com"
    # Email account password
    password: "[REDACTED]"

    # IMAP server host
    host: "imap.gmail.com"
    # IMAP server port
    port: 993
    # Whether the IMAP server uses SSL
    ssl: true
    # Whether the IMAP server uses StartTLS
    start_tls: false

    # The mailbox where incoming mail will end up. Usually "inbox".
    mailbox: "inbox"

  ## Build Artifacts
  artifacts:
    enabled: true
    # The location where build artifacts are stored (default: shared/artifacts).
    # path: shared/artifacts

  ## Git LFS
  lfs:
    enabled: true
    # The location where LFS objects are stored (default: shared/lfs-objects).
    # storage_path: shared/lfs-objects

  ## Gravatar
  ## For Libravatar see: http://doc.gitlab.com/ce/customization/libravatar.html
  gravatar:
    # gravatar urls: possible placeholders: %{hash} %{size} %{email}
    # plain_url: "http://..."     # default: http://www.gravatar.com/avatar/%{hash}?s=%{size}&d=identicon
    # ssl_url:   "https://..."    # default: https://secure.gravatar.com/avatar/%{hash}?s=%{size}&d=identicon

  ## Auxiliary jobs
  # Periodically executed jobs, to self-heal Gitlab, do external synchronizations, etc.
  # Please read here for more information: https://github.com/ondrejbartas/sidekiq-cron#adding-cron-job
  cron_jobs:
    # Flag stuck CI builds as failed
    stuck_ci_builds_worker:
      cron: "0 0 * * *"
    # Remove expired build artifacts
    expire_build_artifacts_worker:
      cron: "50 * * * *"
    # Periodically run 'git fsck' on all repositories. If started more than
    # once per hour you will have concurrent 'git fsck' jobs.
    repository_check_worker:
      cron: "20 * * * *"
    # Send admin emails once a week
    admin_email_worker:
      cron: "0 0 * * 0"

    # Remove outdated repository archives
    repository_archive_cache_worker:
      cron: "0 * * * *"

  registry:
    # enabled: true
    # host: registry.example.com
    # port: 5005
    # api_url: http://localhost:5000/ # internal address to the registry, will be used by GitLab to directly communicate with API
    # key: config/registry.key
    # path: shared/registry
    # issuer: gitlab-issuer

  #
  # 2. GitLab CI settings
  # ==========================

  gitlab_ci:
    # Default project notifications settings:
    #
    # Send emails only on broken builds (default: true)
    # all_broken_builds: true
    #

    #
    # Add pusher to recipients list (default: false)
    # add_pusher: true

    # The location where build traces are stored (default: builds/). Relative paths are relative to Rails.root
    # builds_path: builds/

  #
  # 3. Auth settings
  # ==========================

  ## LDAP settings
  # You can inspect a sample of the LDAP users with login access by running:
  #   bundle exec rake gitlab:ldap:check RAILS_ENV=production
  ldap:
    enabled: false
    servers:
      ##########################################################################
      #
      # Since GitLab 7.4, LDAP servers get ID's (below the ID is 'main'). GitLab
      # Enterprise Edition now supports connecting to multiple LDAP servers.
      #
      # If you are updating from the old (pre-7.4) syntax, you MUST give your
      # old server the ID 'main'.
      #
      ##########################################################################
      main: # 'main' is the GitLab 'provider ID' of this LDAP server
        ## label
        #
        # A human-friendly name for your LDAP server. It is OK to change the label later,
        # for instance if you find out it is too large to fit on the web page.
        #
        # Example: 'Paris' or 'Acme, Ltd.'
        label: 'LDAP'

        host: '_your_ldap_server'
        port: 389
        uid: 'sAMAccountName'
        method: 'plain' # "tls" or "ssl" or "plain"
        bind_dn: '_the_full_dn_of_the_user_you_will_bind_with'
        password: '_the_password_of_the_bind_user'

        # Set a timeout, in seconds, for LDAP queries. This helps avoid blocking
        # a request if the LDAP server becomes unresponsive.
        # A value of 0 means there is no timeout.
        timeout: 10

        # This setting specifies if LDAP server is Active Directory LDAP server.
        # For non AD servers it skips the AD specific queries.
        # If your LDAP server is not AD, set this to false.
        active_directory: true

        # If allow_username_or_email_login is enabled, GitLab will ignore everything
        # after the first '@' in the LDAP username submitted by the user on login.
        #
        # Example:
        # - the user enters 'jane.doe@example.com' and 'p@ssw0rd' as LDAP credentials;

        # - GitLab queries the LDAP server with 'jane.doe' and 'p@ssw0rd'.
        #
        # If you are using "uid: 'userPrincipalName'" on ActiveDirectory you need to
        # disable this setting, because the userPrincipalName contains an '@'.
        allow_username_or_email_login: false

        # To maintain tight control over the number of active users on your GitLab installation,
        # enable this setting to keep new users blocked until they have been cleared by the admin
        # (default: false).
        block_auto_created_users: false

        # Base where we can search for users
        #
        #   Ex. ou=People,dc=gitlab,dc=example
        #
        base: ''

        # Filter LDAP users
        #
        #   Format: RFC 4515 http://tools.ietf.org/search/rfc4515
        #   Ex. (employeeType=developer)
        #
        #   Note: GitLab does not support omniauth-ldap's custom filter syntax.
        #
        user_filter: ''

        # LDAP attributes that GitLab will use to create an account for the LDAP user.
        # The specified attribute can either be the attribute name as a string (e.g. 'mail'),
        # or an array of attribute names to try in order (e.g. ['mail', 'email']).
        # Note that the user's LDAP login will always be the attribute specified as `uid` above.
        attributes:
          # The username will be used in paths for the user's own projects
          # (like `gitlab.example.com/username/project`) and when mentioning
          # them in issues, merge request and comments (like `@username`).
          # If the attribute specified for `username` contains an email address,
          # the GitLab username will be the part of the email address before the '@'.
          username: ['uid', 'userid', 'sAMAccountName']
          email:    ['mail', 'email', 'userPrincipalName']

          # If no full name could be found at the attribute specified for `name`,
          # the full name is determined using the attributes specified for
          # `first_name` and `last_name`.
          name:       'cn'
          first_name: 'givenName'
          last_name:  'sn'

      # GitLab EE only: add more LDAP servers
      # Choose an ID made of a-z and 0-9 . This ID will be stored in the database
      # so that GitLab can remember which LDAP server a user belongs to.
      # uswest2:
      #   label:
      #   host:
      #   ....

  ## OmniAuth settings
  omniauth:
    # Allow login via Twitter, Google, etc. using OmniAuth providers
    enabled: false

    # Uncomment this to automatically sign in with a specific omniauth provider's without
    # showing GitLab's sign-in page (default: show the GitLab sign-in page)
    # auto_sign_in_with_provider: saml

    # CAUTION!
    # This allows users to login without having a user account first. Define the allowed providers
    # using an array, e.g. ["saml", "twitter"], or as true/false to allow all providers or none.
    # User accounts will be created automatically when authentication was successful.
    allow_single_sign_on: ["saml"]

    # Locks down those users until they have been cleared by the admin (default: true).
    block_auto_created_users: true
    # Look up new users in LDAP servers. If a match is found (same uid), automatically
    # link the omniauth identity with the LDAP account. (default: false)
    auto_link_ldap_user: false

    # Allow users with existing accounts to login and auto link their account via SAML
    # login, without having to do a manual login first and manually add SAML
    # (default: false)
    auto_link_saml_user: false

    # Set different Omniauth providers as external so that all users creating accounts
    # via these providers will not be able to have access to internal projects. You
    # will need to use the full name of the provider, like `google_oauth2` for Google.
    # Refer to the examples below for the full names of the supported providers.
    # (default: [])
    external_providers: []

    ## Auth providers
    # Uncomment the following lines and fill in the data of the auth provider you want to use
    # If your favorite auth provider is not listed you can use others:
    # see https://github.com/gitlabhq/gitlab-public-wiki/wiki/Custom-omniauth-provider-configurations
    # The 'app_id' and 'app_secret' parameters are always passed as the first two
    # arguments, followed by optional 'args' which can be either a hash or an array.
    # Documentation for this is available at http://doc.gitlab.com/ce/integration/omniauth.html
    providers:
      # See omniauth-cas3 for more configuration details
      # - { name: 'cas3',
      #     label: 'cas3',
      #     args: {
      #             url: 'https://sso.example.com',
      #             disable_ssl_verification: false,
      #             login_url: '/cas/login',
      #             service_validate_url: '/cas/p3/serviceValidate',
      #             logout_url: '/cas/logout'} }
      # - { name: 'github',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET',

      #     url: "https://github.com/",
      #     verify_ssl: true,
      #     args: { scope: 'user:email' } }
      # - { name: 'bitbucket',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET' }
      # - { name: 'gitlab',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET',
      #     args: { scope: 'api' } }
      # - { name: 'google_oauth2',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET',
      #     args: { access_type: 'offline', approval_prompt: '' } }
      # - { name: 'facebook',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET' }
      # - { name: 'twitter',
      #     app_id: 'YOUR_APP_ID',
      #     app_secret: 'YOUR_APP_SECRET' }
      #
      # - { name: 'saml',
      #     label: 'Our SAML Provider',
      #     groups_attribute: 'Groups',
      #     external_groups: ['Contractors', 'Freelancers'],
      #     args: {
      #             assertion_consumer_service_url: 'https://gitlab.example.com/users/auth/saml/callback',
      #             idp_cert_fingerprint: '43:51:43:a1:b5:fc:8b:b7:0a:3a:a9:b1:0f:66:73:a8',
      #             idp_sso_target_url: 'https://login.example.com/idp',
      #             issuer: 'https://gitlab.example.com',
      #             name_identifier_format: 'urn:oasis:names:tc:SAML:2.0:nameid-format:transient'
      #           } }
      #
      # - { name: 'crowd',
      #     args: {
      #       crowd_server_url: 'CROWD SERVER URL',
      #       application_name: 'YOUR_APP_NAME',
      #       application_password: 'YOUR_APP_PASSWORD' } }
      #
      # - { name: 'auth0',
      #     args: {
      #       client_id: 'YOUR_AUTH0_CLIENT_ID',
      #       client_secret: 'YOUR_AUTH0_CLIENT_SECRET',
      #       namespace: 'YOUR_AUTH0_DOMAIN' } }

    # SSO maximum session duration in seconds. Defaults to CAS default of 8 hours.
    # cas3:
    #   session_duration: 28800

  # Shared file storage settings
  shared:
    # path: /mnt/gitlab # Default: shared


  #
  # 4. Advanced settings
  # ==========================

  # GitLab Satellites
  #
  # Note for maintainers: keep the satellites.path setting until GitLab 9.0 at
  # least. This setting is fed to 'rm -rf' in
  # db/migrate/20151023144219_remove_satellites.rb
  satellites:
    path: /home/git/gitlab-satellites/

  ## Backup settings
  backup:
    path: "tmp/backups"   # Relative paths are relative to Rails.root (default: tmp/backups/)
    # archive_permissions: 0640 # Permissions for the resulting backup.tar file (default: 0600)
    # keep_time: 604800   # default: 0 (forever) (in seconds)
    # pg_schema: public     # default: nil, it means that all schemas will be backed up
    # upload:
    #   # Fog storage connection settings, see http://fog.io/storage/ .
    #   connection:
    #     provider: AWS
    #     region: eu-west-1
    #     aws_access_key_id: AKIAKIAKI
    #     aws_secret_access_key: 'secret123'
    #   # The remote 'directory' to store your backups. For S3, this would be the bucket name.
    #   remote_directory: 'my.s3.bucket'
    #   # Use multipart uploads when file size reaches 100MB, see
    #   #  http://docs.aws.amazon.com/AmazonS3/latest/dev/uploadobjusingmpu.html
    #   multipart_chunk_size: 104857600
    #   # Turns on AWS Server-Side Encryption with Amazon S3-Managed Keys for backups, this is optional
    #   # encryption: 'AES256'

  ## GitLab Shell settings
  gitlab_shell:
    path: /home/git/gitlab-shell/

    # REPOS_PATH MUST NOT BE A SYMLINK!!!
    repos_path: /home/git/repositories/
    hooks_path: /home/git/gitlab-shell/hooks/

    # File that contains the secret key for verifying access for gitlab-shell.
    # Default is '.gitlab_shell_secret' relative to Rails.root (i.e. root of the GitLab app).
    # secret_file: /home/git/gitlab/.gitlab_shell_secret

    # Git over HTTP
    upload_pack: true
    receive_pack: true

    # If you use non-standard ssh port you need to specify it
    # ssh_port: 22

  ## Git settings
  # CAUTION!
  # Use the default values unless you really know what you are doing

  git:
    bin_path: /usr/bin/git
    # The next value is the maximum memory size grit can use
    # Given in number of bytes per git object (e.g. a commit)
    # This value can be increased if you have very large commits
    max_size: 20971520 # 20.megabytes
    # Git timeout to read a commit, in seconds
    timeout: 10

  #
  # 5. Extra customization
  # ==========================

  extra:
    ## Google analytics. Uncomment if you want it
    # google_analytics_id: '_your_tracking_id'

    ## Piwik analytics.
    # piwik_url: '_your_piwik_url'
    # piwik_site_id: '_your_piwik_site_id'

  rack_attack:
    git_basic_auth:
      # Rack Attack IP banning enabled
      # enabled: true
      #
      # Whitelist requests from 127.0.0.1 for web proxies (NGINX/Apache) with incorrect headers
      # ip_whitelist: ["127.0.0.1"]
      #
      # Limit the number of Git HTTP authentication attempts per IP
      # maxretry: 10
      #
      # Reset the auth attempt counter per IP after 60 seconds
      # findtime: 60
      #
      # Ban an IP for one hour (3600s) after too many auth attempts
      # bantime: 3600

development:
  <<: *base

test:
  <<: *base
  gravatar:
    enabled: true
  lfs:
    enabled: false
  gitlab:
    host: localhost
    port: 80

    # When you run tests we clone and setup gitlab-shell
    # In order to setup it correctly you need to specify
    # your system username you use to run GitLab
    # user: YOUR_USERNAME
  satellites:
    path: tmp/tests/gitlab-satellites/

  backup:
    path: tmp/tests/backups
  gitlab_shell:
    path: tmp/tests/gitlab-shell/
    repos_path: tmp/tests/repositories/
    hooks_path: tmp/tests/gitlab-shell/hooks/
  issues_tracker:
    redmine:
      title: "Redmine"
      project_url: "http://redmine/projects/:issues_tracker_id"
      issues_url: "http://redmine/:project_id/:issues_tracker_id/:id"
      new_issue_url: "http://redmine/projects/:issues_tracker_id/issues/new"
  ldap:
    enabled: false
    servers:
      main:
        label: ldap
        host: 127.0.0.1
        port: 3890
        uid: 'uid'
        method: 'plain' # "tls" or "ssl" or "plain"
        base: 'dc=example,dc=com'
        user_filter: ''
        group_base: 'ou=groups,dc=example,dc=com'
        admin_group: ''

staging:
  <<: *base




```

##### Copy the example secrets file
```
sudo -u git -H cp config/secrets.yml.example config/secrets.yml
sudo -u git -H chmod 0600 config/secrets.yml
```
##### Make sure GitLab can write to the log/ and tmp/ directories
```
sudo chown -R git log/
sudo chown -R git tmp/
sudo chmod -R u+rwX,go-w log/
sudo chmod -R u+rwX tmp/
```
    # Make sure GitLab can write to the tmp/pids/ and tmp/sockets/ directories
    sudo chmod -R u+rwX tmp/pids/
    sudo chmod -R u+rwX tmp/sockets/

    # Create the public/uploads/ directory
    sudo -u git -H mkdir public/uploads/

    # Make sure only the GitLab user has access to the public/uploads/ directory
    # now that files in public/uploads are served by gitlab-workhorse
    sudo chmod 0700 public/uploads

    sudo chmod ug+rwX,o-rwx /home/git/repositories/

    # Change the permissions of the directory where CI build traces are stored
    sudo chmod -R u+rwX builds/

    # Change the permissions of the directory where CI artifacts are stored
    sudo chmod -R u+rwX shared/artifacts/

    # Copy the example Unicorn config
    sudo -u git -H cp config/unicorn.rb.example config/unicorn.rb

    # Find number of cores
    nproc

    # Enable cluster mode if you expect to have a high load instance
    # Ex. change amount of workers to 3 for 2GB RAM server
    # Set the number of workers to at least the number of cores
    sudo -u git -H editor config/unicorn.rb

    # Copy the example Rack attack config
    sudo -u git -H cp config/initializers/rack_attack.rb.example config/initializers/rack_attack.rb

    # Configure Git global settings for git user
    # 'autocrlf' is needed for the web editor
    sudo -u git -H git config --global core.autocrlf input

    # Disable 'git gc --auto' because GitLab already runs 'git gc' when needed
    sudo -u git -H git config --global gc.auto 0

    # Configure Redis connection settings
    sudo -u git -H cp config/resque.yml.example config/resque.yml

    # Change the Redis socket path if you are not using the default CentOS configuration
    sudo -u git -H editor config/resque.yml

**Important Note:** Make sure to edit both `gitlab.yml` and `unicorn.rb` to match your setup.

**Note:** If you want to use HTTPS, see [Using HTTPS][https] for the additional steps.

### Configure GitLab DB settings

    # PostgreSQL only:
    sudo -u git cp config/database.yml.postgresql config/database.yml

    # MySQL only:
    sudo -u git cp config/database.yml.mysql config/database.yml

    # MySQL and remote PostgreSQL only:
    # Update username/password in config/database.yml.
    # You only need to adapt the production settings (first part).
    # If you followed the database guide then please do as follows:
    # Change 'secure password' with the value you have given to $password
    # You can keep the double quotes around the password
    sudo -u git -H editor config/database.yml

    # PostgreSQL and MySQL:
    # Make config/database.yml readable to git only
    sudo -u git -H chmod o-rwx config/database.yml

### Install Gems

**Note:** As of bundler 1.5.2, you can invoke `bundle install -jN`
(where `N` the number of your processor cores) and enjoy the parallel gems installation with measurable
difference in completion time (~60% faster). Check the number of your cores with `nproc`.
For more information check this [post](http://robots.thoughtbot.com/parallel-gem-installing-using-bundler).
First make sure you have bundler >= 1.5.2 (run `bundle -v`) as it addresses some [issues](https://devcenter.heroku.com/changelog-items/411)
that were [fixed](https://github.com/bundler/bundler/pull/2817) in 1.5.2.

    cd /home/git/gitlab

    # For PostgreSQL (note, the option says "without ... mysql")
    sudo -u git -H bundle config build.pg --with-pg-config=/usr/pgsql-9.3/bin/pg_config
    sudo -u git -H bundle install --deployment --without development test mysql aws kerberos

    # Or for MySQL (note, the option says "without ... postgres")
    sudo -u git -H bundle install --deployment --without development test postgres aws kerberos

**Note:** If you want to use Kerberos for user authentication, then omit `kerberos`
in the `--without` option above.

### Install GitLab shell

GitLab Shell is an SSH access and repository management software developed specially for GitLab.

    # Run the installation task for gitlab-shell (replace `REDIS_URL` if needed):
    sudo -u git -H bundle exec rake gitlab:shell:install[v3.0.0] REDIS_URL=unix:/var/run/redis/redis.sock RAILS_ENV=production

    # By default, the gitlab-shell config is generated from your main GitLab config.
    # You can review (and modify) the gitlab-shell config as follows:
    sudo -u git -H editor /home/git/gitlab-shell/config.yml

    # Ensure the correct SELinux contexts are set
    # Read http://wiki.centos.org/HowTos/Network/SecuringSSH
    restorecon -Rv /home/git/.ssh

**Note:** If you want to use HTTPS, see [Using HTTPS](#using-https) for the additional steps.

**Note:** Make sure your hostname can be resolved on the machine itself by either a
proper DNS record or an additional line in /etc/hosts ("127.0.0.1
hostname"). This might be necessary for example if you set up GitLab behind a
reverse proxy. If the hostname cannot be resolved, the final installation check
will fail with "Check GitLab API access: FAILED. code: 401" and pushing commits
will be rejected with "[remote rejected] master -> master (hook declined)".

### Install gitlab-workhorse

    cd /home/git
    sudo -u git -H git clone https://gitlab.com/gitlab-org/gitlab-workhorse.git
    cd gitlab-workhorse
    sudo -u git -H git checkout v0.7.5
    sudo -u git -H make

### Initialize Database and Activate Advanced Features

    # Go to GitLab installation folder

    cd /home/git/gitlab

    sudo -u git -H bundle exec rake gitlab:setup RAILS_ENV=production

    # Type 'yes' to create the database tables.

    # When done you see 'Administrator account created:'

**Note:** You can set the Administrator/root password and e-mail by supplying
  them in environmental variables, `GITLAB_ROOT_PASSWORD` and
  `GITLAB_ROOT_EMAIL` respectively, as seen below. If you don't set the
  password (and it is set to the default one) please wait with exposing GitLab
  to the public internet until the installation is done and you've logged into
  the server the first time. During the first login you'll be forced to change
  the default password.

    sudo -u git -H bundle exec rake gitlab:setup RAILS_ENV=production GITLAB_ROOT_PASSWORD=yourpassword GITLAB_ROOT_EMAIL=youremail

### Secure secrets.yml

The `secrets.yml` file stores encryption keys for sessions and secure variables.
Backup `secrets.yml` someplace safe, but don't store it in the same place as your
database backups. Otherwise your secrets are exposed if one of your backups is
compromised.

### Install Init Script

Download the init script (will be `/etc/init.d/gitlab`):

    cp lib/support/init.d/gitlab /etc/init.d/gitlab

And if you are installing with a non-default folder or user copy and edit the defaults file:

    cp lib/support/init.d/gitlab.default.example /etc/default/gitlab

If you installed GitLab in another directory or as a user other than the default you should change these settings in `/etc/default/gitlab`. Do not edit `/etc/init.d/gitlab` as it will be
changed on upgrade.

Make GitLab start on boot:

    chkconfig gitlab on

### Set up logrotate

    cp lib/support/logrotate/gitlab /etc/logrotate.d/gitlab

### Check Application Status

Check if GitLab and its environment are configured correctly:

    sudo -u git -H bundle exec rake gitlab:env:info RAILS_ENV=production

### Compile assets

    sudo -u git -H bundle exec rake assets:precompile RAILS_ENV=production

### Start your GitLab instance

    service gitlab start

------

## 8. Configure the web server

Use either Nginx or Apache, not both. Official installation guide recommends nginx.

### Nginx

#### Installation

You will need a new version of nginx otherwise you might encounter an issue like [this][issue-nginx].
To do so, follow the instructions provided by the [nginx wiki][nginx-centos] and then install nginx with:

    yum update
    yum -y install nginx
    chkconfig nginx on

#### Site Configuration

    cp lib/support/nginx/gitlab /etc/nginx/conf.d/gitlab.conf

Make sure to edit the config file to match your setup:

    # Change YOUR_SERVER_FQDN to the fully-qualified
    # domain name of your host serving GitLab.

**Note:** If you want to use HTTPS, replace the `gitlab` Nginx config with `gitlab-ssl`. See [Using HTTPS](#using-https) for HTTPS configuration details.

Add `nginx` user to `git` group:

    usermod -a -G git nginx
    chmod g+rx /home/git/

#### Test Configuration

Validate your `gitlab` or `gitlab-ssl` Nginx config file with the following command:

    nginx -t

You should receive `syntax is okay` and `test is successful` messages. If you receive errors check your `gitlab` or `gitlab-ssl` Nginx config file for typos, etc. as indiciated in the error message given.


#### Restart

    service nginx restart

### Apache

Httpd can be configured with or without SSL support.  Please choose appropriate commands in next steps.

#### GitLab-Workhorse

Apache installation requires changes to gitlab-workhorse configuration. Change
`gitlab_workhorse_options` in `/etc/default/gitlab` to the following:

    gitlab_workhorse_options="-listenUmask 0 -listenNetwork tcp -listenAddr 127.0.0.1:8181 -authBackend http://127.0.0.1:8080"

And restart:

    service gitlab restart

#### HTTPS

We will configure apache with module `mod_proxy` which is loaded by default when
installing apache and `mod_ssl` which will provide ssl support:

    yum -y install httpd mod_ssl
    chkconfig httpd on
    wget -O /etc/httpd/conf.d/gitlab.conf https://gitlab.com/gitlab-org/gitlab-recipes/raw/master/web-server/apache/gitlab-ssl-apache22.conf
    mv /etc/httpd/conf.d/ssl.conf{,.bak}
    sed -i 's/logs\///g' /etc/httpd/conf.d/gitlab.conf

Open `/etc/httpd/conf.d/gitlab.conf` with your editor and replace `YOUR_SERVER_FQDN` with your FQDN. Also make sure the path to your certificates is valid.

Add `LoadModule ssl_module /etc/httpd/modules/mod_ssl.so` in `/etc/httpd/conf/httpd.conf`.

#### HTTP

We will configure apache with module `mod_proxy` which is loaded by default when
installing apache:

    yum -y install httpd
    chkconfig httpd on
    wget -O /etc/httpd/conf.d/gitlab.conf https://gitlab.com/gitlab-org/gitlab-recipes/raw/master/web-server/apache/gitlab-apache22.conf
    sed -i 's/logs\///g' /etc/httpd/conf.d/gitlab.conf

Open `/etc/httpd/conf.d/gitlab.conf` with your editor and replace `YOUR_SERVER_FQDN` with your FQDN.

#### SELinux

To configure SELinux read the **SELinux modifications** section in [README](https://gitlab.com/gitlab-org/gitlab-recipes/blob/master/web-server/apache/README.md).

Finally, start apache:

    service httpd start

**Note:**
If you want to run other websites on the same system, you'll need to add in `/etc/httpd/conf/httpd.conf`:

    NameVirtualHost *:80
    <IfModule mod_ssl.c>
        # If you add NameVirtualHost *:443 here, you will also have to change
        # the VirtualHost statement in /etc/httpd/conf.d/gitlab.conf
        # to <VirtualHost *:443>
        NameVirtualHost *:443
        Listen 443
    </IfModule>

------

## 9. Configure the firewall

Poke an iptables hole so users can access the web server (http and https ports) and ssh.

    lokkit -s http -s https -s ssh

Restart the service for the changes to take effect:

    service iptables restart

## Done!

### Double-check Application Status

To make sure you didn't miss anything run a more thorough check with:

    cd /home/git/gitlab
    sudo -u git -H bundle exec rake gitlab:check RAILS_ENV=production

If all items are green, then congratulations on successfully installing GitLab!

**NOTE:** Supply `SANITIZE=true` environment variable to `gitlab:check` to omit project names from the output of the check command.

## Initial Login

If you didn't [provide a root password during setup](#initialize-database-and-activate-advanced-features),
you'll be redirected to a password reset screen to provide the password for the
initial administrator account. Enter your desired password and you'll be
redirected back to the login screen.

The default account's username is **root**. Provide the password you created
earlier and login. After login you can change the username if you wish.

**Enjoy!**

You can use `sudo service gitlab start` and `sudo service gitlab stop` to start and stop GitLab.

You can also check some [Advanced Setup Tips][tips].

## Links used in this guide

- [EPEL information](http://www.thegeekstuff.com/2012/06/enable-epel-repository/)
- [SELinux booleans](http://wiki.centos.org/TipsAndTricks/SelinuxBooleans)

[https]: https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/install/installation.md#using-https
[EPEL]: https://fedoraproject.org/wiki/EPEL
[REMI]: http://rpms.famillecollet.com/
[PUIAS]: https://puias.math.ias.edu/wiki/YumRepositories6#Computational
[SDL]: https://puias.math.ias.edu
[PU]: http://www.princeton.edu/
[IAS]: http://www.ias.edu/
[keys]: https://fedoraproject.org/keys
[issue-nginx]: https://github.com/gitlabhq/gitlabhq/issues/5774
[nginx-centos]: http://wiki.nginx.org/Install#Official_Red_Hat.2FCentOS_packages
[psql-doc-auth]: http://www.postgresql.org/docs/9.3/static/auth-methods.html
[tips]: https://gitlab.com/gitlab-org/gitlab-ce/blob/master/doc/install/installation.md#advanced-setup-tips
