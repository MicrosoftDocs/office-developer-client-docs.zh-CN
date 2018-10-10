---
title: CompareBookmarks 方法示例 (VB)
TOCTitle: CompareBookmarks Method Example (VB)
ms:assetid: 048c91a1-d1dd-6b8a-b602-09cdb0f8a6f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248807(v=office.15)
ms:contentKeyID: 48543012
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ac654ebb995f3b4ab9331a647b8c4da1ccc4a266
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467965"
---
# <a name="comparebookmarks-method-example-vb"></a><span data-ttu-id="0a441-102">CompareBookmarks 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="0a441-102">CompareBookmarks Method Example (VB)</span></span>


<span data-ttu-id="0a441-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0a441-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0a441-p101">以下示例展示了 [CompareBookmarks](comparebookmarks-method-ado.md) 方法。除非书签存在某些特殊之处，一般很少需要书签的相对值。</span><span class="sxs-lookup"><span data-stu-id="0a441-p101">This example demonstrates the [CompareBookmarks](comparebookmarks-method-ado.md) method. The relative value of bookmarks is seldom needed unless a particular bookmark is somehow special.</span></span>

<span data-ttu-id="0a441-p102">将派生自 ***Authors***（作者）表的 [Recordset](recordset-object-ado.md) 的随机行指定为搜索目标。然后显示每一行相对于该目标的位置。</span><span class="sxs-lookup"><span data-stu-id="0a441-p102">Designate a random row of a [Recordset](recordset-object-ado.md) derived from the ***Authors*** table as the target of a search. Then display the position of each row relative to that target.</span></span>

```vb 
 
'BeginCompareBookmarksVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' recordset and connection variables 
 Dim rstAuthors As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strSQLAuthors As String 
 Dim strCnxn As String 
 
 ' comparison variables 
 Dim count As Integer 
 Dim target As Variant 
 Dim result As Long 
 Dim strAnswer As String 
 Dim strTitle As String 
 strTitle = "CompareBookmarks Example" 
 
 ' Open a connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset as a static cursor type recordset 
 Set rstAuthors = New ADODB.Recordset 
 strSQLAuthors = "SELECT * FROM Authors" 
 rstAuthors.Open strSQLAuthors, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 count = rstAuthors.RecordCount 
 Debug.Print "Rows in the Recordset = "; count 
 
 ' Exit if an empty recordset 
 If count = 0 Then Exit Sub 
 
 ' Get position between 0 and count -1 
 Randomize 
 count = (Int(count * Rnd)) 
 Debug.Print "Randomly chosen row position = "; count 
 ' Move row to random position 
 rstAuthors.Move count, adBookmarkFirst 
 ' Remember the mystery row 
 target = rstAuthors.Bookmark 
 
 count = 0 
 rstAuthors.MoveFirst 
 ' Loop through recordset 
 Do Until rstAuthors.EOF 
 result = rstAuthors.CompareBookmarks(rstAuthors.Bookmark, target) 
 
 If result = adCompareNotEqual Then 
 Debug.Print "Row "; count; ": Bookmarks are not equal." 
 ElseIf result = adCompareNotComparable Then 
 Debug.Print "Row "; count; ": Bookmarks are not comparable." 
 Else 
 Select Case result 
 Case adCompareLessThan 
 strAnswer = "less than" 
 Case adCompareEqual 
 strAnswer = "equal to" 
 Case adCompareGreaterThan 
 strAnswer = "greater than" 
 Case Else 
 strAnswer = "in error comparing to" 
 End Select 
 'show the results row-by-row 
 Debug.Print "Row position " & count & " is " & strAnswer & " the target." 
 End If 
 
 count = count + 1 
 rstAuthors.MoveNext 
 Loop 
 
 ' clean up 
 rstAuthors.Close 
 Cnxn.Close 
 Set rstAuthors = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstAuthors Is Nothing Then 
 If rstAuthors.State = adStateOpen Then rstAuthors.Close 
 End If 
 Set rstAuthors = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
'EndCompareBookmarksVB 
```

