FROM centos:7

# First we'll need to grab the SaltStack RPM which has the GPG key and the repository.
RUN yum install -y https://repo.saltstack.com/yum/redhat/salt-repo-latest-2.el7.noarch.rpm  \
&& yum clean expire-cache

RUN yum install -y salt-minion

COPY composer.conf /etc/salt/minion.d

CMD ["salt-minion"]
