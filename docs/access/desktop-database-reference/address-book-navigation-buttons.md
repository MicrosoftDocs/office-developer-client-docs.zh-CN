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
# <a name="address-book-navigation-buttons"></a><span data-ttu-id="41c2e-102">通讯簿导航按钮</span><span class="sxs-lookup"><span data-stu-id="41c2e-102">Address Book Navigation Buttons</span></span>


<span data-ttu-id="41c2e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="41c2e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="41c2e-p101">通讯簿应用程序在网页的底部显示导航按钮。您可以使用导航按钮，通过选择第一行或最后一行数据或与当前行相邻的行，在 HTML 网格显示中导航数据。</span><span class="sxs-lookup"><span data-stu-id="41c2e-p101">The Address Book application displays the navigation buttons at the bottom of the Web page. You can use the navigation buttons to navigate through the data in the HTML grid display by selecting either the first or last row of data, or rows adjacent to the current selection.</span></span>

## <a name="navigation-sub-procedures"></a><span data-ttu-id="41c2e-106">导航子过程</span><span class="sxs-lookup"><span data-stu-id="41c2e-106">Navigation Sub Procedures</span></span>

<span data-ttu-id="41c2e-107">通讯簿应用程序包含多个过程，允许用户通过单击**第一个**、**下一个**、**上一步**和**最后一个**按钮以在数据间移动。</span><span class="sxs-lookup"><span data-stu-id="41c2e-107">The Address Book application contains several procedures that allow users to click the **First**, **Next**, **Previous**, and **Last** buttons to move around the data.</span></span>

<span data-ttu-id="41c2e-108">例如，单击**第一个**按钮可激活 VBScript 第一个\_OnClick Sub 过程。</span><span class="sxs-lookup"><span data-stu-id="41c2e-108">For example, clicking the **First** button activates the VBScript First\_OnClick Sub procedure.</span></span> <span data-ttu-id="41c2e-109">[MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，这将使数据当前选定内容的第一行执行该过程。</span><span class="sxs-lookup"><span data-stu-id="41c2e-109">The procedure executes a [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, which makes the first row of data the current selection.</span></span> <span data-ttu-id="41c2e-110">单击**最后一个**按钮激活上次\_OnClick Sub 过程，调用[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，使当前选定内容的最后一行的数据。</span><span class="sxs-lookup"><span data-stu-id="41c2e-110">Clicking the **Last** button activates the Last\_OnClick Sub procedure, which invokes the [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, making the last row of data the current selection.</span></span> <span data-ttu-id="41c2e-111">以类似方式工作的剩余的导航按钮。</span><span class="sxs-lookup"><span data-stu-id="41c2e-111">The remaining navigation buttons work in a similar fashion.</span></span>

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

