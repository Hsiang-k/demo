<!-- Headings -->
# <center><font color=#0099ff size=4 face="黑体">This my first demo in Github</font></center>
<p align="right" >Designed by 向凯</p>

>This is a quote:hello, it's me!!

(A link to an external web site) This is my blog URL  [hsiang's blog](http://rujinyu.com)

>以下是从我的个人博客上截取的Linux服务器命令片段(因为我的blog是挂在linux服务器上的)

### 1.设置服务器本地免密登陆

#### 1).生成本地主机密钥

```shell
ssh-keygen -t rsa
```

#### 2).将本地主机密钥文件传输到服务器上（注意需要输入服务器root用户密码）

```shell
ssh-copy-id -i ~/.ssh/id_rsa.pub root@server_ip
```

<!--more-->

### 2.查看日志

#### 1)动态查看日志，按Ctrl+C退出。program为你想查看的项目名

```shell
cd /var/log
tail -f program.log
```

#### 2)tail -n cnt的意思是显示最后cnt行。program.log是日志文件的名称。grep的意思是查找文件里符合条件的字符串

```shell
tail -n cnt program.log | grep "yyyy-mm-dd"
```

#### 3)如果希望看关键字附近的日志，思路是首先找到关键字所在的行，输入例如指令：

```shell
cat -n program.log | grep "yyyy-mm-dd"
```

这样会的到关键字的所在行的行号，如588,然后输入指令例如：

```shell
cat -n program.log |tail -n +420|head -n 20
```

意思是从420行开始查，显示前20行日志，即从420行查到440行

#### 4)可以使用less命令，对日志进行翻页查看

```
less -N program.log
```

可以查看日志，-N的意思是显示行号，这里N必须大写，按PageUp和PageDown可以进行翻页，输入q退出指令

#### 5)有时候less命令查看日志显示乱码，可以在使用less命令之前先输入命令:

```shell
export LESSCHARSET=utf-8
```

设置一下编码就可以解决乱码问题了有时候log日志很长，你希望从最底部开始往上看，可以按住SHIFT+G，然后通过PageUp和PageDown进行翻页,退出输入q即可

### 3.查看端口占用情况

```shell
netstat -ant |grep port || lsof -i:port || sudo lsof -i tcp:port #查看	
kill -9 PID #杀掉线程，注意PID
```

### 4.密码更改遇到的错误

```shell
BAD PASSWORD: it is based on a dictionary word
```

解决方案:多输几个大小写字母

## npm
```bash
npm install
npm start
```
#### python function

```python
'''
opencv图片降噪处理
'''
import cv2
import matplot.pyplot as plt
def filter_mask(img):
        # 这个过滤器是根据视觉测试手工挑选的
        kernel = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, (2, 2))

        # 填补任何小洞
        closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)
        # 去除噪音
        opening = cv2.morphologyEx(closing, cv2.MORPH_OPEN, kernel)

        # 膨胀以合并相邻的小块
        
        # opening = cv2.erode(img, kernel, iterations=2)
        
        dilation = cv2.dilate(opening, kernel, iterations=2)

        return dilation
```
##### javascript
```javascript
function add(num1, num2) {
    return num1 + num2;
}
```
<p align="center"><font color=#ff00 size=4 face="黑体">images</font></p>
<p>下面是我将照片上传网站获得的链接</p>

![wallhaven-lqre12.jpeg](https://i.loli.net/2021/04/28/Cm2RcEArTUhtNPn.jpg)

<p>从GitHub 文件目录中读到的照片</p>
