---
title: Database.QueryTimeout 属性 (DAO)
TOCTitle: QueryTimeout Property
ms:assetid: c83ca852-715a-c853-429b-80a15c3fc39b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823170(v=office.15)
ms:contentKeyID: 48547648
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d928864d729cdfb40f44d496e983bf86413d57f7
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925273"
---
# <a name="databasequerytimeout-property-dao"></a><span data-ttu-id="f70ed-102">Database.QueryTimeout 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f70ed-102">Database.QueryTimeout property (DAO)</span></span>


<span data-ttu-id="f70ed-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f70ed-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="f70ed-104">设置或返回一个值，该值指定对 ODBC 数据源执行查询时发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="f70ed-104">Sets or returns a value that specifies the number of seconds to wait before a timeout error occurs when a query is executed on an ODBC data source.</span></span>

## <a name="syntax"></a><span data-ttu-id="f70ed-105">语法</span><span class="sxs-lookup"><span data-stu-id="f70ed-105">Syntax</span></span>

<span data-ttu-id="f70ed-106">*表达式*。QueryTimeout</span><span class="sxs-lookup"><span data-stu-id="f70ed-106">*expression* .QueryTimeout</span></span>

<span data-ttu-id="f70ed-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f70ed-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f70ed-108">注解</span><span class="sxs-lookup"><span data-stu-id="f70ed-108">Remarks</span></span>

<span data-ttu-id="f70ed-109">默认值为 60。</span><span class="sxs-lookup"><span data-stu-id="f70ed-109">The default value is 60.</span></span>

<span data-ttu-id="f70ed-p101">在使用 ODBC 数据库（如 Microsoft SQL Server）时，由于网络阻塞或频繁使用 ODBC 服务器的原因，可能会有延迟。不需要无限期地等待，您可以指定等待时间。</span><span class="sxs-lookup"><span data-stu-id="f70ed-p101">When you're using an ODBC database, such as Microsoft SQL Server, there may be delays due to network traffic or heavy use of the ODBC server. Rather than waiting indefinitely, you can specify how long to wait.</span></span>

<span data-ttu-id="f70ed-p102">将 **QueryTimeout** 用于 **[Connection](connection-object-dao.md)** 或 **[Database](database-object-dao.md)** 对象时，它为所有与数据库关联的查询指定了全局值。可以通过设置特定 [**QueryDef**](querydef-object-dao.md) 对象的 **ODBCTimeout** 属性来重写特定查询的这个值。</span><span class="sxs-lookup"><span data-stu-id="f70ed-p102">When you use **QueryTimeout** with a **[Connection](connection-object-dao.md)** or **[Database](database-object-dao.md)** object, it specifies a global value for all queries associated with the database. You can override this value for a specific query by setting the **ODBCTimeout** property of the particular **[QueryDef](querydef-object-dao.md)** object.</span></span>

## <a name="example"></a><span data-ttu-id="f70ed-114">示例</span><span class="sxs-lookup"><span data-stu-id="f70ed-114">Example</span></span>

<span data-ttu-id="f70ed-115">以下示例使用 **ODBCTimeout** 和 **QueryTimeout** 属性，演示 **Database** 对象的 **QueryTimeout** 设置如何设置从 **Database** 对象创建的任何 **QueryDef** 对象的默认 **ODBCTimeout** 设置。</span><span class="sxs-lookup"><span data-stu-id="f70ed-115">This example uses the **ODBCTimeout** and **QueryTimeout** properties to show how the **QueryTimeout** setting on a **Database** object sets the default **ODBCTimeout** setting on any **QueryDef** objects created from the **Database** object.</span></span>

```vb 
Sub ODBCTimeoutX() 
 
 Dim dbsCurrent As Database 
 Dim qdfStores As QueryDef 
 Dim rstStores As Recordset 
 
 Set dbsCurrent = OpenDatabase("Northwind.mdb") 
 
 ' Change the default QueryTimeout of the Northwind 
 ' database. 
 Debug.Print "Default QueryTimeout of Database: " & _ 
 dbsCurrent.QueryTimeout 
 dbsCurrent.QueryTimeout = 30 
 Debug.Print "New QueryTimeout of Database: " & _ 
 dbsCurrent.QueryTimeout 
 
 ' Create a new QueryDef object. 
 Set qdfStores = dbsCurrent.CreateQueryDef("Stores", _ 
 "SELECT * FROM stores") 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the SQL Server. 
 qdfStores.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 
 ' Change the ODBCTimeout setting of the new QueryDef 
 ' object from its default setting. 
 Debug.Print "Default ODBCTimeout of QueryDef: " & _ 
 qdfStores.ODBCTimeout 
 qdfStores.ODBCTimeout = 0 
 Debug.Print "New ODBCTimeout of QueryDef: " & _ 
 qdfStores.ODBCTimeout 
 
 ' Execute the query and display the results. 
 Set rstStores = qdfStores.OpenRecordset() 
 
 Debug.Print "Contents of recordset:" 
 With rstStores 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 ' Delete new QueryDef because this is a demonstration. 
 dbsCurrent.QueryDefs.Delete qdfStores.Name 
 dbsCurrent.Close 
 
End Sub 
 
```

