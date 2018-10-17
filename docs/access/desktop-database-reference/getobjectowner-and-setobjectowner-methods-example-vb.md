---
title: GetObjectOwner 和 SetObjectOwner 方法示例 (VB)
TOCTitle: GetObjectOwner and SetObjectOwner Methods Example (VB)
ms:assetid: 0a30cce1-7626-8db3-4af4-84098c284db0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248833(v=office.15)
ms:contentKeyID: 48543146
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 720eaf7d4ba4a73a85f392d33244369ae96a75b6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467247"
---
# <a name="getobjectowner-and-setobjectowner-methods-example-vb"></a><span data-ttu-id="8b192-102">GetObjectOwner 和 SetObjectOwner 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="8b192-102">GetObjectOwner and SetObjectOwner Methods Example (VB)</span></span>


<span data-ttu-id="8b192-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b192-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8b192-p101">本示例演示 [GetObjectOwner](getobjectowner-method-adox.md) 和 [SetObjectOwner](https://msdn.microsoft.com/library/jj249006\(v=office.15\)) 方法。此代码假设存在 Accounting 组（请参阅 [Groups 和 Users 的 Append、ChangePassword 方法示例 (VB)](groups-and-users-append-changepassword-methods-example-vb.md) 以了解如何将该组添加到系统）。Categories（类别）表的所有者设置为 Accounting。</span><span class="sxs-lookup"><span data-stu-id="8b192-p101">This example demonstrates the [GetObjectOwner](getobjectowner-method-adox.md) and [SetObjectOwner](https://msdn.microsoft.com/library/jj249006\(v=office.15\)) methods. This code assumes the existence of the group Accounting (see the [Groups and Users Append, ChangePassword Methods Example (VB)](groups-and-users-append-changepassword-methods-example-vb.md) to see how to add this group to the system). The owner of the Categories table is set to Accounting.</span></span>

```vb 
 
' BeginOwnersVB 
Sub Main() 
 On Error GoTo OwnersXError 
 
 Dim tblLoop As New ADOX.Table 
 Dim cat As New ADOX.Catalog 
 Dim strOwner As String 
 
 ' Open the Catalog. 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" & _ 
 "jet oledb:system database=" & _ 
 "'c:\Program Files\Microsoft Office\Office\system.mdw'" 
 
 ' Print the original owner of Categories 
 strOwner = cat.GetObjectOwner("Categories", adPermObjTable) 
 Debug.Print "Owner of Categories: " & strOwner 
 
 ' Set the owner of Categories to Accounting 
 cat.SetObjectOwner "Categories", adPermObjTable, "Accounting" 
 
 ' List the owners of all tables and columns in the catalog. 
 For Each tblLoop In cat.Tables 
 Debug.Print "Table: " & tblLoop.Name 
 Debug.Print " Owner: " & _ 
 cat.GetObjectOwner(tblLoop.Name, adPermObjTable) 
 Next tblLoop 
 
 ' Restore the original owner of Categories 
 cat.SetObjectOwner "Categories", adPermObjTable, strOwner 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Exit Sub 
 
OwnersXError: 
 
 Set cat = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
 
End Sub 
' EndOwnersVB 
```
