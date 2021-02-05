# python-deb
A debian folder to build python 3.8
This is a /debian folder to build python for Debian. Why one may need it? 
# You want to build the latest python for your debian/ubuntu but you don't want to break the existing python installation
# You want to use the appropriate installation method, i.e. package instead of make && make install


Usage:
```bash
apt install pbuilder debhelper
echo USENETWORK=yes >> /etc/pbuilderrc
pbuilder create --distribution=eoan
exit

wget https://www.python.org/ftp/python/3.8.1/Python-3.8.1.tgz
tar xzf Python-3.8.1.tgz
git clone https://github.com/d0td0td0t/python-deb
cd Python-3.8.1
rsync -avP ../python-deb/debian/ ./debian/
```
