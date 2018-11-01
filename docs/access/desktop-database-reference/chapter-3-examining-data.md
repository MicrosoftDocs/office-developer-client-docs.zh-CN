---
title: 第 3 章：检查数据
TOCTitle: 'Chapter 3: Examining Data'
ms:assetid: 73c69134-3127-3344-d5c3-5ecb9e0e958b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249474(v=office.15)
ms:contentKeyID: 48545648
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b5542b465cc6fc31949f2ceb5ed8bda408b1e653
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875929"
---
# <a name="chapter-3-examining-data"></a>第 3 章：检查数据


**适用于**： Access 2013、 Office 2013

第 2 章介绍了如何从作为 **Recordset** 对象的数据源中检索数据。本章将更深入地讨论 **Recordset** ，包括如何在 **Recordset** 中导航并查看其中的数据。

**Recordsets** 具有旨在便于浏览和查看其中内容的方法和属性。取决于提供程序支持的功能，某些 **Recordset** 方法或属性可能不可用。若要继续研究 **Recordset** 对象，请考虑将从 Microsoft SQL Server 2000 上的罗斯文示例数据库返回的 **Recordset** ，使用以下代码：

```vb 
 
'BeginRsTour 
Public Sub RecordsetTour() 
 On Error GoTo ErrHandler: 
 
 Dim objRs As New ADODB.Recordset 
 Dim strSQL As String 
 
 strSQL = "SELECT ProductID, ProductName, UnitPrice FROM Products " & _ 
 "WHERE CategoryID = 7" '7 = Produce 
 
 objRs.Open strSQL, strConnStr, adOpenForwardOnly, _ 
 adLockReadOnly, adCmdText 
 
 'Clean up 
 objRs.Close 
 Set objRs = Nothing 
 Exit Sub 
 
ErrHandler: 
 If Not objRs Is Nothing Then 
 If objRs.State = adStateOpen Then objRs.Close 
 Set objRs = Nothing 
 End If 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndRsTour 
```

以下 SQL 查询返回一个具有五行（记录）和三列（字段）的 **Recordset** 。下表中显示了各行的值。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>字段 0<br />
名称 = 产品 Id</p></th>
<th><p>字段 1<br />
名称 = 产品名</p></th>
<th><p>字段 2<br />
名称 = 单价</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>7</p></td>
<td><p>海鲜粉</p></td>
<td><p>30.0000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>沙茶</p></td>
<td><p>23.2500</p></td>
</tr>
<tr class="odd">
<td><p>28</p></td>
<td><p>烤肉酱</p></td>
<td><p>45.6000</p></td>
</tr>
<tr class="even">
<td><p>51</p></td>
<td><p>猪肉干</p></td>
<td><p>53.0000</p></td>
</tr>
<tr class="odd">
<td><p>74</p></td>
<td><p>鸡精</p></td>
<td><p>10.0000</p></td>
</tr>
</tbody>
</table>


下一节介绍如何在此示例**Recordset**中找到指针的当前位置。

本章包含以下主题：

  - [Locating the Current Record (ADO)](locating-the-current-record.md)

  - [Navigating Through the Data (ADO)](navigating-through-the-data.md)

  - [Understanding Recordset Structure (ADO)](understanding-recordset-structure.md)