---
title: 通讯簿导航按钮
TOCTitle: Address Book Navigation Buttons
ms:assetid: 4ec32c08-5b35-8dce-23ec-0daa4db551cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249253(v=office.15)
ms:contentKeyID: 48544765
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9f37a188fd3ddb3608eda414fbdcea6402cd9d41
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603943"
---
# <a name="address-book-navigation-buttons"></a><span data-ttu-id="051c9-102">通讯簿导航按钮</span><span class="sxs-lookup"><span data-stu-id="051c9-102">Address Book Navigation Buttons</span></span>


<span data-ttu-id="051c9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="051c9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="051c9-104"><<<<<<< 标头的通讯簿应用程序底部的 Web 页上显示的导航按钮。</span><span class="sxs-lookup"><span data-stu-id="051c9-104"><<<<<<< HEAD The Address Book application displays the navigation buttons at the bottom of the Web page.</span></span> <span data-ttu-id="051c9-105">您可以使用导航按钮，通过选择第一行或最后一行数据或与当前行相邻的行，在 HTML 网格显示中导航数据。</span><span class="sxs-lookup"><span data-stu-id="051c9-105">You can use the navigation buttons to navigate through the data in the HTML grid display by selecting either the first or last row of data, or rows adjacent to the current selection.</span></span>
<span data-ttu-id="051c9-106">=== 通讯簿应用程序的网页底部显示的导航按钮。</span><span class="sxs-lookup"><span data-stu-id="051c9-106">======= The Address Book application displays the navigation buttons at the bottom of the webpage.</span></span> <span data-ttu-id="051c9-107">您可以使用导航按钮，通过选择第一行或最后一行数据或与当前行相邻的行，在 HTML 网格显示中导航数据。</span><span class="sxs-lookup"><span data-stu-id="051c9-107">You can use the navigation buttons to navigate through the data in the HTML grid display by selecting either the first or last row of data, or rows adjacent to the current selection.</span></span>
>>>>>>> <span data-ttu-id="051c9-108">master</span><span class="sxs-lookup"><span data-stu-id="051c9-108">master</span></span>

## <a name="navigation-sub-procedures"></a><span data-ttu-id="051c9-109">导航子过程</span><span class="sxs-lookup"><span data-stu-id="051c9-109">Navigation Sub Procedures</span></span>

<span data-ttu-id="051c9-110">通讯簿应用程序包含多个过程，允许用户通过单击**第一个**、**下一个**、**上一步**和**最后一个**按钮以在数据间移动。</span><span class="sxs-lookup"><span data-stu-id="051c9-110">The Address Book application contains several procedures that allow users to click the **First**, **Next**, **Previous**, and **Last** buttons to move around the data.</span></span>

<span data-ttu-id="051c9-111">例如，单击**第一个**按钮可激活 VBScript 第一个\_OnClick Sub 过程。</span><span class="sxs-lookup"><span data-stu-id="051c9-111">For example, clicking the **First** button activates the VBScript First\_OnClick Sub procedure.</span></span> <span data-ttu-id="051c9-112">[MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，这将使数据当前选定内容的第一行执行该过程。</span><span class="sxs-lookup"><span data-stu-id="051c9-112">The procedure executes a [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, which makes the first row of data the current selection.</span></span> <span data-ttu-id="051c9-113">单击**最后一个**按钮激活上次\_OnClick Sub 过程，调用[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法，使当前选定内容的最后一行的数据。</span><span class="sxs-lookup"><span data-stu-id="051c9-113">Clicking the **Last** button activates the Last\_OnClick Sub procedure, which invokes the [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, making the last row of data the current selection.</span></span> <span data-ttu-id="051c9-114">以类似方式工作的剩余的导航按钮。</span><span class="sxs-lookup"><span data-stu-id="051c9-114">The remaining navigation buttons work in a similar fashion.</span></span>

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

