FROM ssh

RUN apt update

# for debconf: unable to initialize frontend: Dialog
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

# stm32mp1 yocto build env download 
# see https://wiki.st.com/stm32mpu/wiki/STM32MP1_Distribution_Package

RUN apt install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 pylint xterm -y

RUN apt install make xsltproc docbook-utils fop dblatex xmlto -y

RUN apt install libmpc-dev libgmp-dev -y

RUN apt install libncurses5 libncurses5-dev libncursesw5-dev libssl-dev linux-headers-generic u-boot-tools device-tree-compiler bison flex g++ libyaml-dev libmpc-dev libgmp-dev -y

RUN apt install coreutils bsdmainutils sed curl bc lrzsz corkscrew cvs subversion mercurial nfs-common nfs-kernel-server libarchive-zip-perl dos2unix texi2html diffstat libxml2-utils -y

# install python
RUN apt install python -y

# install `repo`
RUN curl https://storage.googleapis.com/git-repo-downloads/repo > /bin/repo
RUN chmod a+x /bin/repo

# install lub-usb
RUN apt install libusb-1.0