---
title: Filter 和 RecordCount 属性示例 (VB)
TOCTitle: Filter and RecordCount properties example (VB)
ms:assetid: 3da4623e-03e7-27ac-7351-3b22415be0b9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249167(v=office.15)
ms:contentKeyID: 48544354
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f892349d2ddb9c8fc5063d3fbec37ca9ef0d469f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292480"
---
# <a name="filter-and-recordcount-properties-example-vb"></a><span data-ttu-id="b62ba-102">Filter 和 RecordCount 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="b62ba-102">Filter and RecordCount properties example (VB)</span></span>


<span data-ttu-id="b62ba-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b62ba-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b62ba-104">本示例打开 **Pubs** 数据库 Publishers（发行商）表上的一个 ***Recordset***。</span><span class="sxs-lookup"><span data-stu-id="b62ba-104">This example open a **Recordset** on the Publishers table in the ***Pubs*** database.</span></span> <span data-ttu-id="b62ba-105">然后使用 [Filter](filter-property-ado.md) 属性将可见的记录数限制为发行商属于特定国家/地区的记录。</span><span class="sxs-lookup"><span data-stu-id="b62ba-105">It then uses the [Filter](filter-property-ado.md) property to limit the number of visible records to those publishers in a particular country/region.</span></span> <span data-ttu-id="b62ba-106">**RecordCount** 属性用于显示筛选和未筛选的记录集之间的差值。</span><span class="sxs-lookup"><span data-stu-id="b62ba-106">The **RecordCount** property is used to show the difference between the filtered and unfiltered recordsets.</span></span>

```vb 
 
'BeginFilterVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' recordset variables 
 Dim rstPublishers As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim SQLPublishers As String 
 
 ' criteria variables 
 Dim intPublisherCount As Integer 
 Dim strCountry As String 
 Dim strMessage As String 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open recordset with data from Publishers table 
 Set rstPublishers = New ADODB.Recordset 
 SQLPublishers = "publishers" 
 rstPublishers.Open SQLPublishers, strCnxn, adOpenStatic, , adCmdTable 
 
 intPublisherCount = rstPublishers.RecordCount 
 
 ' get user input 
 strCountry = Trim(InputBox("Enter a country to filter on (e.g. USA):")) 
 
 If strCountry <> "" Then 
 ' open a filtered Recordset object 
 rstPublishers.Filter = "Country ='" & strCountry & "'" 
 
 If rstPublishers.RecordCount = 0 Then 
 MsgBox "No publishers from that country." 
 Else 
 ' print number of records for the original recordset 
 ' and the filtered recordset 
 strMessage = "Orders in original recordset: " & _ 
 vbCr & intPublisherCount & vbCr & _ 
 "Orders in filtered recordset (Country = '" & _ 
 strCountry & "'): " & vbCr & _ 
 rstPublishers.RecordCount 
 MsgBox strMessage 
 End If 
 End If 
 
 ' clean up 
 rstPublishers.Close 
 Cnxn.Close 
 Set rstPublishers = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstPublishers Is Nothing Then 
 If rstPublishers.State = adStateOpen Then rstPublishers.Close 
 End If 
 Set rstPublishers = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
'EndFilterVB 
```


> [!NOTE]
> <span data-ttu-id="b62ba-p102">[!注释] 如果知道要选择的数据，通过这种方式打开 **Recordset** 通过比使用 SQL 语句效率更高。本示例演示如何仅创建一个 **Recordset** 并获取特定国家/地区的记录。</span><span class="sxs-lookup"><span data-stu-id="b62ba-p102">When you know the data you want to select, it's usually more efficient to open a **Recordset** with an SQL statement. This example shows how you can create just one **Recordset** and obtain records from a particular country/region.</span></span>



```vb 
 
'BeginFilter2VB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim rstPublishers As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strSQLPublishers As String 
 Dim strCnxn As String 
 
 ' open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open recordset with criteria from Publishers table 
 Set rstPublishers = New ADODB.Recordset 
 strSQLPublishers = "SELECT * FROM publishers WHERE Country = 'USA'" 
 rstPublishers.Open strSQLPublishers, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 ' print recordset 
 rstPublishers.MoveFirst 
 Do While Not rstPublishers.EOF 
 Debug.Print rstPublishers!pub_name & ", " & rstPublishers!country 
 rstPublishers.MoveNext 
 Loop 
 
 ' clean up 
 rstPublishers.Close 
 Cnxn.Close 
 Set rstPublishers = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstPublishers Is Nothing Then 
 If rstPublishers.State = adStateOpen Then rstPublishers.Close 
 End If 
 Set rstPublishers = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndFilter2VB 
```

