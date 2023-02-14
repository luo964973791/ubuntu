### ubuntu离线安装deb依赖包,在有互联网的主机执行,然后压缩打包.
```javascript
cd /var/cache/apt/archives   #注意离线安装deb安装包也必须放在/var/cache/apt/archives这个路径下安装.
apt-get install python3-pip --download-only
ls #所有的安装包下载下来以后,copy到没有互联网的服务器.
apt-get install ./*.deb
```


### ubuntu离线安装pip3依赖包.
```javascript
cat requirement.txt   #比如安装requests模块，在有互联网的服务器执行.
requests
pip3 download -d /root/down -r requirement.txt
cd /root
tar zcvf down.tar.gz down

#在没有互联网的服务器执行
tar xvf down.tar.gz
pip3 install /root/down/*.whl  #拷贝到内网服务器安装.
```
