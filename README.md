# SpringBoot+Vue前后端分离开发

因为他要求创建一个README.md，所以我先创建一个！

嫌弃了git本地仓库直接建立在桌面，浪费了C盘的空间，我在D盘又新建了文件夹，将git仓库初始化。发现clone下载速度巨慢，通过设置代理socks：1080的方式，让下载速度变快：

```c
git config --global http.proxy 'socks5://127.0.0.1:1080'
git config --global https.proxy 'socks5://127.0.0.1:1080'
```

可是这个方法只能加速 https 的速度，我再想要push的时候，每次都需要输入密码。

把换成了SSH的方式：

```c
$ git remote -v                   //查看传输方式
```

```c
$ git remote rm origin            //移除当前方式
```

```c
$ git remote add origin git@github.com:hex39/SpringBoot_Vue_Book_CRUD.git
//设置成SSH方式
```

使用git在本地新建一个分支后，需要做远程分支关联，如果没有关联，git会在下面的操作中提示你显示的添加关联。关联目的是在执行git pull, git push操作时就不需要指定对应的远程分支，你只要没有显示指定，git pull的时候，就会提示你。

```c
$ git branch --set-upstream
```

$ git push -u origin master 上面命令将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数使用git push了。

```
$ git push -u origin master
```

接下来就能无脑 git push 命令了！

现在还需要测试一下git pull命令
