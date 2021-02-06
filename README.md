# python-deb
A debian folder to build python 3.8
This is a /debian folder to build python for Debian. Why one may need it? 
1. You want to build the latest python for your debian/ubuntu but you don't want to break the existing python installation
2. You want to use the appropriate installation method, i.e. package instead of make && make install


Usage:
```bash
# Prepare the pbuilder build environment (building for Ubuntu eoan
# You'll have to lookup the release name in /etc/apt/sources.list):

sudo bash
apt install pbuilder debhelper
echo USENETWORK=yes >> /etc/pbuilderrc
pbuilder create --distribution=eoan
exit

# Download python source and this repository.
wget https://www.python.org/ftp/python/3.9.1/Python-3.9.1.tgz
tar xzf Python-3.9.1.tgz
git clone https://github.com/d0td0td0t/python-deb
cd Python-3.9.1
rsync -avP ../python-deb/debian/ ./debian/

# Actually build the package:
sudo pdebuild
```
