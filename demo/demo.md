<!-- Headings -->
# <center><font color=#0099ff size=4 face="黑体">This my first demo in Github</font></center>
<p align="right" >Designed by 向凯</p>

## 一、blockQuote

>This is a block quote:hello, it's me!!

## 二、external web site
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
## 三、代码加高亮
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
## 四、照片
<p>下面是我将照片上传网站获得的链接</p>

![wallhaven-lqre12.jpeg](https://i.loli.net/2021/04/28/Cm2RcEArTUhtNPn.jpg)

<p>下面是从GitHub 文件目录中读到的照片</p>

![wallhaven-lqre13.jpeg](https://github.com/Hsiang-k/demo/blob/master/images/header.jpg)

## 五、从一个markdown文件跳转到另一个markdown文件

[Link from the second markdown file back to the README.md](https://github.com/Hsiang-k/demo/blob/master/README.md)
<p>从README.md文件跳转到本文件见README文件</p>

## 六、其他

## list部分

>bulleted list：
- bulleted list item 1 
- bulleted list item 2
- bulleted list item 3 
    - element1
    - element2
    - element3

>numbered list:
1. numbered item 1
2. numbered item 2
3. numbered item 3
    - numbered element

## table 部分
|  Name     |    Email  |
| --------- | --------- |
| xiangkai  | 1234@gmial.com |
| John      | hhh@gmial.com  |

## 加粗
**This is a bold text**

##  强调
*This a italicized text.*

## 删除线
~~Strikethrough~~

--- 
这是一条华丽的分割线

---
作者：向凯
<p>完结撒花</p>