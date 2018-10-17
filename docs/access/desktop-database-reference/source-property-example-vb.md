---
title: Source 属性示例 (VB)
TOCTitle: Source Property Example (VB)
ms:assetid: 7ebc5028-8a2c-51ab-a397-8a50642fabd5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249532(v=office.15)
ms:contentKeyID: 48545885
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e430f7148df45e22a09c60332dde5d8b45713c1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467844"
---
# <a name="source-property-example-vb"></a><span data-ttu-id="c6e97-102">Source 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c6e97-102">Source Property Example (VB)</span></span>


<span data-ttu-id="c6e97-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c6e97-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c6e97-104">本示例通过打开三个基于不同数据源的 [Recordset](source-property-ado-recordset.md) 对象来演示 [Source](recordset-object-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="c6e97-104">This example demonstrates the [Source](source-property-ado-recordset.md) property by opening three [Recordset](recordset-object-ado.md) objects based on different data sources.</span></span>

```vb 
 
'BeginSourceVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim Cnxn As ADODB.Connection 
 Dim rstTitles As ADODB.Recordset 
 Dim rstPublishers As ADODB.Recordset 
 Dim rstPublishersDirect As ADODB.Recordset 
 Dim rstTitlesPublishers As ADODB.Recordset 
 Dim cmdSQL As ADODB.Command 
 Dim strCnxn As String 
 Dim strSQL As String 
 
 ' Open a connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open a recordset based on a command object 
 Set cmdSQL = New ADODB.Command 
 Set cmdSQL.ActiveConnection = Cnxn 
 strSQL = "Select title, type, pubdate FROM Titles ORDER BY title" 
 cmdSQL.CommandText = strSQL 
 Set rstTitles = cmdSQL.Execute() 
 
 ' Open a recordset based on a table 
 Set rstPublishers = New ADODB.Recordset 
 strSQL = "Publishers" 
 rstPublishers.Open strSQL, Cnxn, adOpenStatic, adLockReadOnly, adCmdTable 
 'rstPublishers.Open strSQL, Cnxn, , , adCmdTable 
 ' the above two lines of code are identical 
 
 ' Open a recordset based on a table 
 Set rstPublishersDirect = New ADODB.Recordset 
 rstPublishersDirect.Open strSQL, strCnxn, , , adCmdTableDirect 
 
 ' Open a recordset based on an SQL string. 
 Set rstTitlesPublishers = New ADODB.Recordset 
 strSQL = "SELECT title_ID AS TitleID, title AS Title, " & _ 
 "publishers.pub_id AS PubID, pub_name AS PubName " & _ 
 "FROM publishers INNER JOIN Titles " & _ 
 "ON publishers.pub_id = Titles.pub_id " & _ 
 "ORDER BY Title" 
 rstTitlesPublishers.Open strSQL, strCnxn, , , adCmdText 
 
 ' Use the Source property to display the source of each recordset. 
 MsgBox "rstTitles source: " & vbCr & _ 
 rstTitles.Source & vbCr & vbCr & _ 
 "rstPublishers source: " & vbCr & _ 
 rstPublishers.Source & vbCr & vbCr & _ 
 "rstPublishersDirect source: " & vbCr & _ 
 rstPublishersDirect.Source & vbCr & vbCr & _ 
 "rstTitlesPublishers source: " & vbCr & _ 
 rstTitlesPublishers.Source 
 
 ' clean up 
 rstTitles.Close 
 rstPublishers.Close 
 rstTitlesPublishers.Close 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set rstPublishers = Nothing 
 Set rstTitlesPublishers = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstTitles Is Nothing Then 
 If rstTitles.State = adStateOpen Then rstTitles.Close 
 End If 
 Set rstTitles = Nothing 
 
 If Not rstPublishers Is Nothing Then 
 If rstPublishers.State = adStateOpen Then rstPublishers.Close 
 End If 
 Set rstPublishers = Nothing 
 
 If Not rstTitlesPublishers Is Nothing Then 
 If rstTitlesPublishers.State = adStateOpen Then rstTitlesPublishers.Close 
 End If 
 Set rstTitlesPublishers = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndSourceVB 
```
