
# Answer

いろいろ必要なパッケージを入れる

```
apt install build-essential devscripts dh-make fakeroot dpkg-dev
```

`pkgbuild` ユーザに変わって、作業フォルダを作る

```
su - pkgbuild
mkdir build
```

パッケージを解凍

```
cp /opt/CESD00301/cesd00301-0.0.1.tar.xz ./
tar xf cesd00301-0.0.1.tar.xz
cd cesd00301
```

`dh_make` で必要なファイルを作成

```
dh_make -f ../cesd00301-0.0.1.tar.xz
```

`debian/control` の

- Section
- Priority
- Description

を適当に書き換える

GPG鍵を使いパッケージをビルド

```
dpkg-buildpackage -rfakeroot -k'keyid' 
```

出来上がったdebを所定の場所に置く

