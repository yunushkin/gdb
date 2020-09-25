# Сборка GDB 9.2 с поддержкой python
1. Скачать Msys2-64
2. установить в Programm Files
3. создать директорию в /home/{login} (особенность ограничений)
4. установить mingw-w64
   pacman -S mingw-w64-x86_64-gcc
5. установить make
   pacman -Sy make
6???   pacman -S texinfo pacman -S libtool
6. export PATH=/mingw64/bin:$PATH
7. mkdir /home/User/gdb
8. cd /home/User/gdb
9. Конфигурирование (/home/User/gdb-9.2 - исходные файлы gdb должны отличаться от директории сборки(/home/User/gdb))
 
 
/home/User/gdb-9.2/configure --host=x86_64-w64-mingw32 --build=x86_64-amd-linux-gnu --target=x86_64-amd-linux-gnu --enable-interwork --enable-multilib                 --enable-target-optspace --with-float=soft --disable-werror --with-pkgversion="pulsar-gdb v1.0.0" --with-python

--prefix=${PREFIX} 

../binutils-gdb/configure --host=x86_64-w64-mingw32 --build=x86_64-amd-linux-gnu --target=x86_64-amd-linux-gnu \
                          --enable-interwork --enable-multilib \
                          --enable-target-optspace --with-float=soft --disable-werror \
                          --with-pkgversion="pulsar-gdb v1.0.0" --with-python
                          
                          
COLLECT_GCC=i686-w64-mingw32-g++-win32
COLLECT_LTO_WRAPPER=/usr/lib/gcc/i686-w64-mingw32/4.9-win32/lto-wrapper
Target: i686-w64-mingw32
Configured with: ../../src/configure --build=i586-linux-gnu
--prefix=/usr --includedir='/usr/include' --mandir='/usr/share/man'
--infodir='/usr/share/info' --sysconfdir=/etc --localstatedir=/var
--libexecdir='/usr/lib/gcc-mingw-w64' --disable-maintainer-mode
--disable-dependency-tracking --prefix=/usr --enable-shared
--enable-static --disable-multilib --with-system-zlib
--libexecdir=/usr/lib --without-included-gettext --libdir=/usr/lib
--enable-libstdcxx-time=yes --with-tune=generic
--enable-version-specific-runtime-libs --enable-fully-dynamic-string
--enable-libgomp --enable-languages=c,c++,fortran,objc,obj-c++
--enable-lto --with-plugin-ld --enable-threads=win32
--program-suffix=-win32 --program-prefix=i686-w64-mingw32-
--target=i686-w64-mingw32 --with-as=/usr/bin/i686-w64-mingw32-as
--with-ld=/usr/bin/i686-w64-mingw32-ld
Thread model: win32
