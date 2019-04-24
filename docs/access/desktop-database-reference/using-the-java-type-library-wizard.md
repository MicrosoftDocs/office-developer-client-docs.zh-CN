---
title: 使用 Java 类型库向导
TOCTitle: Using the Java Type Library Wizard
ms:assetid: 96af770c-c7c2-c905-3c3e-383a5b99cab2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249670(v=office.15)
ms:contentKeyID: 48546455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a27491acabd19f688eca4159a36dcfcfc486a026
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312080"
---
# <a name="using-the-java-type-library-wizard"></a>使用 Java 类型库向导


**适用于**：Access 2013、Office 2013

The Java Type Library Wizard is a feature of Visual J++ 1.x, integrated into the **Tools** menu of the development environment. Its purpose is to search a type library and create a Java interface that allows access to COM objects. For Visual J++ 6.0, the Java Type Library Wizard has been replaced with [ADO for Windows Foundation Classes](ado-wfc-programming.md).

Java 类型库向导的执行效果与 [Microsoft SDK for Java](using-the-microsoft-sdk-for-java.md) 中的命令行工具类似。不过，您不能进入向导所生成的类包装中，这一点与 Microsoft SDK for Java 所生成的类包装不同。

Java 类型库向导在以下位置生成类: \\ \<windows directory\>\\Java\\trustlib\\msado15.dll。 生成类的目录下的 Summary.txt 文件显示了所生成的类定义。

Java 类型库向导将在任何给定类型库中发现的枚举类型转换为 INT（整数）类型。它还定义一个接口，对应于类型库中的每个枚举类型。您可以用以下语法引用 ADO 枚举类型的值：

```vb 
 
msado15.<Enum Name>.<constant Name> 
```

以设置 **Command** 对象的 **CommandType** 属性为例，其代码片断如下：

```vb 
 
Cmd1.putCommandType( msado15.CommandTypeEnum.adCmdStoredProc ); 
```

或者，您也可以从 Java 类型库向导所生成的枚举类型包装继承 ADO 对象和枚举值。如果这么做，那么可以从语法中删除"msado15."。不过，类必须从它所引用的每个 Java 对象和枚举类型接口继承，以完全避免在所有 ADO 对象和枚举值之前引用 msado15.\*。

有关更多示例代码，请参阅 [ADO Java 类包装](ado-java-class-wrappers.md)。

**从 Visual j + + 版本 1. * x 运行 Java 类型库向导***

1.  From the **Tools** menu, select **Java Type Library Wizard**.

2.  Select "Microsoft ActiveX Data Objects Library" and click **OK**. 这现在 (re \\) 将在 trustlib 目录中为 ADO 生成文件 (默认情况下为\\c\\:\\winnt\\java trustlib msado15.dll)。 If you used the Microsoft SDK for Java to already generate classes for ADO, they will be replaced with those from the Java Type Library Wizard.

3.  To use these files, open your project in Visual J++. 从“工程”**** 菜单中，选择“添加到工程”****。 选择 "**文件**", 并将所有。在\\trustlib 目录中生成的 JAVA 文件 (默认情况下为\\c\\:\\winnt\\java trustlib msado15.dll) 到您的项目。

