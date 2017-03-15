# cvc4

./configure  --enable-language-bindings=python --with-antlr-dir=/home/ronghai/CVC4/antlr-3.4 ANTLR=/home/ronghai/CVC4/antlr-3.4/bin/antlr3


After follow to install cvc on Ubuntu, it reports 
```
root@z3:~/CVC4/builds/i686-pc-linux-gnu/production# cvc4
cvc4: error while loading shared libraries: libcvc4parser.so.3: cannot open shared object file: No such file or directory 
```

The solution is as follows:
```
root@z3:~/CVC4/builds/i686-pc-linux-gnu/production# ln -s lib/libcvc4parser.so.3 /usr/lib/libcvc4parser.so.3
root@z3:~/CVC4/builds/i686-pc-linux-gnu/production# ls /usr/lib/lib*
/usr/lib/libbfd-2.24-system.so  /usr/lib/libcvc4parser.so.3  /usr/lib/libopcodes-2.24-system.so
root@z3:~/CVC4/builds/i686-pc-linux-gnu/production# sudo ldconfig
```
Now cvc works.
```
root@z3:~/CVC4/builds/i686-pc-linux-gnu/production# cvc4
cvc4 1.5-prerelease [git master e5f3b5e6 (with modifications)] assertions:off
CVC4> ^CCVC4 interrupted by user
```

The next step is to build python binding.

