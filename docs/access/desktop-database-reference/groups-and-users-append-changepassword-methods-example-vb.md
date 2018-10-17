---
title: Groups 和 Users 的 Append、ChangePassword 方法示例 (VB)
TOCTitle: Groups and Users Append, ChangePassword Methods Example (VB)
ms:assetid: e9ae5f1c-d1fa-ab58-c889-b4e197cecf4c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250183(v=office.15)
ms:contentKeyID: 48548445
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e312ec2bb0a3e9e3ffc04a6f03e6001430f3a97
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466105"
---
# <a name="groups-and-users-append-changepassword-methods-example-vb"></a><span data-ttu-id="f66ba-102">Groups 和 Users 的 Append、ChangePassword 方法示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="f66ba-102">Groups and Users Append, ChangePassword Methods Example (VB)</span></span>


<span data-ttu-id="f66ba-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f66ba-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f66ba-p101">本示例演示 [Groups](append-method-adox-groups.md) 的 [Append](groups-collection-adox.md) 方法，以及 [Users](append-method-adox-users.md) 的 [Append](users-collection-adox.md) 方法，演示方法为将一个新的 [Group](group-object-adox.md) 和一个新的 [User](user-object-adox.md) 添加到系统。接下来将新的 **Group** 追加到新 **User** 的 **Groups** 集合。最终结果是，将新 **User** 添加到该 **Group** 中。此外， [ChangePassword](changepassword-method-adox.md) 方法用于指定 **User** 密码。</span><span class="sxs-lookup"><span data-stu-id="f66ba-p101">This example demonstrates the [Append](append-method-adox-groups.md) method of [Groups](groups-collection-adox.md), as well as the [Append](append-method-adox-users.md) method of [Users](users-collection-adox.md) by adding a new [Group](group-object-adox.md) and a new [User](user-object-adox.md) to the system. The new **Group** is appended to the **Groups** collection of the new **User**. Consequently, the new **User** is added to the **Group**. Also, the [ChangePassword](changepassword-method-adox.md) method is used to specify the **User** password.</span></span>

```vb 
 
' BeginGroupVB 
Sub Main() 
 On Error GoTo GroupXError 
 
 Dim cat As ADOX.Catalog 
 Dim usrNew As ADOX.User 
 Dim usrLoop As ADOX.User 
 Dim grpLoop As ADOX.Group 
 
 Set cat = New ADOX.Catalog 
 
 cat.ActiveConnection = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\" & _ 
 "Microsoft Office\Office\Samples\Northwind.mdb';" & _ 
 "jet oledb:system database=" & _ 
 "'c:\Program Files\Microsoft Office\Office\system.mdw'" 
 
 With cat 
 'Create and append new group with a string. 
 .Groups.Append "Accounting" 
 
 ' Create and append new user with an object. 
 Set usrNew = New ADOX.User 
 usrNew.Name = "Pat Smith" 
 usrNew.ChangePassword "", "Password1" 
 .Users.Append usrNew 
 
 ' Make the user Pat Smith a member of the 
 ' Accounting group by creating and adding the 
 ' appropriate Group object to the user's Groups 
 ' collection. The same is accomplished if a User 
 ' object representing Pat Smith is created and 
 ' appended to the Accounting group Users collection 
 usrNew.Groups.Append "Accounting" 
 
 ' Enumerate all User objects in the 
 ' catalog's Users collection. 
 For Each usrLoop In .Users 
 Debug.Print " " & usrLoop.Name 
 Debug.Print " Belongs to these groups:" 
 ' Enumerate all Group objects in each User 
 ' object's Groups collection. 
 If usrLoop.Groups.Count <> 0 Then 
 For Each grpLoop In usrLoop.Groups 
 Debug.Print " " & grpLoop.Name 
 Next grpLoop 
 Else 
 Debug.Print " [None]" 
 End If 
 Next usrLoop 
 
 ' Enumerate all Group objects in the default 
 ' workspace's Groups collection. 
 For Each grpLoop In .Groups 
 Debug.Print " " & grpLoop.Name 
 Debug.Print " Has as its members:" 
 ' Enumerate all User objects in each Group 
 ' object's Users collection. 
 If grpLoop.Users.Count <> 0 Then 
 For Each usrLoop In grpLoop.Users 
 Debug.Print " " & usrLoop.Name 
 Next usrLoop 
 Else 
 Debug.Print " [None]" 
 End If 
 Next grpLoop 
 
 ' Delete new User and Group objects because this 
 ' is only a demonstration. 
 ' These two line are commented out because the sub "OwnersX" uses 
 ' the group "Accounting". 
' .Users.Delete "Pat Smith" 
' .Groups.Delete "Accounting" 
 
 End With 
 
 'Clean up 
 Set cat.ActiveConnection = Nothing 
 Set cat = Nothing 
 Set usrNew = Nothing 
 Exit Sub 
 
GroupXError: 
 
 Set cat = Nothing 
 Set usrNew = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
' EndGroupVB 
```
