# Creating nginx 1.0.15 with lua extension RPM Packages for Centos 6.5

## Building with rpmbuild on host OS

### Centos Step 1
* Configure [EPEL](http://fedoraproject.org/wiki/EPEL)
  * Download latest version of epel-release [epel-release](http://linux.mirrors.es.net/fedora-epel/6/i386/repoview/epel-release.html)
  * rpm -ihv epel-release-{version}.noarch.rpm
* Setup rpmbuild
  * [Instructions](http://wiki.centos.org/HowTos/SetupRpmBuildEnvironment)

### Centos Step 2
* Copy contents of repo to ~/rpmbuild/SOURCES
* Build SRPM
  * rpmbuild -bs nginx.spec
* Install dependencies
  * sudo yum localinstall luajit-2.1.0-alpha.xunyou.el6.rpm
  * sudo yum-builddep ~/rpmbuild/SRPMS/nginx-{version}.{release}.src.rpm
* rpmbuild --rebuild ~/rpmbuild/SRPMS/nginx-{version}.{release}.src.rpm



