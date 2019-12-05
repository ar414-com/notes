##### 强制覆盖本地
````
git fetch --all && git reset --hard origin/master && git pull origin master
````

##### git clone 指定分支
````
git clone -b dev https://github.com/ar414-com/notes.git
````

#### git初始化仓库，远程提交
1、 初始化本地仓库
````  
git init
````
2、 连接远程仓库
````  
git remote add origin  https://github.com/ar414-com/notes.git
````
3、 更新本地代码(远程可能有些代码本地是没有的)
````  
git add .
````
4、提交暂存区的文件到本地仓库
````
git commit -m "first commit"
````
5、提交本地代码
````
git push origin master
````

