# Mochiweb RPM package for CentOS 7

Steps to build:

  * Install build tools: yum groupinstall "Development tools" && yum install rpmdevtools
  * git clone https://github.com/idi-ops/mochiweb-centos-rpm
  * cd mochiweb-centos-rpm
  * Install build dependencies: yum install -y `egrep '^BuildRequires' erlang-mochiweb.spec | awk '{ printf("%s ", $2); }'`
  * spectool -g -A -R erlang-mochiweb.spec
  * mkdir -p ~/rpmbuild/SOURCES
  * cp * ~/rpmbuild/SOURCES
  * rpmbuild -bb erlang-mochiweb.spec

