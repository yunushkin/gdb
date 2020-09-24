# Сборка GDB с поддержкой python
export TARGET=x86_64-amd-linux-gnu
export PREFIX=/opt/mytoolchain
export HOST=x86_64-w64-mingw32
export BUILD=x86_64-amd-linux-gnu
export PKGVERSION="test v1.0.0"


../binutils-gdb/configure --host=${HOST} --build=${BUILD} --target=${TARGET} \
                          --prefix=${PREFIX} --enable-interwork --enable-multilib \
                          --enable-target-optspace --with-float=soft --disable-werror \
                          --with-pkgversion=${PKGVERSION} --with-python
