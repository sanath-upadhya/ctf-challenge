FROM ubuntu
EXPOSE 22
COPY README.txt /home/labuser/
COPY flag.txt /etc/kernel/postinst.d
RUN apt-get update && apt-get -y install ssh
RUN adduser --disabled-password --gecos "" labuser && echo 'labuser:thispwd' | chpasswd 
ENTRYPOINT service ssh start && tail -f /dev/null 