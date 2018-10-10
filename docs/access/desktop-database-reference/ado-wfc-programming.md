---
title: ADO/WFC 编程
TOCTitle: ADO/WFC Programming
ms:assetid: fc438cc2-00b9-9590-6e0d-a865001ccf2f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250293(v=office.15)
ms:contentKeyID: 48548887
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 88343d14a9419cbc3425e0c21dee08d243f2e697
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466037"
---
# <a name="adowfc-programming"></a>ADO/WFC 编程


**适用于**： Access 2013 |Office 2013

对于 Microsoft Visual J++ 6.0，ADO 已经得到扩展，这使它能够按以下方式使用 Windows 基础类 (WFC)。首先，已经实现了一组 Java 类，这些类扩展了 ADO 接口，并创建了对 Java 程序员有用的通知；这些 Java 类还公开了可以将 Java 类型返回给用户的函数。为了提高性能，Java 类可以直接访问 OLE DB 行集对象中的本机数据类型，并将它们作为 Java 类型返回给 Java 程序员，而不用将它们首先转换为变量型值，或者相反。经过扩展后，ADO 还能使用 WFC 框架中的事件通知。

ADO for Windows Foundation Classes (ADO/WFC) 支持所有标准的 ADO 方法、属性、对象和事件。但是，那些需要变量型作为参数并且在 Microsoft Visual Basic 等语言中展示了良好性能的操作，在 Visual J++ 等语言中性能却有所降低。为此，ADO/WFC 还提供了 [Field](field-object-ado.md) 对象的访问器函数，该函数采用本机 Java 数据类型而不是变量型数据类型。

若要查看 ADO 文档中有关 ADO/WFC 包的更详细信息，请参阅 [ADO/WFC 语法索引](https://msdn.microsoft.com/library/jj250066\(v=office.15\))。

## <a name="referencing-the-library"></a>引用库

若要将 ADO/WFC 数据类导入项目，请在代码中包括以下行：

```java 
 
import com.ms.wfc.data.*; 
```

