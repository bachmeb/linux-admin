# git

## References
* https://www.digitalocean.com/community/tutorials/how-to-install-git-on-centos-7

##### Install gcc
* [gcc](/docs/common/gcc.md)

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
