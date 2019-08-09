#  Git总结 (上传的基本操作)
* 首先下载Git
* 然后安装Git
* 安装成功后 鼠标右击 桌面 菜单栏里会有 Git GUI和Git Bash
* 右击桌面 然后点击 Git Bash
* 然后输入用户名 git config --global user.name "jie_je"
* 然后在输入邮箱 git config --global           email1282814653@qq.com
**在同一个路径的情况下账户密码不需要重复输入**
* 1. 首先初始化仓库 git init
* 2. 接下来 添加文件 git add . (.是添加全部文件)
* 3. 然后添加 上传的文件的描述 git commit -m'' (''里面些的是描述)
* 4. 然后 git remote add origin url (url 是git上面需要上传的http 地址路径)
**在同一个路径下只需要输入一次url即可**
* 5. 最后使用 git push origin master 把本地的数据放到仓库中去
* 6. 最后可是使用 git status 查看上传状态
* 如果更新内容 在上传更新内容的话 在同一个路径的情况下 重复操作1. 2. 3. 5. 即可

