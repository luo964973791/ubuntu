### ubuntu离线安装deb依赖包,在有互联网的主机执行,然后压缩打包.
```javascript
cd /tmp
apt-get install python3-pip --download-only --no-install-recommends
cd /var/cache/apt/archives
tar zcvf tmp.tar.gz tmp
#在没互联网的ubuntu服务器安装依赖.
tar xvf tmp.tar.gz && cd tmp
apt-get install ./*.deb --no-install-recommends
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
