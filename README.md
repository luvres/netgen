## Netgen 5.3.1 build OCC 7
-----
### Procedure:

#### Download Netgen in sourceforge.net
```
wget https://sourceforge.net/projects/netgen-mesher/files/netgen-mesher/5.3/netgen-5.3.1.tar.gz
tar xvzf netgen-5.3.1.tar.gz
mv netgen-5.3.1/* .
rm netgen-5.3.1* -fR
```

#### Patch nglib-occt7
```
curl -L https://github.com/FreeCAD/homebrew-freecad/releases/download/0/nglib-occt7.patch | patch -p1

OR

wget https://raw.githubusercontent.com/luvres/netgen/master/nglib-occt7.patch
patch -p1 < nglib-occt7.patch
```

#### Patch occdir
```
curl -L https://raw.githubusercontent.com/luvres/netgen/master/occdir.patch | patch

OR

wget https://raw.githubusercontent.com/luvres/netgen/master/occdir.patch
patch -p0 < nglib-occt7.patch
```
##### Occdir patch source
```
sed -i '/DOCCGEOMETRY/s/\/usr/$occdir/' configure
sed -i '/DOCCGEOMETRY/s/inc/include/' configure
sed -i '/DOCCGEOMETRY/s/\/usr/$occdir/' configure.ac
sed -i '/DOCCGEOMETRY/s/inc/include/' configure.ac
```
