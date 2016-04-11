# git

## References
* https://www.digitalocean.com/community/tutorials/how-to-install-git-on-centos-7
* http://stackoverflow.com/questions/8329485/git-clone-fatal-unable-to-find-remote-helper-for-https

### Install
##### Get a link to download git
* https://git-scm.com/
* https://www.kernel.org/pub/software/scm/git/

##### Download git
```
cd ~/Downloads
wget https://www.kernel.org/pub/software/scm/git/git-2.8.1.tar.gz
```

##### Extract the installation package
```
tar -xvf git-2.8.1.tar.gz
```

##### Install gcc
* [gcc](/docs/common/gcc.md)

##### Configure the installation
```
cd git-2.8.1
./configure
```
```c
/*
configure: Setting lib to 'lib' (the default)
configure: Will try -pthread then -lpthread to enable POSIX Threads.
configure: CHECKS for site configuration
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables...
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking for size_t... yes
checking for working alloca.h... yes
checking for alloca... yes
configure: CHECKS for programs
checking whether we are using the GNU C compiler... (cached) yes
checking whether gcc accepts -g... (cached) yes
checking for gcc option to accept ISO C89... (cached) none needed
checking for inline... inline
checking if linker supports -R... no
checking if linker supports -Wl,-rpath,... yes
checking for gar... no
checking for ar... ar
checking for gtar... gtar
checking for gnudiff... no
checking for gdiff... no
checking for diff... diff
checking for asciidoc... no
Using 'grep -a' for sane_grep
configure: CHECKS for libraries
checking for SHA1_Init in -lcrypto... no
checking for SHA1_Init in -lssl... no
checking for curl_global_init in -lcurl... no
checking for XML_ParserCreate in -lexpat... no
checking for iconv in -lc... yes
checking for deflateBound in -lz... no
checking for socket in -lc... yes
checking for inet_ntop... yes
checking for inet_pton... yes
checking for hstrerror... yes
checking for basename in -lc... yes
checking for gettext in -lc... yes
checking libintl.h usability... yes
checking libintl.h presence... yes
checking for libintl.h... yes
configure: CHECKS for header files
checking sys/select.h usability... yes
checking sys/select.h presence... yes
checking for sys/select.h... yes
checking sys/poll.h usability... yes
checking sys/poll.h presence... yes
checking for sys/poll.h... yes
checking for inttypes.h... (cached) yes
checking for old iconv()... no
configure: CHECKS for typedefs, structures, and compiler characteristics
checking for socklen_t... yes
checking for struct itimerval... yes
checking for struct stat.st_mtimespec.tv_nsec... no
checking for struct stat.st_mtim.tv_nsec... yes
checking for struct dirent.d_type... yes
checking for struct passwd.pw_gecos... yes
checking for struct sockaddr_storage... yes
checking for struct addrinfo... yes
checking for getaddrinfo... yes
checking for library containing getaddrinfo... none required
checking whether the platform regex can handle null bytes... yes
checking whether system succeeds to read fopen'ed directory... no
checking whether snprintf() and/or vsnprintf() return bogus value... no
checking whether the platform uses typical file type bits... yes
configure: CHECKS for library functions
checking libgen.h usability... yes
checking libgen.h presence... yes
checking for libgen.h... yes
checking paths.h usability... yes
checking paths.h presence... yes
checking for paths.h... yes
checking libcharset.h usability... no
checking libcharset.h presence... no
checking for libcharset.h... no
checking for strings.h... (cached) yes
checking for locale_charset in -liconv... no
checking for locale_charset in -lcharset... no
checking for HMAC_CTX_cleanup in -lcrypto... no
checking for clock_gettime... no
checking for CLOCK_MONOTONIC... yes
checking for setitimer... yes
checking for library containing setitimer... none required
checking for strcasestr... yes
checking for library containing strcasestr... none required
checking for memmem... yes
checking for library containing memmem... none required
checking for strlcpy... no
checking for uintmax_t... yes
checking for strtoumax... yes
checking for library containing strtoumax... none required
checking for setenv... yes
checking for library containing setenv... none required
checking for unsetenv... yes
checking for library containing unsetenv... none required
checking for mkdtemp... yes
checking for library containing mkdtemp... none required
checking for mkstemps... no
checking for initgroups... yes
checking for library containing initgroups... none required
checking for getdelim... yes
checking for library containing getdelim... none required
checking for BSD sysctl... no
checking for POSIX Threads with ''... no
checking for POSIX Threads with '-mt'... no
checking for POSIX Threads with '-pthread'... yes
configure: creating ./config.status
config.status: creating config.mak.autogen
config.status: executing config.mak.autogen commands
*/
```
##### Search yum for zlib
```
sudo yum search zlib
```
```c
/*
Loaded plugins: product-id, security, subscription-manager
================================ Matched: zlib =================================
perl-Archive-Tar.noarch : A module for Perl manipulation of .tar files
iptstate.x86_64 : A top-like display of IP Tables state table entries
jzlib.x86_64 : JZlib re-implementation of zlib in pure Java
jzlib-demo.x86_64 : Examples for jzlib
jzlib-javadoc.x86_64 : Javadoc for jzlib
minizip.i386 : Minizip manipulates files from a .zip archive
minizip.x86_64 : Minizip manipulates files from a .zip archive
minizip-devel.i386 : Development files for the minizip library
minizip-devel.x86_64 : Development files for the minizip library
perl-Compress-Zlib.x86_64 : A module providing Perl interfaces to the zlib
                          : compression library.
perl-IO-Zlib.noarch : Perl IO:: style interface to Compress::Zlib
zlib.i386 : The zlib compression and decompression library.
zlib.x86_64 : The zlib compression and decompression library.
zlib-devel.i386 : Header files and libraries for Zlib development.
zlib-devel.x86_64 : Header files and libraries for Zlib development.
*/
```

##### Install zlib-devel
```
sudo yum install zlib-devel
```
```c
/*
Loaded plugins: product-id, security, subscription-manager
Setting up Install Process
Resolving Dependencies
--> Running transaction check
---> Package zlib-devel.i386 0:1.2.3-7.el5 set to be updated
---> Package zlib-devel.x86_64 0:1.2.3-7.el5 set to be updated
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package          Arch         Version           Repository                Size
================================================================================
Installing:
 zlib-devel       i386         1.2.3-7.el5       rhel-5-server-rpms       102 k
 zlib-devel       x86_64       1.2.3-7.el5       rhel-5-server-rpms       103 k

Transaction Summary
================================================================================
Install       2 Package(s)
Upgrade       0 Package(s)

Total download size: 205 k
*/
```
```
Is this ok [y/N]: y
```
```c
/*
Downloading Packages:
(1/2): zlib-devel-1.2.3-7.el5.i386.rpm                   | 102 kB     00:00
(2/2): zlib-devel-1.2.3-7.el5.x86_64.rpm                 | 103 kB     00:00
--------------------------------------------------------------------------------
Total                                           169 kB/s | 205 kB     00:01
Running rpm_check_debug
Running Transaction Test
Finished Transaction Test
Transaction Test Succeeded
Running Transaction
  Installing     : zlib-devel                                               1/2
  Installing     : zlib-devel                                               2/2

Installed:
  zlib-devel.i386 0:1.2.3-7.el5         zlib-devel.x86_64 0:1.2.3-7.el5

Complete!
*/
```

##### Run make
```
make
```
```c
/*
    CC credential-store.o
    * new link flags
    CC abspath.o
    CC advice.o
    CC alias.o
    CC alloc.o
    CC archive.o
    CC archive-tar.o
    CC archive-zip.o
    CC argv-array.o
    * new prefix flags
    CC attr.o
    CC base85.o
    CC bisect.o
    CC blob.o
    CC branch.o
    CC bulk-checkin.o
    CC bundle.o
    CC cache-tree.o
    CC color.o
    CC column.o
    CC combine-diff.o
    CC commit.o
    CC compat/obstack.o
    CC compat/terminal.o
    CC config.o
    CC connect.o
    CC connected.o
    CC convert.o
    CC copy.o
    CC credential.o
    CC csum-file.o
    CC ctype.o
    CC date.o
    CC decorate.o
    CC diffcore-break.o
    CC diffcore-delta.o
    CC diffcore-order.o
    CC diffcore-pickaxe.o
    CC diffcore-rename.o
    CC diff-delta.o
    CC diff-lib.o
    CC diff-no-index.o
    CC diff.o
    CC dir.o
    CC editor.o
    CC entry.o
    CC environment.o
    CC ewah/bitmap.o
    CC ewah/ewah_bitmap.o
    CC ewah/ewah_io.o
    CC ewah/ewah_rlw.o
    CC exec_cmd.o
    CC fetch-pack.o
    CC fsck.o
    CC gettext.o
    CC gpg-interface.o
    CC graph.o
    CC grep.o
    CC hashmap.o
    GEN common-cmds.h
    CC help.o
    CC hex.o
    CC ident.o
    CC kwset.o
    CC levenshtein.o
    CC line-log.o
    CC line-range.o
    CC list-objects.o
    CC ll-merge.o
    CC lockfile.o
    CC log-tree.o
    CC mailinfo.o
    CC mailmap.o
    CC match-trees.o
    CC merge.o
    CC merge-blobs.o
    CC merge-recursive.o
    CC mergesort.o
    CC name-hash.o
    CC notes.o
    CC notes-cache.o
    CC notes-merge.o
    CC notes-utils.o
    CC object.o
    CC pack-bitmap.o
    CC pack-bitmap-write.o
    CC pack-check.o
    CC pack-objects.o
    CC pack-revindex.o
    CC pack-write.o
    CC pager.o
    CC parse-options.o
    CC parse-options-cb.o
    CC patch-delta.o
    CC patch-ids.o
    CC path.o
    CC pathspec.o
    CC pkt-line.o
    CC preload-index.o
    CC pretty.o
    CC prio-queue.o
    CC progress.o
    CC prompt.o
    CC quote.o
    CC reachable.o
    CC read-cache.o
    CC reflog-walk.o
    CC refs.o
    CC refs/files-backend.o
    CC ref-filter.o
    CC remote.o
    CC replace_object.o
    CC rerere.o
    CC resolve-undo.o
    CC revision.o
    CC run-command.o
    CC send-pack.o
    CC sequencer.o
    CC server-info.o
    CC setup.o
    CC sha1-array.o
    CC sha1-lookup.o
    CC sha1_file.o
    CC sha1_name.o
    CC shallow.o
    CC sideband.o
    CC sigchain.o
    CC split-index.o
    CC strbuf.o
    CC streaming.o
    CC string-list.o
    CC submodule.o
    CC submodule-config.o
    CC symlinks.o
    CC tag.o
    CC tempfile.o
    CC trace.o
    CC trailer.o
    CC transport.o
    CC transport-helper.o
    CC tree-diff.o
    CC tree.o
    CC tree-walk.o
    CC unpack-trees.o
    CC url.o
    CC urlmatch.o
    CC usage.o
    CC userdiff.o
    CC utf8.o
    CC varint.o
    CC version.o
    CC versioncmp.o
    CC walker.o
    CC wildmatch.o
    CC worktree.o
    CC wrapper.o
    CC write_or_die.o
    CC ws.o
    CC wt-status.o
    CC xdiff-interface.o
    CC zlib.o
    CC unix-socket.o
    CC block-sha1/sha1.o
    CC thread-utils.o
    CC compat/strlcpy.o
    AR libgit.a
    CC xdiff/xdiffi.o
    CC xdiff/xprepare.o
    CC xdiff/xutils.o
    CC xdiff/xemit.o
    CC xdiff/xmerge.o
    CC xdiff/xpatience.o
    CC xdiff/xhistogram.o
    AR xdiff/lib.a
    LINK git-credential-store
    CC daemon.o
    LINK git-daemon
    CC fast-import.o
    LINK git-fast-import
    CC http-backend.o
    LINK git-http-backend
    CC imap-send.o
    LINK git-imap-send
    CC sh-i18n--envsubst.o
    LINK git-sh-i18n--envsubst
    CC shell.o
    LINK git-shell
    CC show-index.o
    LINK git-show-index
    CC upload-pack.o
    LINK git-upload-pack
    CC remote-testsvn.o
    CC vcs-svn/line_buffer.o
    CC vcs-svn/sliding_window.o
    CC vcs-svn/repo_tree.o
    CC vcs-svn/fast_export.o
    CC vcs-svn/svndiff.o
    CC vcs-svn/svndump.o
    AR vcs-svn/lib.a
    LINK git-remote-testsvn
    CC credential-cache.o
    LINK git-credential-cache
    CC credential-cache--daemon.o
    LINK git-credential-cache--daemon
    * new script parameters
    GEN git-bisect
    GEN git-difftool--helper
    GEN git-filter-branch
    GEN git-merge-octopus
    GEN git-merge-one-file
    GEN git-merge-resolve
    GEN git-mergetool
    GEN git-quiltimport
    GEN git-rebase
    GEN git-request-pull
    GEN git-stash
    GEN git-submodule
    GEN git-web--browse
    SUBDIR perl
/usr/bin/perl Makefile.PL PREFIX='/usr/local' INSTALL_BASE='' --localedir='/usr/local/share/locale'
'INSTALL_BASE' is not a known MakeMaker parameter name.
Writing perl.mak for Git
    * new perl-specific parameters
    GEN git-add--interactive
    GEN git-difftool
    GEN git-archimport
    GEN git-cvsexportcommit
    GEN git-cvsimport
    GEN git-cvsserver
    GEN git-relink
    GEN git-send-email
    GEN git-svn
    * new Python interpreter location
    GEN git-p4
    GEN git-instaweb
    GEN git-mergetool--lib
    GEN git-parse-remote
    GEN git-rebase--am
    GEN git-rebase--interactive
    GEN git-rebase--merge
    GEN git-sh-setup
    GEN git-sh-i18n
    CC git.o
    CC builtin/add.o
    CC builtin/am.o
    CC builtin/annotate.o
    CC builtin/apply.o
    CC builtin/archive.o
    CC builtin/bisect--helper.o
    CC builtin/blame.o
    CC builtin/branch.o
    CC builtin/bundle.o
    CC builtin/cat-file.o
    CC builtin/check-attr.o
    CC builtin/check-ignore.o
    CC builtin/check-mailmap.o
    CC builtin/check-ref-format.o
    CC builtin/checkout-index.o
    CC builtin/checkout.o
    CC builtin/clean.o
    CC builtin/clone.o
    CC builtin/column.o
    CC builtin/commit-tree.o
    CC builtin/commit.o
    CC builtin/config.o
    CC builtin/count-objects.o
    CC builtin/credential.o
    CC builtin/describe.o
    CC builtin/diff-files.o
    CC builtin/diff-index.o
    CC builtin/diff-tree.o
    CC builtin/diff.o
    CC builtin/fast-export.o
    CC builtin/fetch-pack.o
    CC builtin/fetch.o
    CC builtin/fmt-merge-msg.o
    CC builtin/for-each-ref.o
    CC builtin/fsck.o
    CC builtin/gc.o
    CC builtin/get-tar-commit-id.o
    CC builtin/grep.o
    CC builtin/hash-object.o
    CC builtin/help.o
    CC builtin/index-pack.o
    CC builtin/init-db.o
    CC builtin/interpret-trailers.o
    CC builtin/log.o
    CC builtin/ls-files.o
    CC builtin/ls-remote.o
    CC builtin/ls-tree.o
    CC builtin/mailinfo.o
    CC builtin/mailsplit.o
    CC builtin/merge.o
    CC builtin/merge-base.o
    CC builtin/merge-file.o
    CC builtin/merge-index.o
    CC builtin/merge-ours.o
    CC builtin/merge-recursive.o
    CC builtin/merge-tree.o
    CC builtin/mktag.o
    CC builtin/mktree.o
    CC builtin/mv.o
    CC builtin/name-rev.o
    CC builtin/notes.o
    CC builtin/pack-objects.o
    CC builtin/pack-redundant.o
    CC builtin/pack-refs.o
    CC builtin/patch-id.o
    CC builtin/prune-packed.o
    CC builtin/prune.o
    CC builtin/pull.o
    CC builtin/push.o
    CC builtin/read-tree.o
    CC builtin/receive-pack.o
    CC builtin/reflog.o
    CC builtin/remote.o
    CC builtin/remote-ext.o
    CC builtin/remote-fd.o
    CC builtin/repack.o
    CC builtin/replace.o
    CC builtin/rerere.o
    CC builtin/reset.o
    CC builtin/rev-list.o
    CC builtin/rev-parse.o
    CC builtin/revert.o
    CC builtin/rm.o
    CC builtin/send-pack.o
    CC builtin/shortlog.o
    CC builtin/show-branch.o
    CC builtin/show-ref.o
    CC builtin/stripspace.o
    CC builtin/submodule--helper.o
    CC builtin/symbolic-ref.o
    CC builtin/tag.o
    CC builtin/unpack-file.o
    CC builtin/unpack-objects.o
    CC builtin/update-index.o
    CC builtin/update-ref.o
    CC builtin/update-server-info.o
    CC builtin/upload-archive.o
    CC builtin/var.o
    CC builtin/verify-commit.o
    CC builtin/verify-pack.o
    CC builtin/verify-tag.o
    CC builtin/worktree.o
    CC builtin/write-tree.o
    LINK git
    BUILTIN git-add
    BUILTIN git-am
    BUILTIN git-annotate
    BUILTIN git-apply
    BUILTIN git-archive
    BUILTIN git-bisect--helper
    BUILTIN git-blame
    BUILTIN git-branch
    BUILTIN git-bundle
    BUILTIN git-cat-file
    BUILTIN git-check-attr
    BUILTIN git-check-ignore
    BUILTIN git-check-mailmap
    BUILTIN git-check-ref-format
    BUILTIN git-checkout-index
    BUILTIN git-checkout
    BUILTIN git-clean
    BUILTIN git-clone
    BUILTIN git-column
    BUILTIN git-commit-tree
    BUILTIN git-commit
    BUILTIN git-config
    BUILTIN git-count-objects
    BUILTIN git-credential
    BUILTIN git-describe
    BUILTIN git-diff-files
    BUILTIN git-diff-index
    BUILTIN git-diff-tree
    BUILTIN git-diff
    BUILTIN git-fast-export
    BUILTIN git-fetch-pack
    BUILTIN git-fetch
    BUILTIN git-fmt-merge-msg
    BUILTIN git-for-each-ref
    BUILTIN git-fsck
    BUILTIN git-gc
    BUILTIN git-get-tar-commit-id
    BUILTIN git-grep
    BUILTIN git-hash-object
    BUILTIN git-help
    BUILTIN git-index-pack
    BUILTIN git-init-db
    BUILTIN git-interpret-trailers
    BUILTIN git-log
    BUILTIN git-ls-files
    BUILTIN git-ls-remote
    BUILTIN git-ls-tree
    BUILTIN git-mailinfo
    BUILTIN git-mailsplit
    BUILTIN git-merge
    BUILTIN git-merge-base
    BUILTIN git-merge-file
    BUILTIN git-merge-index
    BUILTIN git-merge-ours
    BUILTIN git-merge-recursive
    BUILTIN git-merge-tree
    BUILTIN git-mktag
    BUILTIN git-mktree
    BUILTIN git-mv
    BUILTIN git-name-rev
    BUILTIN git-notes
    BUILTIN git-pack-objects
    BUILTIN git-pack-redundant
    BUILTIN git-pack-refs
    BUILTIN git-patch-id
    BUILTIN git-prune-packed
    BUILTIN git-prune
    BUILTIN git-pull
    BUILTIN git-push
    BUILTIN git-read-tree
    BUILTIN git-receive-pack
    BUILTIN git-reflog
    BUILTIN git-remote
    BUILTIN git-remote-ext
    BUILTIN git-remote-fd
    BUILTIN git-repack
    BUILTIN git-replace
    BUILTIN git-rerere
    BUILTIN git-reset
    BUILTIN git-rev-list
    BUILTIN git-rev-parse
    BUILTIN git-revert
    BUILTIN git-rm
    BUILTIN git-send-pack
    BUILTIN git-shortlog
    BUILTIN git-show-branch
    BUILTIN git-show-ref
    BUILTIN git-stripspace
    BUILTIN git-submodule--helper
    BUILTIN git-symbolic-ref
    BUILTIN git-tag
    BUILTIN git-unpack-file
    BUILTIN git-unpack-objects
    BUILTIN git-update-index
    BUILTIN git-update-ref
    BUILTIN git-update-server-info
    BUILTIN git-upload-archive
    BUILTIN git-var
    BUILTIN git-verify-commit
    BUILTIN git-verify-pack
    BUILTIN git-verify-tag
    BUILTIN git-worktree
    BUILTIN git-write-tree
    BUILTIN git-cherry
    BUILTIN git-cherry-pick
    BUILTIN git-format-patch
    BUILTIN git-fsck-objects
    BUILTIN git-init
    BUILTIN git-merge-subtree
    BUILTIN git-show
    BUILTIN git-stage
    BUILTIN git-status
    BUILTIN git-whatchanged
    SUBDIR git-gui
GITGUI_VERSION = 0.20.GITGUI
    * new locations or Tcl/Tk interpreter
    GEN git-gui
    INDEX lib/
    MSGFMT    po/bg.msg 547 translated.
    MSGFMT    po/de.msg 520 translated.
    MSGFMT    po/el.msg 381 translated, 4 fuzzy, 6 untranslated.
    MSGFMT    po/fr.msg 520 translated.
    MSGFMT    po/hu.msg 514 translated.
    MSGFMT    po/it.msg 519 translated, 1 untranslated.
    MSGFMT    po/ja.msg 520 translated.
    MSGFMT    po/nb.msg 474 translated, 39 untranslated.
    MSGFMT po/pt_br.msg 520 translated.
    MSGFMT    po/ru.msg 516 translated, 4 untranslated.
    MSGFMT    po/sv.msg 547 translated.
    MSGFMT    po/vi.msg 543 translated.
    MSGFMT po/zh_cn.msg 366 translated, 7 fuzzy, 17 untranslated.
    SUBDIR gitk-git
    * new Tcl/Tk interpreter location
    GEN gitk-wish
Generating catalog po/bg.msg
msgfmt --statistics --tcl po/bg.po -l bg -d po/
311 translated messages.
Generating catalog po/ca.msg
msgfmt --statistics --tcl po/ca.po -l ca -d po/
307 translated messages.
Generating catalog po/de.msg
msgfmt --statistics --tcl po/de.po -l de -d po/
307 translated messages.
Generating catalog po/es.msg
msgfmt --statistics --tcl po/es.po -l es -d po/
184 translated messages, 46 fuzzy translations, 77 untranslated messages.
Generating catalog po/fr.msg
msgfmt --statistics --tcl po/fr.po -l fr -d po/
311 translated messages.
Generating catalog po/hu.msg
msgfmt --statistics --tcl po/hu.po -l hu -d po/
277 translated messages, 18 fuzzy translations, 12 untranslated messages.
Generating catalog po/it.msg
msgfmt --statistics --tcl po/it.po -l it -d po/
274 translated messages, 17 fuzzy translations, 16 untranslated messages.
Generating catalog po/ja.msg
msgfmt --statistics --tcl po/ja.po -l ja -d po/
311 translated messages.
Generating catalog po/pt_br.msg
msgfmt --statistics --tcl po/pt_br.po -l pt_br -d po/
279 translated messages, 16 fuzzy translations, 12 untranslated messages.
Generating catalog po/ru.msg
msgfmt --statistics --tcl po/ru.po -l ru -d po/
307 translated messages.
Generating catalog po/sv.msg
msgfmt --statistics --tcl po/sv.po -l sv -d po/
311 translated messages.
Generating catalog po/vi.msg
msgfmt --statistics --tcl po/vi.po -l vi -d po/
307 translated messages.
    SUBDIR perl
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <private-Error.pm >blib/lib/Error.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Migration.pm >blib/lib/Git/SVN/Migration.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Editor.pm >blib/lib/Git/SVN/Editor.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Log.pm >blib/lib/Git/SVN/Log.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN.pm >blib/lib/Git/SVN.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Memoize/YAML.pm >blib/lib/Git/SVN/Memoize/YAML.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Ra.pm >blib/lib/Git/SVN/Ra.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/I18N.pm >blib/lib/Git/I18N.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Prompt.pm >blib/lib/Git/SVN/Prompt.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/GlobSpec.pm >blib/lib/Git/SVN/GlobSpec.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Fetcher.pm >blib/lib/Git/SVN/Fetcher.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/SVN/Utils.pm >blib/lib/Git/SVN/Utils.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git/IndexInfo.pm >blib/lib/Git/IndexInfo.pm
/usr/bin/perl -pe "s<\Q++LOCALEDIR++\E></usr/local/share/locale>" <Git.pm >blib/lib/Git.pm
Manifying blib/man3/private-Error.3pm
Manifying blib/man3/Git::SVN::Editor.3pm
Manifying blib/man3/Git::SVN::Memoize::YAML.3pm
Manifying blib/man3/Git::SVN::Ra.3pm
Manifying blib/man3/Git::I18N.3pm
Manifying blib/man3/Git::SVN::Prompt.3pm
Manifying blib/man3/Git::SVN::Fetcher.3pm
Manifying blib/man3/Git::SVN::Utils.3pm
Manifying blib/man3/Git.3pm
    SUBDIR templates
    MSGFMT po/build/locale/bg/LC_MESSAGES/git.mo
2477 translated messages.
    MSGFMT po/build/locale/ca/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/de/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/fr/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/is/LC_MESSAGES/git.mo
14 translated messages.
    MSGFMT po/build/locale/it/LC_MESSAGES/git.mo
716 translated messages, 350 untranslated messages.
    MSGFMT po/build/locale/ko/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/pt_PT/LC_MESSAGES/git.mo
2521 translated messages, 5 fuzzy translations, 4 untranslated messages.
    MSGFMT po/build/locale/ru/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/sv/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/vi/LC_MESSAGES/git.mo
2530 translated messages.
    MSGFMT po/build/locale/zh_CN/LC_MESSAGES/git.mo
2530 translated messages.
    CC test-chmtime.o
    LINK test-chmtime
    CC test-ctype.o
    LINK test-ctype
    CC test-config.o
    LINK test-config
    CC test-date.o
    LINK test-date
    CC test-delta.o
    LINK test-delta
    CC test-dump-cache-tree.o
    LINK test-dump-cache-tree
    CC test-dump-split-index.o
    LINK test-dump-split-index
    CC test-dump-untracked-cache.o
    LINK test-dump-untracked-cache
    CC test-fake-ssh.o
    LINK test-fake-ssh
    CC test-genrandom.o
    LINK test-genrandom
    CC test-hashmap.o
    LINK test-hashmap
    CC test-index-version.o
    LINK test-index-version
    CC test-line-buffer.o
    LINK test-line-buffer
    CC test-match-trees.o
    LINK test-match-trees
    CC test-mergesort.o
    LINK test-mergesort
    CC test-mktemp.o
    LINK test-mktemp
    CC test-parse-options.o
    LINK test-parse-options
    CC test-path-utils.o
    LINK test-path-utils
    CC test-prio-queue.o
    LINK test-prio-queue
    CC test-read-cache.o
    LINK test-read-cache
    CC test-regex.o
    LINK test-regex
    CC test-revision-walking.o
    LINK test-revision-walking
    CC test-run-command.o
    LINK test-run-command
    CC test-scrap-cache-tree.o
    LINK test-scrap-cache-tree
    CC test-sha1.o
    LINK test-sha1
    CC test-sha1-array.o
    LINK test-sha1-array
    CC test-sigchain.o
    LINK test-sigchain
    CC test-string-list.o
    LINK test-string-list
    CC test-submodule-config.o
    LINK test-submodule-config
    CC test-subprocess.o
    LINK test-subprocess
    CC test-svn-fe.o
    LINK test-svn-fe
    CC test-urlmatch-normalization.o
    LINK test-urlmatch-normalization
    CC test-wildmatch.o
    LINK test-wildmatch
    GEN bin-wrappers/git
    GEN bin-wrappers/git-upload-pack
    GEN bin-wrappers/git-receive-pack
    GEN bin-wrappers/git-upload-archive
    GEN bin-wrappers/git-shell
    GEN bin-wrappers/git-cvsserver
    GEN bin-wrappers/test-chmtime
    GEN bin-wrappers/test-ctype
    GEN bin-wrappers/test-config
    GEN bin-wrappers/test-date
    GEN bin-wrappers/test-delta
    GEN bin-wrappers/test-dump-cache-tree
    GEN bin-wrappers/test-dump-split-index
    GEN bin-wrappers/test-dump-untracked-cache
    GEN bin-wrappers/test-fake-ssh
    GEN bin-wrappers/test-genrandom
    GEN bin-wrappers/test-hashmap
    GEN bin-wrappers/test-index-version
    GEN bin-wrappers/test-line-buffer
    GEN bin-wrappers/test-match-trees
    GEN bin-wrappers/test-mergesort
    GEN bin-wrappers/test-mktemp
    GEN bin-wrappers/test-parse-options
    GEN bin-wrappers/test-path-utils
    GEN bin-wrappers/test-prio-queue
    GEN bin-wrappers/test-read-cache
    GEN bin-wrappers/test-regex
    GEN bin-wrappers/test-revision-walking
    GEN bin-wrappers/test-run-command
    GEN bin-wrappers/test-scrap-cache-tree
    GEN bin-wrappers/test-sha1
    GEN bin-wrappers/test-sha1-array
    GEN bin-wrappers/test-sigchain
    GEN bin-wrappers/test-string-list
    GEN bin-wrappers/test-submodule-config
    GEN bin-wrappers/test-subprocess
    GEN bin-wrappers/test-svn-fe
    GEN bin-wrappers/test-urlmatch-normalization
    GEN bin-wrappers/test-wildmatch
    GEN git-remote-testgit
*/
```

##### Install git
```
sudo make install
```
```c
    SUBDIR git-gui
    SUBDIR gitk-git
    SUBDIR perl
    SUBDIR templates
install -d -m 755 '/usr/local/bin'
install -d -m 755 '/usr/local/libexec/git-core'
install   git-credential-store git-daemon git-fast-import git-http-backend git-imap-send git-sh-i18n--envsubst git-shell git-show-index git-upload-pack git-remote-testsvn git-credential-cache git-credential-cache--daemon git-bisect git-difftool--helper git-filter-branch git-merge-octopus git-merge-one-file git-merge-resolve git-mergetool git-quiltimport git-rebase git-request-pull git-stash git-submodule git-web--browse git-add--interactive git-difftool git-archimport git-cvsexportcommit git-cvsimport git-cvsserver git-relink git-send-email git-svn git-p4 git-instaweb '/usr/local/libexec/git-core'
install -m 644  git-mergetool--lib git-parse-remote git-rebase--am git-rebase--interactive git-rebase--merge git-sh-setup git-sh-i18n '/usr/local/libexec/git-core'
install git git-upload-pack git-receive-pack git-upload-archive git-shell git-cvsserver '/usr/local/bin'
make -C templates DESTDIR='' install
make[1]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/templates'
install -d -m 755 '/usr/local/share/git-core/templates'
(cd blt && gtar cf - .) | \
        (cd '/usr/local/share/git-core/templates' && umask 022 && gtar xof -)
make[1]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/templates'
install -d -m 755 '/usr/local/libexec/git-core/mergetools'
install -m 644 mergetools/* '/usr/local/libexec/git-core/mergetools'
install -d -m 755 '/usr/local/share/locale'
(cd po/build/locale && gtar cf - .) | \
        (cd '/usr/local/share/locale' && umask 022 && gtar xof -)
make -C perl prefix='/usr/local' DESTDIR='' install
make[1]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/perl'
make[2]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/perl'
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Error.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/IndexInfo.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/I18N.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Prompt.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Migration.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Editor.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/GlobSpec.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Log.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Utils.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Ra.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Fetcher.pm
Installing /usr/local/lib/perl5/site_perl/5.8.8/Git/SVN/Memoize/YAML.pm
Installing /usr/local/share/man/man3/Git::SVN::Fetcher.3pm
Installing /usr/local/share/man/man3/Git::SVN::Prompt.3pm
Installing /usr/local/share/man/man3/private-Error.3pm
Installing /usr/local/share/man/man3/Git.3pm
Installing /usr/local/share/man/man3/Git::SVN::Editor.3pm
Installing /usr/local/share/man/man3/Git::SVN::Utils.3pm
Installing /usr/local/share/man/man3/Git::SVN::Ra.3pm
Installing /usr/local/share/man/man3/Git::SVN::Memoize::YAML.3pm
Installing /usr/local/share/man/man3/Git::I18N.3pm
Writing /usr/local/lib64/perl5/site_perl/5.8.8/x86_64-linux-thread-multi/auto/Git/.packlist
Appending installation info to /usr/local/lib64/perl5/5.8.8/x86_64-linux-thread-multi/perllocal.pod
make[2]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/perl'
make[1]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/perl'
make -C gitweb install
make[1]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/gitweb'
make[2]: Entering directory `/home/bachmeb/Downloads/git-2.8.1'
make[2]: `GIT-VERSION-FILE' is up to date.
make[2]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1'
    GEN gitweb.cgi
    GEN static/gitweb.js
install -d -m 755 '/usr/local/share/gitweb'
install -m 755 gitweb.cgi '/usr/local/share/gitweb'
install -d -m 755 '/usr/local/share/gitweb/static'
install -m 644 static/gitweb.js static/gitweb.css static/git-logo.png static/git-favicon.png '/usr/local/share/gitweb/static'
make[1]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/gitweb'
make -C gitk-git install
make[1]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/gitk-git'
install -m 755 gitk-wish '/usr/local/bin'/gitk
install -d -m 755 '/usr/local/share/gitk/lib/msgs'
install -m 644 po/bg.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/ca.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/de.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/es.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/fr.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/hu.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/it.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/ja.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/pt_br.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/ru.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/sv.msg '/usr/local/share/gitk/lib/msgs' &&  install -m 644 po/vi.msg '/usr/local/share/gitk/lib/msgs' && true
make[1]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/gitk-git'
make -C git-gui gitexecdir='/usr/local/libexec/git-core' install
make[1]: Entering directory `/home/bachmeb/Downloads/git-2.8.1/git-gui'
  DEST /usr/local/libexec/git-core
    INSTALL 755 git-gui
    INSTALL 755 git-gui--askpass
    LINK        git-citool -> git-gui
  DEST /usr/local/share/git-gui/lib
    INSTALL 644 tclIndex
    INSTALL 644 about.tcl
    INSTALL 644 blame.tcl
    INSTALL 644 branch_checkout.tcl
    INSTALL 644 branch_create.tcl
    INSTALL 644 branch_delete.tcl
    INSTALL 644 branch_rename.tcl
    INSTALL 644 branch.tcl
    INSTALL 644 browser.tcl
    INSTALL 644 checkout_op.tcl
    INSTALL 644 choose_font.tcl
    INSTALL 644 choose_repository.tcl
    INSTALL 644 choose_rev.tcl
    INSTALL 644 class.tcl
    INSTALL 644 commit.tcl
    INSTALL 644 console.tcl
    INSTALL 644 database.tcl
    INSTALL 644 date.tcl
    INSTALL 644 diff.tcl
    INSTALL 644 encoding.tcl
    INSTALL 644 error.tcl
    INSTALL 644 index.tcl
    INSTALL 644 line.tcl
    INSTALL 644 logo.tcl
    INSTALL 644 merge.tcl
    INSTALL 644 mergetool.tcl
    INSTALL 644 option.tcl
    INSTALL 644 remote_add.tcl
    INSTALL 644 remote_branch_delete.tcl
    INSTALL 644 remote.tcl
    INSTALL 644 search.tcl
    INSTALL 644 shortcut.tcl
    INSTALL 644 spellcheck.tcl
    INSTALL 644 sshkey.tcl
    INSTALL 644 status_bar.tcl
    INSTALL 644 themed.tcl
    INSTALL 644 tools_dlg.tcl
    INSTALL 644 tools.tcl
    INSTALL 644 transport.tcl
    INSTALL 644 win32.tcl
    INSTALL 644 git-gui.ico
    INSTALL 644 win32_shortcut.js
  DEST /usr/local/share/git-gui/lib/msgs
    INSTALL 644 bg.msg
    INSTALL 644 de.msg
    INSTALL 644 el.msg
    INSTALL 644 fr.msg
    INSTALL 644 hu.msg
    INSTALL 644 it.msg
    INSTALL 644 ja.msg
    INSTALL 644 nb.msg
    INSTALL 644 pt_br.msg
    INSTALL 644 ru.msg
    INSTALL 644 sv.msg
    INSTALL 644 vi.msg
    INSTALL 644 zh_cn.msg
make[1]: Leaving directory `/home/bachmeb/Downloads/git-2.8.1/git-gui'
bindir=$(cd '/usr/local/bin' && pwd) && \
        execdir=$(cd '/usr/local/libexec/git-core' && pwd) && \
        { test "$bindir/" = "$execdir/" || \
          for p in git git-shell git-upload-pack git-cvsserver; do \
                rm -f "$execdir/$p" && \
                test -z "" && \
                ln "$bindir/$p" "$execdir/$p" 2>/dev/null || \
                cp "$bindir/$p" "$execdir/$p" || exit; \
          done; \
        } && \
        for p in git-receive-pack git-upload-archive; do \
                rm -f "$bindir/$p" && \
                test -z "" && \
                ln "$bindir/git" "$bindir/$p" 2>/dev/null || \
                ln -s "git" "$bindir/$p" 2>/dev/null || \
                cp "$bindir/git" "$bindir/$p" || exit; \
        done && \
        for p in  git-add git-am git-annotate git-apply git-archive git-bisect--helper git-blame git-branch git-bundle git-cat-file git-check-attr git-check-ignore git-check-mailmap git-check-ref-format git-checkout-index git-checkout git-clean git-clone git-column git-commit-tree git-commit git-config git-count-objects git-credential git-describe git-diff-files git-diff-index git-diff-tree git-diff git-fast-export git-fetch-pack git-fetch git-fmt-merge-msg git-for-each-ref git-fsck git-gc git-get-tar-commit-id git-grep git-hash-object git-help git-index-pack git-init-db git-interpret-trailers git-log git-ls-files git-ls-remote git-ls-tree git-mailinfo git-mailsplit git-merge git-merge-base git-merge-file git-merge-index git-merge-ours git-merge-recursive git-merge-tree git-mktag git-mktree git-mv git-name-rev git-notes git-pack-objects git-pack-redundant git-pack-refs git-patch-id git-prune-packed git-prune git-pull git-push git-read-tree git-receive-pack git-reflog git-remote git-remote-ext git-remote-fd git-repack git-replace git-rerere git-reset git-rev-list git-rev-parse git-revert git-rm git-send-pack git-shortlog git-show-branch git-show-ref git-stripspace git-submodule--helper git-symbolic-ref git-tag git-unpack-file git-unpack-objects git-update-index git-update-ref git-update-server-info git-upload-archive git-var git-verify-commit git-verify-pack git-verify-tag git-worktree git-write-tree git-cherry git-cherry-pick git-format-patch git-fsck-objects git-init git-merge-subtree git-show git-stage git-status git-whatchanged; do \
                rm -f "$execdir/$p" && \
                test -z "" && \
                ln "$execdir/git" "$execdir/$p" 2>/dev/null || \
                ln -s "git" "$execdir/$p" 2>/dev/null || \
                cp "$execdir/git" "$execdir/$p" || exit; \
        done && \
        remote_curl_aliases="" && \
        for p in $remote_curl_aliases; do \
                rm -f "$execdir/$p" && \
                test -z "" && \
                ln "$execdir/git-remote-http" "$execdir/$p" 2>/dev/null || \
                ln -s "git-remote-http" "$execdir/$p" 2>/dev/null || \
                cp "$execdir/git-remote-http" "$execdir/$p" || exit; \
        done && \
        ./check_bindir "z$bindir" "z$execdir" "$bindir/git-add"
```

##### See where git was installed
```
whereis git
```
```c
/*
git: /usr/local/bin/git
*/
```

##### Check the git version
```
git --version
```
```c
/*
git version 2.8.1
*/
```

### Configure
```
git config -l
```
```
git config user.email [YOUR EMAIL ADDRESS]
git config user.name [YOUR USER NAME]
```
```
git remote add origin http://github.com/[username]/[repo].git
```
```
git remote -v
```
```
git pull origin master
```
```
git branch --set-upstream-to=origin/master master
```
