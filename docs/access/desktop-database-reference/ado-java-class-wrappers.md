---
title: ADO Java 类包装
TOCTitle: ADO Java class wrappers
ms:assetid: de50faf0-80f3-f295-3d9e-3f70f86c3ede
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250126(v=office.15)
ms:contentKeyID: 48548183
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b10308865821f86186ff82d2362b7e6a1a7e5cde
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944555"
---
# <a name="ado-java-class-wrappers"></a><span data-ttu-id="182c7-102">ADO Java 类包装</span><span class="sxs-lookup"><span data-stu-id="182c7-102">ADO Java class wrappers</span></span>


<span data-ttu-id="182c7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="182c7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="182c7-p101">此代码声明 ADO [Recordset](recordset-object-ado.md) 类包装实例，并将它初始化，所有步骤都在同一行代码中完成。然后，它为 [Open](open-method-ado-recordset.md) 方法中的每个参数声明变量，尤其是为 [LockType](locktype-property-ado.md) 和 [CursorType](cursortype-property-ado.md) （因为 Java 不支持枚举类型）。它将打开并关闭 **Recordset** 对象。如果将 Rs1 设置为 NULL，则只是计划该变量要在 Java 对不用的对象执行系统和间歇性释放时被释放。</span><span class="sxs-lookup"><span data-stu-id="182c7-p101">This code declares an instance of the ADO [Recordset](recordset-object-ado.md) class wrapper and initializes it, all on the same line of code. Further, it declares variables for each of the arguments in the [Open](open-method-ado-recordset.md) method, especially for [LockType](locktype-property-ado.md) and [CursorType](cursortype-property-ado.md) (because Java doesn't support enumerated types). It opens and closes the **Recordset** object. Setting Rs1 to NULL merely schedules that variable to be released when Java performs its systematic and intermittent release of unused objects.</span></span>

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

