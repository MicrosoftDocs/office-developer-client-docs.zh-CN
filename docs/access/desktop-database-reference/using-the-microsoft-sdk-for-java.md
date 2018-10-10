---
title: 使用 Microsoft SDK for Java
TOCTitle: Using the Microsoft SDK for Java
ms:assetid: 35a1adb2-06d6-ff45-f151-f1f60ff9bfe2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249116(v=office.15)
ms:contentKeyID: 48544152
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dbcae50b0fdecc441bab40894899a75d04ee5f72
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465555"
---
# <a name="using-the-microsoft-sdk-for-java"></a>使用 Microsoft SDK for Java


**适用于**： Access 2013 |Office 2013

Microsoft SDK for Java 是一个针对 Microsoft Internet Explorer 环境的开发包。其中提供了工具、信息和示例，以帮助您基于 JDK 1.1 和 Microsoft Win32 虚拟机 (Microsoft VM) 开发 Java 程序和小程序。Microsoft SDK for Java 未与 Microsoft Visual J++ 绑定。

Jactivex.exe 实用工具从类型库生成类，但只能在命令行中调用。此工具未与 Visual J++ 开发环境集成。与 [Java 类型库向导](using-the-java-type-library-wizard.md)不同，您可以进入 SDK 所创建的类包装中。此功能对于调试代码如何使用 ADO 包装类很有帮助。

此机制读取 ADO 类型库并生成类，您可以在应用程序中对类进行实例化。 将这些类生成在以下位置： \\ \<windows 目录\>\\Java\\trustlib\\msado15。

从源代码角度来看，使用 Microsoft SDK for Java 在 Java 中创建 ADO 应用程序与使用 Java 类型库向导基本相同。对于示例代码，请参阅 [ADO Java 类包装](ado-java-class-wrappers.md)。唯一的真正区别是在开始时生成包装类的方式，如以下步骤所示。

**使用 Microsoft SDK for Java 创建 ADO 项目**

1.  在命令提示符下运行以下语句。您必须设置路径以包括 Microsoft SDK for Java Bin 目录，或从该位置运行命令。一般情况下，Microsoft SDK for Java 的安装位置与 Visual Studio 一样。以下语句为单个命令语句。
    
    ```vb 
     
    \<path to DevStudio>\<path to Java SDK>\bin\JactiveX.exe /javatlb "C:\program files\common files\system\ado\msado15.dll" 
    ```

2.  运行以下命令以编译所生成的类。/g:t 开关打开了调试符号的生成，从而使您能够跟踪到 .Java 符号中。发布版本中没有此命令。
    
    ```vb 
     
    jvc /g:t c:\<windows>\Java\trustlib\msado15\*.Java 
    ```

3.  若要使用这些文件，打开您的项目在 Visual J + + 中。 从**项目**菜单中，选择**添加到项目**。 选择**文件**，然后添加的所有。在 trustlib 中生成的 JAVA 文件\\msado15 目录到您的项目。

