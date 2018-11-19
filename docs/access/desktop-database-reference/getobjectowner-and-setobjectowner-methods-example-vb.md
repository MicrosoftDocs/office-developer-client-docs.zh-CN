---
title: GetObjectOwner 和 SetObjectOwner 方法示例 (VB)
TOCTitle: GetObjectOwner and SetObjectOwner methods example (VB)
ms:assetid: 0a30cce1-7626-8db3-4af4-84098c284db0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248833(v=office.15)
ms:contentKeyID: 48543146
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ec71ee93a0c513b9a613c9f1c1a8a6b7d39a6d4e
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025887"
---
# <a name="getobjectowner-and-setobjectowner-methods-example-vb"></a><span data-ttu-id="9f8f8-102">GetObjectOwner 和 SetObjectOwner 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="9f8f8-102">GetObjectOwner and SetObjectOwner methods example (VB)</span></span>


<span data-ttu-id="9f8f8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9f8f8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9f8f8-104">本示例演示 [GetObjectOwner](getobjectowner-method-adox.md) 和 [SetObjectOwner](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/setobjectowner-method-adox) 方法。</span><span class="sxs-lookup"><span data-stu-id="9f8f8-104">This example demonstrates the [GetObjectOwner](getobjectowner-method-adox.md) and [SetObjectOwner](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/setobjectowner-method-adox) methods.</span></span> <span data-ttu-id="9f8f8-105">此代码假定存在的组 Accounting （请参阅[组和用户 Append、 ChangePassword 方法示例 (VB)](groups-and-users-append-changepassword-methods-example-vb.md)以了解如何将该组添加到系统）。</span><span class="sxs-lookup"><span data-stu-id="9f8f8-105">This code assumes the existence of the group Accounting (see the [Groups and Users Append, ChangePassword methods example (VB)](groups-and-users-append-changepassword-methods-example-vb.md) to see how to add this group to the system).</span></span> <span data-ttu-id="9f8f8-106">Categories（类别）表的所有者设置为 Accounting。</span><span class="sxs-lookup"><span data-stu-id="9f8f8-106">The owner of the Categories table is set to Accounting.</span></span>

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

