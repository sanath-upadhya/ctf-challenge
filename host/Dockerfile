FROM ubuntu
EXPOSE 22


RUN apt update && apt -y install openssh-server
RUN apt-get update && apt-get install net-tools
RUN apt-get update && apt-get -y install nmap
RUN apt-get update && apt-get -y install hydra
RUN apt-get update && apt-get -y install vim
RUN apt-get update && apt-get -y install crunch

RUN adduser --disabled-password --gecos "" labuser && echo 'labuser:labuser' | chpasswd 

COPY README.txt /home/labuser/
COPY .hidden_info.txt /home/labuser
COPY passwords.txt /etc/ssh/ssh_config.ds/

ENTRYPOINT service ssh start && tail -f /dev/null 
