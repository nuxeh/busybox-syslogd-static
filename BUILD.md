# Static busybox binary

To regenerate the `busybox` binary in this repository:

    sudo apt-get install gcc-aarch64-linux-gnu

    git clone git://git.musl-libc.org/musl
    git clone git://busybox.net/busybox.git

    cd musl
    CROSS_COMPILE=aarch64-linux-gnu- ./configure --disable-shared --prefix=$(pwd -P)/out
    make
    make install
    cd ..

    cp ts002_defconfig busybox/configs

    cd busybox
    CROSS_COMPILE=aarch64-linux-gnu- make ts002_defconfig
    CROSS_COMPILE=aarch64-linux-gnu- make

Notes:

 - The busybox configuration is copied from this repository
