---
title: 对行 （访问桌面数据库引用） 进行计数
TOCTitle: Counting rows
ms:assetid: ff684c5e-7f41-0dae-beea-f5c71f79bd84
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250312(v=office.15)
ms:contentKeyID: 48548963
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2388978185ac29149f7f15150ccfdbc559cc910f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701100"
---
# <a name="counting-rows"></a>统计行数


**适用于**： Access 2013、 Office 2013

**RecordCount** 属性返回一个 **长整型** 值，该值指示 **Recordset** 中的记录数。使用 **RecordCount** 属性可以确定 **Recordset** 对象中的记录数。如果 ADO 无法确定记录数，或者如果提供程序或游标类型不支持 **RecordCount** ，该属性将返回 -1。针对已关闭 **Recordset** 读取 **RecordCount** 属性会产生错误。

**RecordCount** 属性取决于提供程序功能和游标类型。对于仅向前型游标， **RecordCount** 属性将返回 -1，对于静态或键集游标将返回实际计数，对于动态游标将返回 -1 或实际计数（具体情况取决于数据源）。

该示例因为打开的仅向前型游标， **Recordset**中[检查数据](chapter-3-examining-data.md)引入将返回-1。 为了使用 **RecordCount** 属性，您需要用更复杂的游标（静态游标或键集游标）来打开 **Recordset** 。

在某些情况下，如果不首先从数据源提取所有的记录，提供程序或游标可能无法提供 **RecordCount** 值。若要强制进行此类提取，请在调用 **RecordCount** 之前调用 **Recordset** 的 **MoveLast** 方法。

如果用以下代码替换调用 **Recordset** **Open** 方法的代码行：

```vb 
 
oRs.Open sSQL, sCnStr, adOpenStatic, adLockOptimistic, adCmdText 
```

您就能够使用 **RecordCount** 属性，因为静态游标和 [Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md) 支持 **RecordCount** 。例如，以下代码将在调试窗口中显示该命令返回的记录数，假定游标支持 **RecordCount** 属性：

```vb 
 
Debug.Print oRs.RecordCount ' Output: 4 
```

此后，将假设使用这些功能更强大（但比较昂贵）的游标和锁定类型设置。

