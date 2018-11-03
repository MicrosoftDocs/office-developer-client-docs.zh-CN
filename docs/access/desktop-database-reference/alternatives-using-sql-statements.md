---
title: 替代方法： 使用 SQL 语句
TOCTitle: 'Alternatives: Using SQL statements'
ms:assetid: 9ed787da-7099-2ef5-b2c6-c4f6bce5ddfe
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249727(v=office.15)
ms:contentKeyID: 48546668
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4bcda13d8b785f1048890d1ed9492f5da3e7288b
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945556"
---
# <a name="alternatives-using-sql-statements"></a><span data-ttu-id="036c5-102">替代方法： 使用 SQL 语句</span><span class="sxs-lookup"><span data-stu-id="036c5-102">Alternatives: Using SQL statements</span></span>


<span data-ttu-id="036c5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="036c5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="036c5-p101">ADO 还允许在编辑数据时使用命令来替代其内置属性和方法。根据您的提供程序的不同，本章提到的所有操作也可以通过将命令传递到数据源来实现。例如，可以使用 SQL UPDATE 语句修改数据，而不使用 **Field** 的 **Value** 属性。可以使用 SQL INSERT 语句向数据源添加新记录，而不使用 ADO 方法 **AddNew** 。有关 SQL 或提供程序的数据操控语言的详细信息，请参阅数据源文档。</span><span class="sxs-lookup"><span data-stu-id="036c5-p101">ADO also allows using commands as alternatives to its built-in properties and methods for editing data. Depending upon your provider, all operations mentioned in this chapter could also be accomplished by passing commands to your data source. For example, SQL UPDATE statements can be used to modify data without using the **Value** property of a **Field**. SQL INSERT statements can be used to add new records to a data source, rather than the ADO method **AddNew**. For more information about SQL or the data-manipulation language of your provider, see the documentation of your data source.</span></span>

<span data-ttu-id="036c5-109">例如，可以将包含 DELETE 语句的 SQL 字符串传递给数据库，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="036c5-109">For example, you can pass a SQL string containing a DELETE statement to a database, as shown in the following code:</span></span>

```vb 
'BeginSQLDelete 
strSQL = "DELETE FROM Shippers WHERE ShipperID = " & intId 
objConn.Execute strSQL, , adCmdText + adExecuteNoRecords 
'EndSQLDelete 
```

