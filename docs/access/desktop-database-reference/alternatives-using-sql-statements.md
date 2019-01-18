---
title: 替代方法：使用 SQL 语句
TOCTitle: 'Alternatives: Using SQL statements'
ms:assetid: 9ed787da-7099-2ef5-b2c6-c4f6bce5ddfe
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249727(v=office.15)
ms:contentKeyID: 48546668
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 185f5c1eb7e11a9425ff6cc4a16f1387424f3219
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711348"
---
# <a name="alternatives-using-sql-statements"></a>替代方法：使用 SQL 语句


**适用于**： Access 2013、 Office 2013

ADO 还允许在编辑数据时使用命令来替代其内置属性和方法。根据您的提供程序的不同，本章提到的所有操作也可以通过将命令传递到数据源来实现。例如，可以使用 SQL UPDATE 语句修改数据，而不使用 **Field** 的 **Value** 属性。可以使用 SQL INSERT 语句向数据源添加新记录，而不使用 ADO 方法 **AddNew** 。有关 SQL 或提供程序的数据操控语言的详细信息，请参阅数据源文档。

例如，可以将包含 DELETE 语句的 SQL 字符串传递给数据库，如以下代码所示：

```vb 
'BeginSQLDelete 
strSQL = "DELETE FROM Shippers WHERE ShipperID = " & intId 
objConn.Execute strSQL, , adCmdText + adExecuteNoRecords 
'EndSQLDelete 
```

