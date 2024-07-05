如何对apt代理？

```bash
sudo apt-get -o Acquire::http::proxy="http://127.0.0.1:7890/" update
```

如何对docker进行代理
1. 创建/etc/systemd/system/docker.service.d/http-proxy.conf文件
```bash
sudo touch /etc/systemd/system/docker.service.d/http-proxy.conf
```
2. 将代理信息依照下面的格式写入
```config
[Service]
Environment="HTTP_PROXY=http://192.168.6.200:3128/"
Environment="HTTPS_PROXY=http://192.168.6.200:3128/"
```
4. 用下面的指令重启docker
```bash
systemctl daemon-reload
systemctl restart docker
```



