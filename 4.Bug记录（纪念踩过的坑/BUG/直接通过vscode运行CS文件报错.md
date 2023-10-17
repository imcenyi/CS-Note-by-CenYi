![Pasted image 20230614104941.png](https://cenyi-picture-1317709115.cos.ap-shanghai.myqcloud.com/picture/202306230142390.png)

## 这个C#脚本文件在Unity所开的项目中可以正常运行，但为什么直接在vscode运行不行呢。
### 1.首先是报错的原因
这个错误提示意味着 PowerShell 无法找到名为 scriptcs 的命令。这通常是因为 scriptcs 没有被正确安装或者没有被添加到系统的 PATH 环境变量中。请确保您已经正确安装了 scriptcs，并将其添加到 PATH 环境变量中。如果您已经安装了 scriptcs 并且将其添加到了 PATH 环境变量中，那么请检查您的命令是否正确拼写。
## 2.那为什么在Unity的项目对象中可以直接运行，而不会报错
Unity 引擎已经为您配置好了项目所需的环境，包括编译器、库和其他依赖项。在 Unity 中，您可以直接编写 C# 代码，并且 Unity 引擎会自动编译和运行您的代码。因此，您可以在 Unity 中直接运行这段代码，而不需要手动配置环境。
在 Unity 中使用了 C# 脚本，那么您不需要使用 scriptcs 来运行它们。Unity 引擎会自动编译和运行您的脚本。因此，如果您在 Unity 中使用 C# 脚本，那么将 scriptcs 添加到 PATH 环境变量中不会对您的 Unity 项目造成任何影响。但是，如果您在 Unity 之外的地方使用 scriptcs 运行 C# 脚本，那么您需要将 scriptcs 添加到 PATH 环境变量中。

## 解决方法，将scriptcs所在的目录加入到环境变量当中。
