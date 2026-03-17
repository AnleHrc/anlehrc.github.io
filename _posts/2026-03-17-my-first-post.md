---
layout: post
title: UE5.2 5.3 使用Rider编译（C++）GAS
date: 2026-03-16
description: 解决DirectX找不到及GAS模块添加报错问题
tags: UE5 C++
categories: game-dev
---

# UE5.2 5.3 使用Rider编译（C++）GAS(Gameplay Abilities System)
## 创建UE C++项目
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/1.png" title="1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
接下来，我们对图中的 RMSE 误差指标进行详细分析……
> 创建之后会出现DirectX找不到的问题,以下为解决办法
>1.  通过下载UE 5.2或者UE5.3源码中的`DirectX.Build.cs`代码,[DirectX.Build.cs](https://github.com/EpicGames/UnrealEngine/blob/5.2/Engine/Source/ThirdParty/Windows/DirectX/DirectX.Build.cs)
> 2. 将下载后的`.cs`文件复制到引擎对应的目录下如:`D:\UnrealEngine\UE_5.2\Engine\Source\ThirdParty\Windows\DirectX\`
> 3. 在Rider中添加 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/2.png" title="2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

> 点击之后选择第二步复制到此目录下的`.cs`文件

## 在UE中开启GAS插件
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/3.png" title="3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

勾选`Gameplay Abilities`之后，点击 **Restart Now**
## 在Rider中添加对应的GAS模块
在Rider`你的项目名称.Build.cs`中添加三个基础的**GAS**模块:
`GameplayAbilities`,`GameplayTags`,`GameplayTasks`
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/4.png" title="4" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

注意：这时直接Run会出现以下错误：
`  Microsoft.MakeFile.targets(44, 5): [MSB3073] 命令“D:\UnrealEngine\UE_5.2\Engine\Build\BatchFiles\Build.bat CPPDemoTestEditor Win64 Development -Project="E:\UnrealEngineProject\CPPDemoTest\CPPDemoTest.uproject" -WaitMutex -FromMsBuild”已退出，代码为 6。`
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/5.png" title="5" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### 解决办法
1. 打开项目所在的文件目录：<span><font style="color:red">**删除红色部分文件**</font></span>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/6.png" title="6" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

2. 重新生成项目的`Visual Studio project files`
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/7.png" title="7" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

3. 使用Rider打开
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/8.png" title="8" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

4. 打开`.uproject`，点击 **Yes**
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/9.png" title="9" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


5. 回到Rider，点击`Build Selected Projects`重新生成项目
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/10.png" title="10" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

6. 编译成功
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/blog-2026-03-17/11.png" title="11" class="img-fluid rounded z-depth-1" %}
    </div>
</div>






