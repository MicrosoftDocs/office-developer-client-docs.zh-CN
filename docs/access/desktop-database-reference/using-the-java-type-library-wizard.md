---
title: 使用 Java 类型库向导
TOCTitle: Using the Java Type Library Wizard
ms:assetid: 96af770c-c7c2-c905-3c3e-383a5b99cab2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249670(v=office.15)
ms:contentKeyID: 48546455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 233e1a9e6237500b3d13e3234e7c6ddf4d556abc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884133"
---
# <a name="using-the-java-type-library-wizard"></a>使用 Java 类型库向导


**适用于**： Access 2013、 Office 2013

Java 类型库向导是一项功能的 Visual J + + 1.x，集成开发环境的**工具**菜单。 其用途是搜索类型库创建一个允许访问 COM 对象的 Java 接口。 对于 Visual J + + 6.0，已使用[ADO for Windows Foundation Classes](ado-wfc-programming.md)取代 Java 类型库向导。

Java 类型库向导的执行效果与 [Microsoft SDK for Java](using-the-microsoft-sdk-for-java.md) 中的命令行工具类似。不过，您不能进入向导所生成的类包装中，这一点与 Microsoft SDK for Java 所生成的类包装不同。

Java 类型库向导生成的类在以下位置： \\ \<windows 目录\>\\Java\\trustlib\\msado15。 生成类的目录下的 Summary.txt 文件显示了所生成的类定义。

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

**若要从 Visual J + + 版本 1.*x 运行 Java 类型库向导***

1.  从**工具**菜单中，选择**Java 类型库向导**。

2.  选择"Microsoft ActiveX 数据对象库"，然后单击**确定**。 此立即 (re) 生成文件\\ADO trustlib 目录 (默认情况下，c： 在\\可以对\\java\\trustlib\\msado15)。 如果您使用 Microsoft SDK for Java 已生成类的 ADO，它们将使用 Java 类型库向导来自被替换。

3.  若要使用这些文件，打开您的项目在 Visual J + + 中。 从**项目**菜单中，选择**添加到项目**。 选择**文件**，然后添加的所有。JAVA 文件中生成\\trustlib 目录 (默认情况下，c： 在\\可以对\\java\\trustlib\\msado15) 向您的项目。

