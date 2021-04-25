FROM ubuntu:20.04

ENV userId="craven"
ENV password="1928"

RUN apt update

# locale seeting
RUN apt install -y locales locales-all
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8

# for bash completion
RUN apt install bash-completion

# install SSH server
RUN apt install  openssh-server sudo -y
RUN service ssh start
CMD ["/usr/sbin/sshd","-D"]

EXPOSE 22

# add user account
RUN useradd -rm -d /home/$userId -s /bin/bash -G sudo -U -u 1000 $userId

# id:password
RUN  echo "$userId:$password" | chpasswd 

