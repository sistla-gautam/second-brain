```
before ./configure
aclocal.m4  bin  build-aux  config.h.in  configure  configure.ac  CONTRIBUTING  doc  Dockerfile  LICENSE  m4  Makefile.am  Makefile.in  NOTICE  README  src  util

after ./configure, before make
aclocal.m4  config.h.in    configure.ac  libtool   Makefile.am  src
bin         config.log     CONTRIBUTING  LICENSE   Makefile.in  stamp-h1
build-aux   config.status  doc           m4        NOTICE       util
config.h    configure      Dockerfile    Makefile  README


after make
aclocal.m4  config.h.in    configure.ac  libtool   Makefile.am  src
bin         config.log     CONTRIBUTING  LICENSE   Makefile.in  stamp-h1
build-aux   config.status  doc           m4        NOTICE       util
config.h    configure      Dockerfile    Makefile  README

```
---
before make
```
total 1348
drwxr-xr-x  8 nichesolv22 nichesolv22   4096 Sep 23 13:36 .
drwxr-xr-x  6 nichesolv22 nichesolv22   4096 Sep 23 13:36 ..
-rw-r--r--  1 nichesolv22 nichesolv22  56229 Mar 30 09:54 aclocal.m4
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 bin
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 build-aux
-rw-rw-r--  1 nichesolv22 nichesolv22   7145 Sep 23 13:36 config.h
-rw-r--r--  1 nichesolv22 nichesolv22   6624 Mar 30 09:54 config.h.in
-rw-rw-r--  1 nichesolv22 nichesolv22  85816 Sep 23 13:36 config.log
-rwxrwxr-x  1 nichesolv22 nichesolv22  66931 Sep 23 13:36 config.status
-rwxr-xr-x  1 nichesolv22 nichesolv22 604269 Mar 30 09:54 configure
-rw-r--r--  1 nichesolv22 nichesolv22  39429 Mar 30 09:17 configure.ac
-rw-r--r--  1 nichesolv22 nichesolv22   1984 Oct 21  2023 CONTRIBUTING
drwxr-xr-x  4 nichesolv22 nichesolv22   4096 Mar 30 09:56 doc
-rw-r--r--  1 nichesolv22 nichesolv22   6058 Mar 30 09:17 Dockerfile
-rw-r--r--  1 nichesolv22 nichesolv22    639 Jan 28  2024 .dockerignore
-rwxrwxr-x  1 nichesolv22 nichesolv22 348562 Sep 23 13:36 libtool
-rw-r--r--  1 nichesolv22 nichesolv22  11358 Oct 21  2023 LICENSE
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 m4
-rw-rw-r--  1 nichesolv22 nichesolv22  33036 Sep 23 13:36 Makefile
-rw-r--r--  1 nichesolv22 nichesolv22   2687 Jan 28  2024 Makefile.am
-rw-r--r--  1 nichesolv22 nichesolv22  31832 Mar 30 09:54 Makefile.in
-rw-r--r--  1 nichesolv22 nichesolv22    165 Oct 21  2023 NOTICE
-rw-r--r--  1 nichesolv22 nichesolv22   6108 Oct 21  2023 README
drwxr-xr-x 12 nichesolv22 nichesolv22   4096 Mar 30 09:56 src
-rw-rw-r--  1 nichesolv22 nichesolv22     23 Sep 23 13:36 stamp-h1
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 util

```

after make
```
total 1348
drwxr-xr-x  8 nichesolv22 nichesolv22   4096 Sep 23 13:36 .
drwxr-xr-x  6 nichesolv22 nichesolv22   4096 Sep 23 13:36 ..
-rw-r--r--  1 nichesolv22 nichesolv22  56229 Mar 30 09:54 aclocal.m4
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 bin
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 build-aux
-rw-rw-r--  1 nichesolv22 nichesolv22   7145 Sep 23 13:36 config.h
-rw-r--r--  1 nichesolv22 nichesolv22   6624 Mar 30 09:54 config.h.in
-rw-rw-r--  1 nichesolv22 nichesolv22  85816 Sep 23 13:36 config.log
-rwxrwxr-x  1 nichesolv22 nichesolv22  66931 Sep 23 13:36 config.status
-rwxr-xr-x  1 nichesolv22 nichesolv22 604269 Mar 30 09:54 configure
-rw-r--r--  1 nichesolv22 nichesolv22  39429 Mar 30 09:17 configure.ac
-rw-r--r--  1 nichesolv22 nichesolv22   1984 Oct 21  2023 CONTRIBUTING
drwxr-xr-x  4 nichesolv22 nichesolv22   4096 Mar 30 09:56 doc
-rw-r--r--  1 nichesolv22 nichesolv22   6058 Mar 30 09:17 Dockerfile
-rw-r--r--  1 nichesolv22 nichesolv22    639 Jan 28  2024 .dockerignore
-rwxrwxr-x  1 nichesolv22 nichesolv22 348562 Sep 23 13:36 libtool
-rw-r--r--  1 nichesolv22 nichesolv22  11358 Oct 21  2023 LICENSE
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 m4
-rw-rw-r--  1 nichesolv22 nichesolv22  33036 Sep 23 13:36 Makefile
-rw-r--r--  1 nichesolv22 nichesolv22   2687 Jan 28  2024 Makefile.am
-rw-r--r--  1 nichesolv22 nichesolv22  31832 Mar 30 09:54 Makefile.in
-rw-r--r--  1 nichesolv22 nichesolv22    165 Oct 21  2023 NOTICE
-rw-r--r--  1 nichesolv22 nichesolv22   6108 Oct 21  2023 README
drwxr-xr-x 12 nichesolv22 nichesolv22   4096 Mar 30 09:56 src
-rw-rw-r--  1 nichesolv22 nichesolv22     23 Sep 23 13:36 stamp-h1
drwxr-xr-x  2 nichesolv22 nichesolv22   4096 Mar 30 09:56 util

```