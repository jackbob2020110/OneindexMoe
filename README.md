# OneIndex-mod
Onedrive Directory Index mod

## 功能：
不占用服务器空间，不走服务器流量，  直接列出 OneDrive 目录，文件直链下载。  

## mod特点
1.采用最新down/oneindex,萌化默认主题
2.无需手动设置定时任务，后台每10分钟自动刷新
3.docker全自动搭建

## 本站Demo
[https://cloud.baiyue.one](https://cloud.baiyue.one)  

## 安装运行

#### 必要条件：
OneDrive 账号 如需5T云盘，[点击传送门](https://mall.baiyue.one/product/11.html) 

## docker安装
首先安装docker【已安装的可跳过】

```
docker version > /dev/null || curl -fsSL get.docker.com | bash 
service docker restart 
systemctl enable docker  #设置开机自启
```
之后执行安装命令
```
docker run -d -p 8181:80 --restart=always baiyuetribe/oneindex
```
完成后输入http://ip:8181 按提示操作即可。

<img width="658" alt="image" src="https://raw.githubusercontent.com/donwa/oneindex/files/images/install.gif">  


最终效果：
![](https://ww1.sinaimg.cn/large/007i4MEmgy1g1h9f6wh8sj31gy0ps1kx.jpg)
## 特殊文件实现功能  
` README.md `、`HEAD.md` 、 `.password`特殊文件使用  

可以参考[https://github.com/donwa/oneindex/tree/files](https://github.com/donwa/oneindex/tree/files)  

**在文件夹底部添加说明:**  
>在 OneDrive 的文件夹中添加` README.md `文件，使用 Markdown 语法。  

**在文件夹头部添加说明:**  
>在 OneDrive 的文件夹中添加`HEAD.md` 文件，使用 Markdown 语法。  

**加密文件夹:**  
>在 OneDrive 的文件夹中添加`.password`文件，填入密码，密码不能为空。  

**直接输出网页:**  
>在 OneDrive 的文件夹中添加`index.html` 文件，程序会直接输出网页而不列目录。  
>配合 文件展示设置-直接输出 效果更佳。  


**上传文件:**  

推荐使用系统自带的OneDrive程序客户端或者使用RaiDrive进行文件的修改、上传、删除操作。