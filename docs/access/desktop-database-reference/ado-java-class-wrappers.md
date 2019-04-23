---
title: ADO Java 类包装
TOCTitle: ADO Java class wrappers
ms:assetid: de50faf0-80f3-f295-3d9e-3f70f86c3ede
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250126(v=office.15)
ms:contentKeyID: 48548183
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 731e659f29d6fd504bab772867fb438985189e13
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283315"
---
# <a name="ado-java-class-wrappers"></a>ADO Java 类包装


**适用于**：Access 2013、Office 2013

此代码声明 ADO [Recordset](recordset-object-ado.md) 类包装实例，并将它初始化，所有步骤都在同一行代码中完成。然后，它为 [Open](open-method-ado-recordset.md) 方法中的每个参数声明变量，尤其是为 [LockType](locktype-property-ado.md) 和 [CursorType](cursortype-property-ado.md) （因为 Java 不支持枚举类型）。它将打开并关闭 **Recordset** 对象。如果将 Rs1 设置为 NULL，则只是计划该变量要在 Java 对不用的对象执行系统和间歇性释放时被释放。

```java 
 
public static void main( String args[]) 
{ 
 msado15._Recordset Rs1 = new msado15.Recordset(); 
 Variant Source = new Variant( "SELECT * FROM Authors" ); 
 Variant Connect = new Variant( "DSN=AdoDemo;UID=admin;PWD=;" ); 
 int LockType = msado15.CursorTypeEnum.adOpenForwardOnly; 
 int CursorType = msado15.LockTypeEnum.adLockReadOnly; 
 int Options = -1; 
 
 Rs1.Open( Source, Connect, LockType, CursorType, Options ); 
 Rs1.Close(); 
 Rs1 = null; 
 
 System.out.println( "Success!\n" ); 
} 
```

