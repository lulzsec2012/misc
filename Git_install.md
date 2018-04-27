#Git 安装方法
* 建立git用户账号及git所对应的目录/home/git
* 切换到git账号安装gitolite 
解压gitolite到/home/git/gitolite目录
建立安装目录： mkdir -p /home/git/bin
安装gitolite：/home/git/gitolite/install -to /home/git/bin (***目录必须是绝对路径***)
* 为管理员添加public key： /home/git/bin/gitolite setup -pk /tmp/admin.pub
* 判定是否安装成功
运行 ssh git@127.0.0.1，如果能够正常返回 gitolite-admin、testing 的信息表示安装正确


