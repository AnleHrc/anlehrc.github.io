# UE5.2 5.3 使用Rider编译（C++）GAS(Gameplay Abilities System)
## 创建UE C++项目
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/9f8e810abfa4eac3ca2abdea64cb2a10.png)
> 创建之后会出现DirectX找不到的问题,以下为解决办法
>1.  通过下载UE 5.2或者UE5.3源码中的`DirectX.Build.cs`代码,[DirectX.Build.cs](https://github.com/EpicGames/UnrealEngine/blob/5.2/Engine/Source/ThirdParty/Windows/DirectX/DirectX.Build.cs)
> 2. 将下载后的`.cs`文件复制到引擎对应的目录下如:`D:\UnrealEngine\UE_5.2\Engine\Source\ThirdParty\Windows\DirectX\`
> 3. 在Rider中添加 ![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/d9507a26e6583b0ebed5f4f33d3ce1bb.png#pic_center)
> 点击之后选择第二步复制到此目录下的`.cs`文件

## 在UE中开启GAS插件
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/38ac79919eecc8af402770e50eb088c2.png)
勾选`Gameplay Abilities`之后，点击 **Restart Now**
## 在Rider中添加对应的GAS模块
在Rider`你的项目名称.Build.cs`中添加三个基础的**GAS**模块:
`GameplayAbilities`,`GameplayTags`,`GameplayTasks`
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/e5b9d51cc6026d67ddc9b2766607cb33.png)
注意：这时直接Run会出现以下错误：
`  Microsoft.MakeFile.targets(44, 5): [MSB3073] 命令“D:\UnrealEngine\UE_5.2\Engine\Build\BatchFiles\Build.bat CPPDemoTestEditor Win64 Development -Project="E:\UnrealEngineProject\CPPDemoTest\CPPDemoTest.uproject" -WaitMutex -FromMsBuild”已退出，代码为 6。`
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/6240565060b2e31fdeee3f130962272e.png)
### 解决办法
1. 打开项目所在的文件目录：<span><font style="color:red">**删除红色部分文件**</font></span>
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/e5f4bf7082b7e2a45ef74a03ab8f06f2.png)
2. 重新生成项目的`Visual Studio project files`
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/9ad808390f590f2af11a28d5fac48940.png)
3. 使用Rider打开
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/9b4aaf8c8f24251f0c998b57d3e3c1c3.png)
4. 打开`.uproject`，点击 **Yes**
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/823c08182b39cc3538aa39e703be8df6.png)

5. 回到Rider，点击`Build Selected Projects`重新生成项目
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/77c80f5c3c9b5ccb94b0a2567dad019f.png)
6. 编译成功
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/45ac15258cc97a1ea9e9b126fdc36e24.png)





