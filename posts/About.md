---
title: "C#笔记(一): 命令行创建项目并构建可执行文件"
date: 2024-8-29
---

# C#笔记(一): 命令行创建项目并构建可执行文件

### 1 dotnet安装
下载并安装
```shell
https://dotnet.microsoft.com/en-us/download
```

### 2 新建解决方案
```shell
mkdir CsharpQuickStart
cd CsharpQuickStart
dotnet new sln -n CsharpQuickStart
```

### 3 在解决方案中添加子项目
```shell
dotnet new console -n ConsoleApp
dotnet sln CsharpQuickStart.sln add ConsoleApp/ConsoleApp.csproj
```

### 4 运行项目
```shell
dotnet run --project ConsoleApp/ConsoleApp.csproj
# cd ConsoleApp
# dotnet run
```

### 5 构建项目
```shell
dotnet publish -c Release -r win-x64 --self-contained -o ./output
./output/ConsoleApp.exe
# Hello, World!
```

> -c Release：指定构建配置为 Release。
> -r win-x64：指定目标运行时为 Windows 64 位。
> --self-contained：生成自包含的可执行文件，这样在目标机器上不需要安装 .NET 运行时。
> -o 参数指定输出目录。
