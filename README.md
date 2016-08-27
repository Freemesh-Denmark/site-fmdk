Doku: https://gluon.readthedocs.org/en/v2016.1/user/site.html

Gluon version used for this build:

Gluon 2016.1.5

Added Packages:
	- USB-auto-mount
	- Kontaktfeld pflicht
	- roamguide (initial inaktiv)

Build
-----
You can easily create your own experimental build with these commands:

    sudo apt-get install git make gcc g++ unzip libncurses5-dev zlib1g-dev subversion gawk bzip2 libssl-dev
    git clone https://github.com/freifunk-gluon/gluon.git
    cd gluon
    git clone git@git.freifunk.in-kiel.de:ffki-site.git site
    make update
    D=$(date '+%y%m%d%H%M');
    for TARGET in ar71xx-generic ar71xx-nand mpc85xx-generic x86-generic x86-kvm_guest x86-64 x86-xen_domu; do
    	make GLUON_TARGET=$TARGET DEFAULT_GLUON_RELEASE=2016.1.5~exp$D BROKEN=1;
    done



