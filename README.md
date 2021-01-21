# licheepizero_SDK

## Instruction how to build an image for LichePi Zero with Yocto

## How to build an image

1.these packages must be installed on your system:<br>
	<br>
	***apt-get install wget git-core unzip make gcc g++ build-essential subversion sed autoconf<br> 
	automake texi2html texinfo coreutils diffstat python-pysqlite2 docbook-utils libsdl1.2-dev <br>
	libxml-parser-perl libgl1-mesa-dev libglu1-mesa-dev xsltproc desktop-file-utils <br>
	chrpath groff libtool xterm gawk fop***<br>
<br>

2.run this command to create build directory:<br>
	<br>
	***source oe-init-build-env***<br>
<br>

3.now you must be in build directory, so add two layers to bblayers file(): <br>
<br>
	***bitbake-layesr add-layer ../source/meta-licheepizero<br>
	   bitbake-layers add-layer ../source/meta-qt5***
<br>

4.modify line with "MACHINE ??" to add "licheepizero-dock" or "licheepizero" in build/conf/local.conf
<br>

5.build your image:<br>
	<br>
	***bitbake console-image***<br>
<br>

after building your image must be in build/tmp/deploy/images/licheepizero...
so you can write it to SD card like :
<br>
<br>
***sudo dd if=~/yocto/tmp/deploy/images/licheepizero/console-image-licheepizero.sunxi-sdimg of=/dev/sdx bs=1024***
<br>
