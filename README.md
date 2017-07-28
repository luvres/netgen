## Netgen 5.3.1 build OCC 7
-----
### Procedure:
#### Download Netgen in sourceforge.net
```
wget https://sourceforge.net/projects/netgen-mesher/files/netgen-mesher/5.3/netgen-5.3.1.tar.gz
tar xvzf netgen-5.3.1.tar.gz
mv netgen-5.3.1/* .
rm netgen-5.3.1* -fR

curl -L https://github.com/FreeCAD/homebrew-freecad/releases/download/0/nglib-occt7.patch | patch -p1

sed -i '/DOCCGEOMETRY/s/\/usr/$occdir/' configure
sed -i '/DOCCGEOMETRY/s/inc/include/' configure
```
