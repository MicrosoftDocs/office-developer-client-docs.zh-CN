---
title: 通讯簿导航按钮
TOCTitle: Address Book Navigation Buttons
ms:assetid: 4ec32c08-5b35-8dce-23ec-0daa4db551cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249253(v=office.15)
ms:contentKeyID: 48544765
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3d68a15873bc5030fd51e54c2219a0ffd91f080f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467678"
---
# <a name="address-book-navigation-buttons"></a>通讯簿导航按钮


**适用于**： Access 2013 |Office 2013

通讯簿应用程序在网页的底部显示导航按钮。您可以使用导航按钮，通过选择第一行或最后一行数据或与当前行相邻的行，在 HTML 网格显示中导航数据。

## <a name="navigation-sub-procedures"></a>导航子过程

通讯簿应用程序包含多个过程，允许用户通过单击**第一个**、**下一个**、**上一步**和**最后一个**按钮以在数据间移动。

例如，单击**第一个**按钮可激活 VBScript 第一个\_OnClick Sub 过程。 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，这将使数据当前选定内容的第一行执行该过程。 单击**最后一个**按钮激活上次\_OnClick Sub 过程，调用[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，使当前选定内容的最后一行的数据。 以类似方式工作的剩余的导航按钮。

```vb 
 
' Move to the first record in the bound Recordset. 
Sub First_OnClick 
 DC1.Recordset.MoveFirst 
End Sub 
 
' Move to the next record from the current position 
' in the bound Recordset. 
Sub Next_OnClick 
 If Not DC1.Recordset.EOF Then ' Cannot move beyond bottom record. 
 DC1.Recordset.MoveNext 
 Exit Sub 
 End If 
End Sub 
 
' Move to the previous record from the current position in the bound 
' Recordset. 
Sub Prev_OnClick 
 If Not DC1.Recordset.BOF Then ' Cannot move beyond top record. 
 DC1.Recordset.MovePrevious 
 Exit Sub 
 End If 
End Sub 
 
' Move to the last record in the bound Recordset. 
Sub Last_OnClick 
 DC1.Recordset.MoveLast 
End Sub 
```

