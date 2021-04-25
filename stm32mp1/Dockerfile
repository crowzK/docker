FROM ubuntu:20.04

RUN apt update && apt install  openssh-server sudo -y

RUN apt install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev pylint3 pylint xterm -y

RUN apt install make xsltproc docbook-utils fop dblatex xmlto -y

RUN apt install libmpc-dev libgmp-dev -y

RUN apt install libncurses5 libncurses5-dev libncursesw5-dev libssl-dev linux-headers-generic u-boot-tools device-tree-compiler bison flex g++ libyaml-dev libmpc-dev libgmp-dev -y

RUN apt install coreutils bsdmainutils sed curl bc lrzsz corkscrew cvs subversion mercurial nfs-common nfs-kernel-server libarchive-zip-perl dos2unix texi2html diffstat libxml2-utils -y

RUN useradd -rm -d /home/craven -s /bin/bash -G sudo -U -u 1000 craven

RUN  echo 'craven:1928' | chpasswd 

RUN mkdir /home/craven/bin

RUN curl https://storage.googleapis.com/git-repo-downloads/repo > /home/craven/bin/repo

RUN chmod a+x /home/craven/bin/repo

RUN apt install bash-completion

RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
