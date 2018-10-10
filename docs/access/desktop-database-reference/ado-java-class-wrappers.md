---
title: ADO Java 类包装
TOCTitle: ADO Java Class Wrappers
ms:assetid: de50faf0-80f3-f295-3d9e-3f70f86c3ede
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250126(v=office.15)
ms:contentKeyID: 48548183
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fa3a4d1d2a917997b9e7ed5407d4f2ce8d1d0361
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467671"
---
# <a name="ado-java-class-wrappers"></a>ADO Java 类包装


**适用于**： Access 2013 |Office 2013

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

