---
title: QueryDef.MaxRecords Property (DAO)
TOCTitle: MaxRecords Property
ms:assetid: 7492cde9-be30-3473-dabc-9602465910d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195877(v=office.15)
ms:contentKeyID: 48545664
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053583
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 87f193be1f7261a4aecbfe1cceb4fe5a55038702
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882103"
---
# <a name="querydefmaxrecords-property-dao"></a><span data-ttu-id="642f8-102">QueryDef.MaxRecords Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="642f8-102">QueryDef.MaxRecords Property (DAO)</span></span>


<span data-ttu-id="642f8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="642f8-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="642f8-104">设置或返回针对 ODBC 数据源的查询所返回的最大记录数。</span><span class="sxs-lookup"><span data-stu-id="642f8-104">Sets or returns the maximum number of records to return from a query against an ODBC data source.</span></span>

## <a name="syntax"></a><span data-ttu-id="642f8-105">语法</span><span class="sxs-lookup"><span data-stu-id="642f8-105">Syntax</span></span>

<span data-ttu-id="642f8-106">*表达式*。MaxRecords</span><span class="sxs-lookup"><span data-stu-id="642f8-106">*expression* .MaxRecords</span></span>

<span data-ttu-id="642f8-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="642f8-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="642f8-108">注解</span><span class="sxs-lookup"><span data-stu-id="642f8-108">Remarks</span></span>

<span data-ttu-id="642f8-109">默认值为 0，表示不限制返回记录的数目。</span><span class="sxs-lookup"><span data-stu-id="642f8-109">The default value is 0, indicating no limit on the number of records returned.</span></span>

<span data-ttu-id="642f8-p101">将 **MaxRecords** 指定的行数返回到 **[Recordset](recordset-object-dao.md)** 中的应用程序后，查询处理器将停止返回其他记录，即使有更多的记录符合列入 **Recordset** 的条件，也是如此。如果有限的客户端资源阻止了对大量记录的管理，该属性将十分有用。</span><span class="sxs-lookup"><span data-stu-id="642f8-p101">Once the number of rows specified by **MaxRecords** is returned to your application in a **[Recordset](recordset-object-dao.md)**, the query processor will stop returning additional records even if more records would qualify for inclusion in the **Recordset**. This property is useful in situations where limited client resources prohibit management of large numbers of records.</span></span>


> [!NOTE]
> <P><span data-ttu-id="642f8-112">[!注释] <STRONG>MaxRecords</STRONG> 属性只能用于 ODBC 数据源。</span><span class="sxs-lookup"><span data-stu-id="642f8-112">The <STRONG>MaxRecords</STRONG> property can only be used with an ODBC data source.</span></span></P>



## <a name="example"></a><span data-ttu-id="642f8-113">示例</span><span class="sxs-lookup"><span data-stu-id="642f8-113">Example</span></span>

<span data-ttu-id="642f8-114">以下示例使用 **MaxRecords** 属性设置对 ODBC 数据源上的查询返回的记录数的限制。</span><span class="sxs-lookup"><span data-stu-id="642f8-114">This example uses the **MaxRecords** property to set a limit on how many records are returned by a query on an ODBC data source.</span></span>

```vb 
Sub MaxRecordsX() 
 
 Dim dbsCurrent As Database 
 Dim qdfPassThrough As QueryDef 
 Dim qdfLocal As QueryDef 
 Dim rstTemp As Recordset 
 
 ' Open a database from which QueryDef objects can be 
 ' created. 
 Set dbsCurrent = OpenDatabase("DB1.mdb") 
 
 ' Create a pass-through query to retrieve data from 
 ' a Microsoft SQL Server database. 
 Set qdfPassThrough = _ 
 dbsCurrent.CreateQueryDef("") 
 
 ' Set the properties of the new query, limiting the 
 ' number of returnable records to 20. 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 qdfPassThrough.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 qdfPassThrough.SQL = "SELECT * FROM titles" 
 qdfPassThrough.ReturnsRecords = True 
 qdfPassThrough.MaxRecords = 20 
 
 Set rstTemp = qdfPassThrough.OpenRecordset() 
 
 ' Display results of query. 
 Debug.Print "Query results:" 
 With rstTemp 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 dbsCurrent.Close 
 
End Sub 
 
```

