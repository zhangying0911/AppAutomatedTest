### 自动化脚本启动第三方app时包名启动页正确但是报错An unknown server-side error occurred while processing the command…

查了很多遇到这个问题的人，大多是appActivity启动页名没写对，所以这里顺便贴一下获取正确的包名和启动页名的命令吧：

```
adb shell dumpsys window windows | grep mFoc
```

这个命令的执行前提是，手动在模拟器or真机上打开了app的某个页面。
结果中斜线左边到空格前的一串是package名，斜线右边到空格前的一串是Activity名，分别直接复制就可以了。
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200406findActivity.png)

奇怪的是我启动自带的app 比如设置，相机这种都没问题，启动第三方的就报错，说包名和启动页名不对。想了很久觉得Android的兼容性问题一直都是很诡异的，于是重新换不同的android sdk来试，android 9、8、7都是同样错误，再试6，神奇的好了，5也是好的。。。emmm，好吧，问题就这样神奇的解决了。

最后还发现，android studio里面的AVD模拟器兼容性问题尤其奇怪，用第三方的模拟器比如Gennymotion又是可以正常启动的。
