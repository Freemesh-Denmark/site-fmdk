Doku: https://gluon.readthedocs.org/en/v2016.2/user/site.html

Gluon version used for this build:

Gluon 2016.2

Added Packages:
	- USB-auto-mount

Build
-----
You can easily create your own experimental build with these commands:

    sudo apt-get install git make gcc g++ unzip libncurses5-dev zlib1g-dev subversion gawk bzip2 libssl-dev
    git clone https://github.com/freifunk-gluon/gluon.git
    cd gluon
    git checkout origin/v2016.2.x
    git clone https://github.com/Freemesh-Denmark/site-fmdk site
    make update

Build just the default target ar71xx-generic:

    make -j16

Build all targets and experimentals

    for TARGET in ar71xx-generic ar71xx-nand mpc85xx-generic x86-generic x86-kvm_guest x86-64 x86-xen_domu
    do
    	make -j16 GLUON_TARGET=$TARGET BROKEN=1
    done
