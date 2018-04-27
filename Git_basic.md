#Git常用命令
##1、初次上传代码到git库
* create a new repository on the command line
 echo "# tensorflow" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/lulzsec2012/tensorflow.git
git push -u origin master
* ***or*** push an existing repository from the command line
 git remote add origin https://github.com/lulzsec2012/tensorflow.git
git push -u origin master
##2、平时上传代码到git库
git add xx.cpp
git commit -m "commit string"
git push origin local-branch:remote-branch 

##3、权限管理
http://blog.csdn.net/larrysai/article/details/12272039
https://blog.csdn.net/shuyong1999/article/details/7557968
##4、下载代码
git clone git@193.169.1.230:testing.git
##5、使用子模块
git submodule add https://github.com/chaconinc/DbConnector #添加子模块地址
git commit -am 'added DbConnector module'
git push
git clone --recursive https://github.com/chaconinc/MainProject
##6、使用bare库
git init --bare repo_name
##7、查看有权限的库
ssh git@193.169.1.230
http://www.uml.org.cn/pzgl/201404092.asp
##8、删除分支
https://blog.zengrong.net/post/1746.html
##9、常用命令
https://www.cnblogs.com/my--sunshine/p/7093412.html

