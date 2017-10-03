FROM ubuntu:16.04

RUN apt-get update \
&& apt-get install wget -y

# First we'll need to grab the SaltStack GPG key and add SaltStack to our sources
RUN wget -O - https://repo.saltstack.com/apt/ubuntu/16.04/amd64/latest/SALTSTACK-GPG-KEY.pub | apt-key add - \
&& echo 'deb http://repo.saltstack.com/apt/ubuntu/16.04/amd64/latest xenial main' > /etc/apt/sources.list.d/saltstack.list

# Install the salt-master components
RUN apt-get update \
&& apt-get install -f \
salt-minion -y

COPY composer.conf /etc/salt/minion.d

CMD ["salt-minion"]
