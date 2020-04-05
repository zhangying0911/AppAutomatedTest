### UIAutomatorviewer启动报错解决方法  
UIAutomatorviewer报错：Unexpected error while obtaining UI hierarchy java.lang.reflect.InvocationTargetException…

原因：

android-sdk-tools中的Uiautomatorviewer的版本太低，
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200405tools.png)



而下载的android sdk系统版本过高（因为我之前只下了API 28）
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200405sdk.png)



解决方法：

更新android-sdk-tools版本，或下载低版本的android sdk（比如android 7）

我又下载了低版本的android sdk（API 24），然后在模拟器中重新换了android 7的模拟器
![](https://github.com/zhangying0911/AppAutomatedTest/raw/master/images/20200405AVD.png)

然后UIAutomatorviewer可以正常启动了～
