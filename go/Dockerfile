FROM golang:1.20.2
RUN apt install apt-transport-https ca-certificates
# RUN sed -i s@/http://deb.debian.org/@/https://mirrors.tuna.tsinghua.edu.cn/@g /etc/apt/sources.list
RUN bash -c 'echo -e "deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye main contrib non-free \n \
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye main contrib non-free \n \
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-updates main contrib non-free \n \
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-updates main contrib non-free \n \
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-backports main contrib non-free \n \
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ bullseye-backports main contrib non-free \n \
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security main contrib non-free \n \
deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security bullseye-security main contrib non-free \n " > /etc/apt/sources.list'
RUN apt-get clean
RUN apt-get update
RUN apt-get install -y vim
RUN go env -w GO111MODULE=on
RUN go env -w GOPROXY=https://goproxy.cn,direct
WORKDIR /var/www/http
EXPOSE 8088