# 解决Ubuntu下Sublime不能输入中文

1. 首先下载`sublime-text-imfix`，这是一个用`Shell`和`C`编写的插件。

	$ it clone https://github.com/lyfeyaj/sublime-text-imfix.git

2. 将`subl`移动到`/usr/bin`，并且将`sublime-imfix.so`移动到`/opt/sublime_text/`（sublime的安装目录）

	$ cd ~/sublime-text-imfix
	$ sudo cp ./lib/libsublime-imfix.so /opt/sublime_text/
	$ sudo cp ./src/subl /usr/bin/

> 以上`~`只是为根目录，因为再第一步中打开终端后，默认位置在`~`，你可以选择下载到其他目录，自然相应的也要更改后面的`~`

3. 用`subl`命令尝试能不能启动sublime，如果成功启动的话，应该是可以输入中文的。

	$ subl

终端输入：

	$ LD_PRELOAD=./libsublime-imfix.so subl

4. 但是这样只能用上述命令才能输入中文，也就是启动能输入中文的版本。所以为了方便，我们再新建一个shell脚本。

	$ cd home
	$ vim sublime

于是我们在`home`目录下新建了一个`sublime`文件，接着输入：

	#!/bin/bash
	LD_PRELOAD=/opt/sublime_text/libsublime-imfix.so subl

接着`esc`退出编辑模式，`:wq`保存退出。

5. 至此，我们就完成了所有工作。想要启动，直接终端输入`bash ~/sublime`，就可以启动sublime，并且可以输入中文。

6. 如果不需要输入中文，直接按照以前的方式打开即可。建立脚本的目的是为了能方便地打开能输入中文的sublime。