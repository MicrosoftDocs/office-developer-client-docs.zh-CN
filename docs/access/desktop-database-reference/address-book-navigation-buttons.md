---
title: 通讯簿导航按钮
TOCTitle: Address Book navigation buttons
ms:assetid: 4ec32c08-5b35-8dce-23ec-0daa4db551cf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249253(v=office.15)
ms:contentKeyID: 48544765
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e7c87acd433df4a303c1e6a15a60184cadf994c3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282462"
---
# <a name="address-book-navigation-buttons"></a><span data-ttu-id="ece34-102">通讯簿导航按钮</span><span class="sxs-lookup"><span data-stu-id="ece34-102">Address Book navigation buttons</span></span>

<span data-ttu-id="ece34-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ece34-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ece34-104">通讯簿应用程序将在网页底部显示导航按钮。</span><span class="sxs-lookup"><span data-stu-id="ece34-104">The Address Book application displays the navigation buttons at the bottom of the webpage.</span></span> <span data-ttu-id="ece34-105">您可以使用导航按钮，通过选择第一行或最后一行数据或与当前行相邻的行，在 HTML 网格显示中导航数据。</span><span class="sxs-lookup"><span data-stu-id="ece34-105">You can use the navigation buttons to navigate through the data in the HTML grid display by selecting either the first or last row of data, or rows adjacent to the current selection.</span></span>

## <a name="navigation-sub-procedures"></a><span data-ttu-id="ece34-106">导航子过程</span><span class="sxs-lookup"><span data-stu-id="ece34-106">Navigation Sub Procedures</span></span>

<span data-ttu-id="ece34-107">通讯簿应用程序中包含多个过程，允许用户通过单击“第一个”\*\*\*\*、“下一个”\*\*\*\*、“上一个”\*\*\*\* 和“最后一个”\*\*\*\* 按钮在数据间移动。</span><span class="sxs-lookup"><span data-stu-id="ece34-107">The Address Book application contains several procedures that allow users to click the **First**, **Next**, **Previous**, and **Last** buttons to move around the data.</span></span>

<span data-ttu-id="ece34-108">例如, 单击**第一个**按钮将激活 VBScript 第一个\_OnClick Sub 过程。</span><span class="sxs-lookup"><span data-stu-id="ece34-108">For example, clicking the **First** button activates the VBScript First\_OnClick Sub procedure.</span></span> <span data-ttu-id="ece34-109">The procedure executes a [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, which makes the first row of data the current selection.</span><span class="sxs-lookup"><span data-stu-id="ece34-109">The procedure executes a [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, which makes the first row of data the current selection.</span></span> <span data-ttu-id="ece34-110">单击 "**上一步**" 按钮\_将激活最后一个 OnClick Sub 过程, 该过程将调用[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md)方法, 从而将最后一行数据设为当前所选内容。</span><span class="sxs-lookup"><span data-stu-id="ece34-110">Clicking the **Last** button activates the Last\_OnClick Sub procedure, which invokes the [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-rds.md) method, making the last row of data the current selection.</span></span> <span data-ttu-id="ece34-111">The remaining navigation buttons work in a similar fashion.</span><span class="sxs-lookup"><span data-stu-id="ece34-111">The remaining navigation buttons work in a similar fashion.</span></span>

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

