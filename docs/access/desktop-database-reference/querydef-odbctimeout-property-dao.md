---
title: QueryDef.ODBCTimeout 属性 (DAO)
TOCTitle: ODBCTimeout Property
ms:assetid: b251c4fb-64a8-aa95-deed-64425df3e00c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822019(v=office.15)
ms:contentKeyID: 48547166
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053052
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ceb3cf0fa2e16af4df23c6511fd6d1421487a409
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922753"
---
# <a name="querydefodbctimeout-property-dao"></a><span data-ttu-id="e3f2f-102">QueryDef.ODBCTimeout 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e3f2f-102">QueryDef.ODBCTimeout property (DAO)</span></span>


<span data-ttu-id="e3f2f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e3f2f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e3f2f-104">指示在开放式数据库连接 (ODBC) 数据库上执行 **[QueryDef](querydef-object-dao.md)** 时，发生超时错误之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-104">Indicates the number of seconds to wait before a timeout error occurs when a **[QueryDef](querydef-object-dao.md)** is executed on an ODBC database.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3f2f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e3f2f-105">Syntax</span></span>

<span data-ttu-id="e3f2f-106">*表达式*。ODBCTimeout</span><span class="sxs-lookup"><span data-stu-id="e3f2f-106">*expression* .ODBCTimeout</span></span>

<span data-ttu-id="e3f2f-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3f2f-108">注解</span><span class="sxs-lookup"><span data-stu-id="e3f2f-108">Remarks</span></span>

<span data-ttu-id="e3f2f-p101">如果 **ODBCTimeout** 属性设置为 -1，则超时默认为包含 [QueryDef](database-querytimeout-property-dao.md) 的 [**Connection**](connection-object-dao.md) 或 [**Database**](database-object-dao.md) 对象的 \*\*\*\*QueryTimeout\*\*\*\* 属性的当前设置。如果 **ODBCTimeout** 属性设置为 0，则不发生超时错误。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-p101">When the **ODBCTimeout** property is set to -1, the timeout defaults to the current setting of the **[QueryTimeout](database-querytimeout-property-dao.md)** property of the **[Connection](connection-object-dao.md)** or **[Database](database-object-dao.md)** object that contains the **QueryDef**. When the **ODBCTimeout** property is set to 0, no timeout error occurs.</span></span>

<span data-ttu-id="e3f2f-p102">如果使用的是 ODBC 数据库（如 Microsoft SQL Server），可能会由于网络阻塞或大量使用 ODBC 服务器而导致延迟。不需要无限期地等待，您可以指定返回错误前的等待时间。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-p102">When you're using an ODBC database, such as Microsoft SQL Server, delays can occur because of network traffic or heavy use of the ODBC server. Rather than waiting indefinitely, you can specify how long to wait before returning an error.</span></span>

<span data-ttu-id="e3f2f-113">设置 **QueryDef** 对象的 **ODBCTimeout** 属性将重写由包含 **QueryDef** 的 **Connection** 或 **Database** 对象的 **QueryTimeout** 属性指定的值，但这一点只适用于该 **QueryDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-113">Setting the **ODBCTimeout** property of a **QueryDef** object overrides the value specified by the **QueryTimeout** property of the **Connection** or **Database** object containing the **QueryDef**, but only for that **QueryDef** object.</span></span>

## <a name="example"></a><span data-ttu-id="e3f2f-114">示例</span><span class="sxs-lookup"><span data-stu-id="e3f2f-114">Example</span></span>

<span data-ttu-id="e3f2f-115">以下示例使用 **ODBCTimeout** 和 **QueryTimeout** 属性，演示 **Database** 对象的 **QueryTimeout** 设置如何设置从 **Database** 对象创建的任何 **QueryDef** 对象的默认 **ODBCTimeout** 设置。</span><span class="sxs-lookup"><span data-stu-id="e3f2f-115">This example uses the **ODBCTimeout** and **QueryTimeout** properties to show how the **QueryTimeout** setting on a **Database** object sets the default **ODBCTimeout** setting on any **QueryDef** objects created from the **Database** object.</span></span>

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

