#### curl检测IP归属
````
[root@10-13-x-x ~]# curl https://ip.cn
//x打码
{"ip": "106.75.x.x", "country": "广东省x市", "city": "x"}

/*** 检测代理是否可用 ***/
//socks5
[root@10-13-x-x ~]# curl --tlsv1.2 -s -m 60 --retry 3 --socks5 113.117.38.234:42693 https://ip.cn
{"ip": "113.117.38.234", "country": "x省x市", "city": "电信"}
//https
[root@10-13-x-x ~]# curl --tlsv1.2 -s -m 60 --retry 3 -x https://180.122.149.239:18441 https://ip.cn
{"ip": "180.122.149.239", "country": "x省x市", "city": "电信"}
````