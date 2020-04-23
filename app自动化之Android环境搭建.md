## app自动化之Android环境搭建
### 一，Android开发工具
1.Android studio下载安装，是Android 集成开发工具，自带AVD模拟器

2.Android SDK工具安装，这一步在安装Android studio的时候会自动安装，默认存储路径：/Users/jiayou/Library/Android/sdk，即：/Users/[电脑用户名]/Library/Android/sdk，其中包含
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200423sdkPath.png)

3.下载Android sdk的两种方式：

  - 命令行进入SDK Manager的图形界面：首先终端进入到tools目录，然后输入 ./android sdk 请出SDK Manager的图形界面（或直接双击tool目录中的android文件）
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200423sdkManager.png)

  勾选想要下载的sdk版本下载即可。但注意此方法在Android SDK Tools25.2.3以上已不再支持，仅可在Android studio中打开
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200423sdkManager.png)

  - Android studio 中直接下载
打开Android studio 中的configure->sdk manager，勾选想要下载的adk版本即可


4.adb命令配置

  - 打开mac的terminal终端，输入 cd ~/ 【进入当前用户的home目录】
  - 输入 `touch .bash_profile`【如果没有`.bash_profile`这个文件，则创建一个这个文件】
  - 输入 `open .bash_profile` 【打开我们创建的这个文件，此时应该弹出一个文本编辑框，如果是第一次配置环境，那么文本编辑框为空白】
  - 在打开的文本编辑器中写入如下代码并保存：

```
export ANDROID_HOME=/Users/jiayou/Library/Android/sdk
export PATH=${PATH}:${ANDROID_HOME}/tools
export PATH=${PATH}:${ANDROID_HOME}/platform-tools
```          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;注意ANDROID_HOME应该根据自己的sdk路径来填写，其余可以直接复制。

  - 在终端中输入 `source .bash_profile` 【使我们的改动生效】

5.java环境配置
下载好java jdk后，在`.bash_profile`中添加如下代码并保存：

```
export ANDROID_HOME=/Users/jiayou/Library/Android/sdk
export PATH=${PATH}:/Users/jiayou/Library/Android/sdk/platform-tools
export PATH=${PATH}:/Users/jiayou/Library/Android/sdk/tools
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_60.jdk/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH
export CLASS_PATH=$JAVA_HOME/lib:$CLASS_PATH
```
