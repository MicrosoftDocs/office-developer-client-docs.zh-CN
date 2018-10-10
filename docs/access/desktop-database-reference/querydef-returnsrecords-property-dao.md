---
title: QueryDef.ReturnsRecords Property (DAO)
TOCTitle: ReturnsRecords Property
ms:assetid: 3d1e538b-4d60-588f-4a20-89f1e2b434e6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192701(v=office.15)
ms:contentKeyID: 48544334
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053005
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f1d10a8e348021d88510519c61825714ca434b3b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467311"
---
# <a name="querydefreturnsrecords-property-dao"></a><span data-ttu-id="ac954-102">QueryDef.ReturnsRecords Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="ac954-102">QueryDef.ReturnsRecords Property (DAO)</span></span>


<span data-ttu-id="ac954-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ac954-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="ac954-104">设置或返回一个值，该值指示针对外部数据库的 SQL 传递查询是否返回记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ac954-104">Sets or returns a value that indicates whether an SQL pass-through query to an external database returns records (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="ac954-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac954-105">Syntax</span></span>

<span data-ttu-id="ac954-106">*表达式*。ReturnsRecords</span><span class="sxs-lookup"><span data-stu-id="ac954-106">*expression* .ReturnsRecords</span></span>

<span data-ttu-id="ac954-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ac954-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac954-108">注解</span><span class="sxs-lookup"><span data-stu-id="ac954-108">Remarks</span></span>

<span data-ttu-id="ac954-p101">并非所有针对外部数据库的 SQL 传递查询都返回记录。例如，SQL UPDATE 语句更新记录但不返回记录，而 SQL SELECT 语句则返回记录。如果查询返回记录，则将 **ReturnsRecords** 属性设置为 **True**；如果查询不返回记录，则 **ReturnsRecords** 属性设置为 **False**。</span><span class="sxs-lookup"><span data-stu-id="ac954-p101">Not all SQL pass-through queries to external databases return records. For example, an SQL UPDATE statement updates records without returning records, while an SQL SELECT statement does return records. If the query returns records, set the **ReturnsRecords** property to **True**; if the query doesn't return records, set the **ReturnsRecords** property to **False**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="ac954-112">[!注释] 在设置 <A href="querydef-connect-property-dao.md">ReturnsRecords</A> 属性之前，必须先设置 <STRONG><STRONG>Connect</STRONG></STRONG> 属性。</span><span class="sxs-lookup"><span data-stu-id="ac954-112">You must set the <STRONG><A href="querydef-connect-property-dao.md">Connect</A></STRONG> property before you set the <STRONG>ReturnsRecords</STRONG> property.</span></span></P>



## <a name="example"></a><span data-ttu-id="ac954-113">示例</span><span class="sxs-lookup"><span data-stu-id="ac954-113">Example</span></span>

<span data-ttu-id="ac954-p102">以下示例使用 **Connect** 和 **ReturnsRecords** 属性，从 Microsoft SQL Server 数据库中选择年初至今销售额排行前五名的书名。如果销售额中有精确匹配，该示例将增加显示查询结果的列表的大小，并输出相应的消息来说明出现这一情况的原因。</span><span class="sxs-lookup"><span data-stu-id="ac954-p102">This example uses the **Connect** and **ReturnsRecords** properties to select the top five book titles from a Microsoft SQL Server database based on year-to-date sales amounts. In the event of an exact match in sales amounts, the example increases the size of the list displaying the results of the query and prints a message explaining why this occurred.</span></span>

```vb 
Sub ClientServerX1() 
 
 Dim dbsCurrent As Database 
 Dim qdfPassThrough As QueryDef 
 Dim qdfLocal As QueryDef 
 Dim rstTopFive As Recordset 
 Dim strMessage As String 
 
 ' Open a database from which QueryDef objects can be 
 ' created. 
 Set dbsCurrent = OpenDatabase("DB1.mdb") 
 
 ' Create a pass-through query to retrieve data from 
 ' a Microsoft SQL Server database. 
 Set qdfPassThrough = _ 
 dbsCurrent.CreateQueryDef("AllTitles") 
 ' Note: The DSN referenced below must be set to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 qdfPassThrough.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 qdfPassThrough.SQL = "SELECT * FROM titles " & _ 
 "ORDER BY ytd_sales DESC" 
 qdfPassThrough.ReturnsRecords = True 
 
 ' Create a temporary QueryDef object to retrieve 
 ' data from the pass-through query. 
 Set qdfLocal = dbsCurrent.CreateQueryDef("") 
 qdfLocal.SQL = "SELECT TOP 5 title FROM AllTitles" 
 
 Set rstTopFive = qdfLocal.OpenRecordset() 
 
 ' Display results of queries. 
 With rstTopFive 
 strMessage = _ 
 "Our top 5 best-selling books are:" & vbCr 
 
 Do While Not .EOF 
 strMessage = strMessage & " " & !Title & _ 
 vbCr 
 .MoveNext 
 Loop 
 
 If .RecordCount > 5 Then 
 strMessage = strMessage & _ 
 "(There was a tie, resulting in " & _ 
 vbCr & .RecordCount & _ 
 " books in the list.)" 
 End If 
 
 MsgBox strMessage 
 .Close 
 End With 
 
 ' Delete new pass-through query because this is a 
 ' demonstration. 
 dbsCurrent.QueryDefs.Delete "AllTitles" 
 dbsCurrent.Close 
 
```

<span data-ttu-id="ac954-116">以下示例使用 **ReturnsRecords** 属性和自定义 **LogMessages** 属性来创建传递查询，该查询将返回数据以及远程服务器生成的任何消息。</span><span class="sxs-lookup"><span data-stu-id="ac954-116">This example uses the **ReturnsRecords** property and the custom **LogMessages** property to create a pass-through query that will return data and any messages generated by the remote server.</span></span>

```vb 
Sub LogMessagesX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsCurrent As Database 
 Dim qdfTemp As QueryDef 
 Dim prpNew As Property 
 Dim rstTemp As Recordset 
 
 ' Create Microsoft Access Workspace object. 
 Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
 
 Set dbsCurrent = wrkAcc.OpenDatabase("DB1.mdb") 
 
 ' Create a QueryDef that will log any messages from the 
 ' server in temporary tables. 
 Set qdfTemp = dbsCurrent.CreateQueryDef("NewQueryDef") 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 qdfTemp.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 qdfTemp.SQL = "SELECT * FROM stores" 
 qdfTemp.ReturnsRecords = True 
 Set prpNew = qdfTemp.CreateProperty("LogMessages", _ 
 dbBoolean, True) 
 qdfTemp.Properties.Append prpNew 
 
 ' Execute query and display results. 
 Set rstTemp = qdfTemp.OpenRecordset() 
 
 Debug.Print "Contents of recordset:" 
 With rstTemp 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 ' Delete new QueryDef because this is a demonstration. 
 dbsCurrent.QueryDefs.Delete qdfTemp.Name 
 dbsCurrent.Close 
 wrkAcc.Close 
 
End Sub 
 
```

