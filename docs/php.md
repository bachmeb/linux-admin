# php

## References
* http://stackoverflow.com/questions/15346605/php-apache-php-fatal-error-call-to-undefined-function-mysql-connect

##### Search yum for php
```
sudo yum search php
```

##### Search yum for installed php packages
```
sudo yum list installed | grep php
```
```c
/*
php.x86_64                            5.3.3-46.el6_7.1                 @updates 
php-cli.x86_64                        5.3.3-46.el6_7.1                 @updates 
php-common.x86_64                     5.3.3-46.el6_7.1                 @updates 
*/
```

##### Search yum for php & mysql
```
sudo yum search mysql | grep php
```
```c
/*
php-ZendFramework-Db-Adapter-Mysqli.noarch : Zend Framework database adapter for
php-ZendFramework-Db-Adapter-Pdo-Mysql.noarch : Zend Framework database adapter
php-mysql.x86_64 : A module for PHP applications that use MySQL databases
php-pear-MDB2-Driver-mysql.noarch : MySQL MDB2 driver
php-pear-MDB2-Driver-mysqli.noarch : MySQL Improved MDB2 driver
php55u-mysqlnd.x86_64 : A module for PHP applications that use MySQL databases
php56u-mysqlnd.x86_64 : A module for PHP applications that use MySQL databases
php70u-mysqlnd.x86_64 : A module for PHP applications that use MySQL databases
php-udan11-sql-parser.noarch : A validating SQL lexer and parser with a focus on
phpMyAdmin.noarch : Handle the administration of MySQL over the World Wide Web
*/
```

##### Display php info
```
php -i
```
```php
This program makes use of the Zend Scripting Language Engine:
Zend Engine v2.3.0, Copyright (c) 1998-2010 Zend Technologies


 _______________________________________________________________________


Configuration

bz2

BZip2 Support => Enabled
Stream Wrapper support => compress.bz2://
Stream Filter support => bzip2.decompress, bzip2.compress
BZip2 Version => 1.0.5, 10-Dec-2007

calendar

Calendar support => enabled

Core

PHP Version => 5.3.3

Directive => Local Value => Master Value
allow_call_time_pass_reference => Off => Off
allow_url_fopen => On => On
allow_url_include => Off => Off
always_populate_raw_post_data => Off => Off
arg_separator.input => & => &
arg_separator.output => & => &
asp_tags => Off => Off
auto_append_file => no value => no value
auto_globals_jit => On => On
auto_prepend_file => no value => no value
browscap => no value => no value
default_charset => no value => no value
default_mimetype => text/html => text/html
define_syslog_variables => Off => Off
disable_classes => no value => no value
disable_functions => no value => no value
display_errors => Off => Off
display_startup_errors => Off => Off
doc_root => no value => no value
docref_ext => no value => no value
docref_root => no value => no value
enable_dl => Off => Off
error_append_string => no value => no value
error_log => no value => no value
error_prepend_string => no value => no value
error_reporting => 22527 => 22527
exit_on_timeout => Off => Off
expose_php => On => On
extension_dir => /usr/lib64/php/modules => /usr/lib64/php/modules
file_uploads => On => On
highlight.bg => <font style="color: #FFFFFF">#FFFFFF</font> => <font style="color: #FFFFFF">#FFFFFF</font>
highlight.comment => <font style="color: #FF8000">#FF8000</font> => <font style="color: #FF8000">#FF8000</font>
highlight.default => <font style="color: #0000BB">#0000BB</font> => <font style="color: #0000BB">#0000BB</font>
highlight.html => <font style="color: #000000">#000000</font> => <font style="color: #000000">#000000</font>
highlight.keyword => <font style="color: #007700">#007700</font> => <font style="color: #007700">#007700</font>
highlight.string => <font style="color: #DD0000">#DD0000</font> => <font style="color: #DD0000">#DD0000</font>
html_errors => Off => Off
ignore_repeated_errors => Off => Off
ignore_repeated_source => Off => Off
ignore_user_abort => Off => Off
implicit_flush => On => On
include_path => .:/usr/share/pear:/usr/share/php => .:/usr/share/pear:/usr/share/php
log_errors => On => On
log_errors_max_len => 1024 => 1024
magic_quotes_gpc => Off => Off
magic_quotes_runtime => Off => Off
magic_quotes_sybase => Off => Off
mail.add_x_header => On => On
mail.force_extra_parameters => no value => no value
mail.log => no value => no value
max_execution_time => 0 => 0
max_file_uploads => 20 => 20
max_input_nesting_level => 64 => 64
max_input_time => -1 => -1
max_input_vars => 1000 => 1000
memory_limit => 128M => 128M
open_basedir => no value => no value
output_buffering => 0 => 0
output_handler => no value => no value
post_max_size => 8M => 8M
precision => 14 => 14
realpath_cache_size => 16K => 16K
realpath_cache_ttl => 120 => 120
register_argc_argv => On => On
register_globals => Off => Off
register_long_arrays => Off => Off
report_memleaks => On => On
report_zend_debug => Off => Off
request_order => GP => GP
safe_mode => Off => Off
safe_mode_exec_dir => no value => no value
safe_mode_gid => Off => Off
safe_mode_include_dir => no value => no value
sendmail_from => no value => no value
sendmail_path => /usr/sbin/sendmail -t -i => /usr/sbin/sendmail -t -i
serialize_precision => 100 => 100
short_open_tag => Off => Off
SMTP => localhost => localhost
smtp_port => 25 => 25
sql.safe_mode => Off => Off
track_errors => Off => Off
unserialize_callback_func => no value => no value
upload_max_filesize => 2M => 2M
upload_tmp_dir => no value => no value
user_dir => no value => no value
user_ini.cache_ttl => 300 => 300
user_ini.filename => .user.ini => .user.ini
variables_order => GPCS => GPCS
xmlrpc_error_number => 0 => 0
xmlrpc_errors => Off => Off
y2k_compliance => On => On
zend.enable_gc => On => On

ctype

ctype functions => enabled

curl

cURL support => enabled
cURL Information => 7.19.7
Age => 3
Features
AsynchDNS => No
Debug => No
GSS-Negotiate => Yes
IDN => Yes
IPv6 => Yes
Largefile => Yes
NTLM => Yes
SPNEGO => No
SSL => Yes
SSPI => No
krb4 => No
libz => Yes
CharConv => No
Protocols => tftp, ftp, telnet, dict, ldap, ldaps, http, file, https, ftps, scp, sftp
Host => x86_64-redhat-linux-gnu
SSL Version => NSS/3.19.1 Basic ECC
ZLib Version => 1.2.3
libSSH Version => libssh2/1.4.2

date

date/time support => enabled
"Olson" Timezone Database Version => 0.system
Timezone Database => internal
PHP Warning:  Unknown: It is not safe to rely on the system's timezone settings. You are *required* to use the date.timezone setting or the date_default_timezone_set() function. In case you used any of those methods and you are still getting this warning, you most likely misspelled the timezone identifier. We selected 'America/New_York' for 'EDT/-4.0/DST' instead in Unknown on line 0
Default timezone => America/New_York

Directive => Local Value => Master Value
date.default_latitude => 31.7667 => 31.7667
date.default_longitude => 35.2333 => 35.2333
date.sunrise_zenith => 90.583333 => 90.583333
date.sunset_zenith => 90.583333 => 90.583333
date.timezone => no value => no value

ereg

Regex Library => Bundled library enabled

exif

EXIF Support => enabled
EXIF Version => 1.4 $Id: exif.c 293036 2010-01-03 09:23:27Z sebastian $
Supported EXIF Version => 0220
Supported filetypes => JPEG,TIFF

Directive => Local Value => Master Value
exif.decode_jis_intel => JIS => JIS
exif.decode_jis_motorola => JIS => JIS
exif.decode_unicode_intel => UCS-2LE => UCS-2LE
exif.decode_unicode_motorola => UCS-2BE => UCS-2BE
exif.encode_jis => no value => no value
exif.encode_unicode => ISO-8859-15 => ISO-8859-15

fileinfo

fileinfo support => enabled
version => 1.0.5-dev

filter

Input Validation and Filtering => enabled
Revision => $Revision: 298196 $

Directive => Local Value => Master Value
filter.default => unsafe_raw => unsafe_raw
filter.default_flags => no value => no value

ftp

FTP support => enabled

gettext

GetText Support => enabled

gmp

gmp support => enabled
GMP version => 4.3.1

hash

hash support => enabled
Hashing Engines => md2 md4 md5 sha1 sha224 sha256 sha384 sha512 ripemd128 ripemd160 ripemd256 ripemd320 whirlpool tiger128,3 tiger160,3 tiger192,3 tiger128,4 tiger160,4 tiger192,4 snefru snefru256 gost adler32 crc32 crc32b salsa10 salsa20 haval128,3 haval160,3 haval192,3 haval224,3 haval256,3 haval128,4 haval160,4 haval192,4 haval224,4 haval256,4 haval128,5 haval160,5 haval192,5 haval224,5 haval256,5 

iconv

iconv support => enabled
iconv implementation => glibc
iconv library version => 2.12

Directive => Local Value => Master Value
iconv.input_encoding => ISO-8859-1 => ISO-8859-1
iconv.internal_encoding => ISO-8859-1 => ISO-8859-1
iconv.output_encoding => ISO-8859-1 => ISO-8859-1

json

json support => enabled
json version => 1.2.1

libxml

libXML support => active
libXML Compiled Version => 2.7.6
libXML Loaded Version => 20706
libXML streams => enabled

openssl

OpenSSL support => enabled
OpenSSL Library Version => OpenSSL 1.0.1e-fips 11 Feb 2013
OpenSSL Header Version => OpenSSL 1.0.1e-fips 11 Feb 2013

pcntl

pcntl support => enabled

pcre

PCRE (Perl Compatible Regular Expressions) Support => enabled
PCRE Library Version => 7.8 2008-09-05

Directive => Local Value => Master Value
pcre.backtrack_limit => 100000 => 100000
pcre.recursion_limit => 100000 => 100000

Phar

Phar: PHP Archive support => enabled
Phar EXT version => 2.0.1
Phar API version => 1.1.1
SVN revision => $Revision: 298908 $
Phar-based phar archives => enabled
Tar-based phar archives => enabled
ZIP-based phar archives => enabled
gzip compression => enabled
bzip2 compression => enabled
Native OpenSSL support => enabled


Phar based on pear/PHP_Archive, original concept by Davey Shafik.
Phar fully realized by Gregory Beaver and Marcus Boerger.
Portions of tar implementation Copyright (c) 2003-2009 Tim Kientzle.
Directive => Local Value => Master Value
phar.cache_list => no value => no value
phar.readonly => On => On
phar.require_hash => On => On

Reflection

Reflection => enabled
Version => $Revision: 300393 $

session

Session Support => enabled
Registered save handlers => files user 
Registered serializer handlers => php php_binary 

Directive => Local Value => Master Value
session.auto_start => Off => Off
session.bug_compat_42 => Off => Off
session.bug_compat_warn => Off => Off
session.cache_expire => 180 => 180
session.cache_limiter => nocache => nocache
session.cookie_domain => no value => no value
session.cookie_httponly => Off => Off
session.cookie_lifetime => 0 => 0
session.cookie_path => / => /
session.cookie_secure => Off => Off
session.entropy_file => no value => no value
session.entropy_length => 0 => 0
session.gc_divisor => 1000 => 1000
session.gc_maxlifetime => 1440 => 1440
session.gc_probability => 1 => 1
session.hash_bits_per_character => 5 => 5
session.hash_function => 0 => 0
session.name => PHPSESSID => PHPSESSID
session.referer_check => no value => no value
session.save_handler => files => files
session.save_path => /var/lib/php/session => /var/lib/php/session
session.serialize_handler => php => php
session.use_cookies => On => On
session.use_only_cookies => On => On
session.use_trans_sid => 0 => 0

shmop

shmop support => enabled

SimpleXML

Simplexml support => enabled
Revision => $Revision: 299424 $
Schema support => enabled

sockets

Sockets Support => enabled

SPL

SPL support => enabled
Interfaces => Countable, OuterIterator, RecursiveIterator, SeekableIterator, SplObserver, SplSubject
Classes => AppendIterator, ArrayIterator, ArrayObject, BadFunctionCallException, BadMethodCallException, CachingIterator, DirectoryIterator, DomainException, EmptyIterator, FilesystemIterator, FilterIterator, GlobIterator, InfiniteIterator, InvalidArgumentException, IteratorIterator, LengthException, LimitIterator, LogicException, MultipleIterator, NoRewindIterator, OutOfBoundsException, OutOfRangeException, OverflowException, ParentIterator, RangeException, RecursiveArrayIterator, RecursiveCachingIterator, RecursiveDirectoryIterator, RecursiveFilterIterator, RecursiveIteratorIterator, RecursiveRegexIterator, RecursiveTreeIterator, RegexIterator, RuntimeException, SplDoublyLinkedList, SplFileInfo, SplFileObject, SplFixedArray, SplHeap, SplMinHeap, SplMaxHeap, SplObjectStorage, SplPriorityQueue, SplQueue, SplStack, SplTempFileObject, UnderflowException, UnexpectedValueException

standard

Dynamic Library Support => enabled
Path to sendmail => /usr/sbin/sendmail -t -i

Directive => Local Value => Master Value
assert.active => 1 => 1
assert.bail => 0 => 0
assert.callback => no value => no value
assert.quiet_eval => 0 => 0
assert.warning => 1 => 1
auto_detect_line_endings => 0 => 0
default_socket_timeout => 60 => 60
safe_mode_allowed_env_vars => PHP_ => PHP_
safe_mode_protected_env_vars => LD_LIBRARY_PATH => LD_LIBRARY_PATH
url_rewriter.tags => a=href,area=href,frame=src,input=src,form=fakeentry => a=href,area=href,frame=src,input=src,form=fakeentry
user_agent => no value => no value

tokenizer

Tokenizer Support => enabled

xml

XML Support => active
XML Namespace Support => active
libxml2 Version => 2.7.6

zip

Zip => enabled
Extension Version => $Id: php_zip.c 300470 2010-06-15 18:48:33Z pajoye $
Zip version => 1.9.1
Libzip version => 0.9.0

zlib

ZLib Support => enabled
Stream Wrapper support => compress.zlib://
Stream Filter support => zlib.inflate, zlib.deflate
Compiled Version => 1.2.3
Linked Version => 1.2.3

Directive => Local Value => Master Value
zlib.output_compression => Off => Off
zlib.output_compression_level => -1 => -1
zlib.output_handler => no value => no value

Additional Modules

Module Name
readline

Environment

Variable => Value
ORBIT_SOCKETDIR => /tmp/orbit-bachmeb
VNCDESKTOP => 99700hlzx6g1:2 (bachmeb)
SSH_AGENT_PID => 5131
HOSTNAME => 99700hlzx6g1
GIO_LAUNCHED_DESKTOP_FILE_PID => 5301
TERM => xterm
SHELL => /bin/bash
HISTSIZE => 1000
XDG_SESSION_COOKIE => 75428f747188af479bb910fa0000001a-1463088293.813748-2046045595
GTK_RC_FILES => /etc/gtk/gtkrc:/home/bachmeb/.gtkrc-1.2-gnome2
WINDOWID => 35651587
SYSFONT => latarcyrheb-sun16
QTDIR => /usr/lib64/qt-3.3
QTINC => /usr/lib64/qt-3.3/include
USER => bachmeb
LS_COLORS => di=01;36:
GNOME_KEYRING_SOCKET => /tmp/keyring-7mzlGf/socket
SSH_AUTH_SOCK => /tmp/keyring-7mzlGf/socket.ssh
SESSION_MANAGER => local/unix:@/tmp/.ICE-unix/5130,unix/unix:/tmp/.ICE-unix/5130
GIO_LAUNCHED_DESKTOP_FILE => /usr/share/applications/gnome-terminal.desktop
PATH => /usr/lib64/qt-3.3/bin:/usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/sbin:/home/bachmeb/bin
MAIL => /var/spool/mail/bachmeb
PWD => /var/wiki/html
LANG => en_US.UTF-8
SSH_ASKPASS => /usr/libexec/openssh/gnome-ssh-askpass
HISTCONTROL => ignoredups
HOME => /home/bachmeb
SHLVL => 3
GNOME_DESKTOP_SESSION_ID => this-is-deprecated
LOGNAME => bachmeb
QTLIB => /usr/lib64/qt-3.3/lib
CVS_RSH => ssh
DBUS_SESSION_BUS_ADDRESS => unix:abstract=/tmp/dbus-cmUHmSnmDC,guid=13255a5abbfc97ac2f5aeb4e00002308
LESSOPEN => ||/usr/bin/lesspipe.sh %s
DISPLAY => :2.0
G_BROKEN_FILENAMES => 1
COLORTERM => gnome-terminal
_ => /usr/bin/php
OLDPWD => /home/bachmeb/FocusWiki

PHP Variables

Variable => Value
_SERVER["ORBIT_SOCKETDIR"] => /tmp/orbit-bachmeb
_SERVER["VNCDESKTOP"] => 99700hlzx6g1:2 (bachmeb)
_SERVER["SSH_AGENT_PID"] => 5131
_SERVER["HOSTNAME"] => 99700hlzx6g1
_SERVER["GIO_LAUNCHED_DESKTOP_FILE_PID"] => 5301
_SERVER["TERM"] => xterm
_SERVER["SHELL"] => /bin/bash
_SERVER["HISTSIZE"] => 1000
_SERVER["XDG_SESSION_COOKIE"] => 75428f747188af479bb910fa0000001a-1463088293.813748-2046045595
_SERVER["GTK_RC_FILES"] => /etc/gtk/gtkrc:/home/bachmeb/.gtkrc-1.2-gnome2
_SERVER["WINDOWID"] => 35651587
_SERVER["SYSFONT"] => latarcyrheb-sun16
_SERVER["QTDIR"] => /usr/lib64/qt-3.3
_SERVER["QTINC"] => /usr/lib64/qt-3.3/include
_SERVER["USER"] => bachmeb
_SERVER["LS_COLORS"] => di=01;36:
_SERVER["GNOME_KEYRING_SOCKET"] => /tmp/keyring-7mzlGf/socket
_SERVER["SSH_AUTH_SOCK"] => /tmp/keyring-7mzlGf/socket.ssh
_SERVER["SESSION_MANAGER"] => local/unix:@/tmp/.ICE-unix/5130,unix/unix:/tmp/.ICE-unix/5130
_SERVER["GIO_LAUNCHED_DESKTOP_FILE"] => /usr/share/applications/gnome-terminal.desktop
_SERVER["PATH"] => /usr/lib64/qt-3.3/bin:/usr/local/bin:/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/sbin:/home/bachmeb/bin
_SERVER["MAIL"] => /var/spool/mail/bachmeb
_SERVER["PWD"] => /var/wiki/html
_SERVER["LANG"] => en_US.UTF-8
_SERVER["SSH_ASKPASS"] => /usr/libexec/openssh/gnome-ssh-askpass
_SERVER["HISTCONTROL"] => ignoredups
_SERVER["HOME"] => /home/bachmeb
_SERVER["SHLVL"] => 3
_SERVER["GNOME_DESKTOP_SESSION_ID"] => this-is-deprecated
_SERVER["LOGNAME"] => bachmeb
_SERVER["QTLIB"] => /usr/lib64/qt-3.3/lib
_SERVER["CVS_RSH"] => ssh
_SERVER["DBUS_SESSION_BUS_ADDRESS"] => unix:abstract=/tmp/dbus-cmUHmSnmDC,guid=13255a5abbfc97ac2f5aeb4e00002308
_SERVER["LESSOPEN"] => ||/usr/bin/lesspipe.sh %s
_SERVER["DISPLAY"] => :2.0
_SERVER["G_BROKEN_FILENAMES"] => 1
_SERVER["COLORTERM"] => gnome-terminal
_SERVER["_"] => /usr/bin/php
_SERVER["OLDPWD"] => /home/bachmeb/FocusWiki
_SERVER["PHP_SELF"] => 
_SERVER["SCRIPT_NAME"] => 
_SERVER["SCRIPT_FILENAME"] => 
_SERVER["PATH_TRANSLATED"] => 
_SERVER["DOCUMENT_ROOT"] => 
_SERVER["REQUEST_TIME"] => 1463148257
_SERVER["argv"] => Array
(
)

_SERVER["argc"] => 0

PHP License
This program is free software; you can redistribute it and/or modify
it under the terms of the PHP License as published by the PHP Group
and included in the distribution in the file:  LICENSE

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

If you did not receive a copy of the PHP license, or have any
questions about PHP licensing, please contact license@php.net.
[bachmeb@99700hlzx6g1 html]$ 

```

