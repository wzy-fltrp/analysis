# Python IDE（Anaconda）的安装

### 1.安装包的下载

建议直接到 [https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/) 下载，选择适合自己操作系统的Anaconda3进行下载；

![](.gitbook/assets/image%20%284%29.png)

### 2.Anaconda3的安装

将安装路径设置为D:\Anaconda3，安装过程除了如下这一步外，一路next就行：

![](.gitbook/assets/image%20%2822%29.png)

### 3.添加环境变量

在我的电脑中依次点击属性——高级系统设置—高级—环境变量——系统变量选中path——编辑——新建，添加D:\Anaconda3等四个目录地址（如果你的安装目录和我一样都为D:\Anaconda3的话）

![](.gitbook/assets/image%20%2820%29.png)

![](.gitbook/assets/image%20%2819%29.png)

在添加完环境变量后，对于windows系统，通过win+R，输入cmd（或直接搜索命令提示符）进入windows的终端，通过输入conda --version，若出现版本名，则证明环境变量已经添加成功

![](.gitbook/assets/image%20%2824%29.png)

### 4.Anaconda的用法（仅简单介绍jupyter notebook）

对于jupyter notebook，可通过在windows终端中输入jupyter notebook进行打开：

```text
C:\Users\Administrator>jupyter notebook
```

 若电脑中有火狐浏览器的话，会直接进行jupyter notebook的打开，否则在输入信息中找到一个类似这样的[http://localhost:8888/](http://localhost:8888/)网址，将它复制到浏览器中，则可进行jupyter notebook的打开。

![](.gitbook/assets/image%20%2817%29.png)

相较于传统的IDE，Anaconda在浏览器中具有很好的集成，无论是深度学习模型的训练，还是数据处理，均可使用jupyter notebook在浏览器中运行。

