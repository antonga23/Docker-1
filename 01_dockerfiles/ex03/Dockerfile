FROM ubuntu:latest

LABEL antonga <antonga@student.wethinkcode.co.za>

EXPOSE 443 80 22

RUN apt-get update &&  apt-get install -y curl openssh-server ca-certificates
RUN apt-get install -y postfix
RUN apt-get install -y curl
RUN apt-get upgrade -y
RUN curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt-get install -y gitlab-ce
RUN apt install -y tzdata

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null