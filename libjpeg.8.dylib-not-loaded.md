# libjpeg.8.dylib not loaded

dyld: Library not loaded: /usr/local/lib/libjpeg.8.dylib - homebrew php

PHP was not working for me as I was encountering this libpng issue, so I reinstalled a new version with Homebrew.

However, I'm getting a similar error with libjpeg this time:

```bash
$ php -v
dyld: Library not loaded: /usr/local/lib/libjpeg.8.dylib
  Referenced from: /usr/local/bin/php
  Reason: image not found
Trace/BPT trap: 5
```

answer:

```bash
wget -c http://www.ijg.org/files/jpegsrc.v8d.tar.gz
tar xzf jpegsrc.v8d.tar.gz
cd jpeg-8d
./configure
make
cp ./.libs/libjpeg.8.dylib /usr/local/opt/jpeg/lib
```

@[stackoverflow](https://stackoverflow.com/questions/32703296/dyld-library-not-loaded-usr-local-lib-libjpeg-8-dylib-homebrew-php)

