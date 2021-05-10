###　实验环境 ：云主机
### 实验工具：putty等远程登录工具
### 软件获取：
#### 1 用wget 从互联网获取
#### 2 用scp从局域网服务器获取，从10.0.1.17服务器拷贝xampp724.run这个文件
    scp vr@10.0.1.17:/home/vr/xampp724.run .   
  注意这个步骤需要输入sudo密码vr123456，还需要输入远程服务器密码：Vr123456,2个不一样。
### 软件的安装，先改权限，赋予可执行权限
    chmod -R 777 xampp724.run   
    sudo ./xampp724.run   

XAMPP Developer Files [Y/n] : Y

然后根据提示安装软件。
Setup has finished installing XAMPP on your computer.
出现以上显示，说明安装正确。
### 查看和验证    浏览器打开 http://101.6.160.22:10180(每个人不同） 
### 停止、启动web服务
#### 首先进入软件安装目录，一般是 /opt/lampp ,命令为
    cd /opt/lampp
    ./ctlscript.sh stop  //停止， 启动为start ，重启为restart 
    /opt/lampp/htdocs  是网站根目录，试着更改index.php 文件（删除index.php 从其他地方找个html文件，改名为index.html)
#### html文件
##### 基本html文件

浏览器打开下面链接，然后按F12显示网页源代码。对比浏览器显示内容和源代码内容。

[http://101.6.160.22:1780/cc07/examples/0mini.html](http://101.6.160.22:1780/cc07/examples/0mini.html)
```  

 <!DOCTYPE html>
   <html>
   <head>
   <title>文档的标题</title>
   </head>
 
   <body>
   文档的内容......
   </body>
 
    </html>
```
##### 包含元素的html文件
[示例文件链接http://101.6.160.22:1780/cc07/examples/1base.html](http://101.6.160.22:1780/cc07/examples/1base.html)

    请注意图片的表示方法，图片链接和图片文件正确对应才能显示，其它类似。请更改文件内容，使符合你的设计。包括文字、图片、链接等。
    
    获取html文件，使用下面命令从服务器拷贝html文件
    
    scp vr@10.0.1.17:/www/cc07/examples/1base.html /opt/lampp/htdocs

    cd /opt/lampp/htdocs    (进入目录，如果已经在此目录下可以跳过此命令）
   
    cp 1base.html index.html   (如果/opt/lampp/htdocs下面有 index.html文件，那么会报错，可以用  rm -rf . 命令删除目录下所有文件）

#### 删除xampp软件执行以下命令
    sudo /opt/lampp/uninstall





