---
title: WorkflowTasks 宏操作
TOCTitle: WorkflowTasks Macro Action
ms:assetid: 4b299681-b45b-f6d1-2cfe-ebf01712bfc1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193503(v=office.15)
ms:contentKeyID: 48544684
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm8454
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 29bd256c08a3b7c650609bc9b365436e5d332b8d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466869"
---
# <a name="workflowtasks-macro-action"></a><span data-ttu-id="0ed9a-102">WorkflowTasks 宏操作</span><span class="sxs-lookup"><span data-stu-id="0ed9a-102">WorkflowTasks Macro Action</span></span>


<span data-ttu-id="0ed9a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0ed9a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0ed9a-104">可以使用 **WorkflowTasks** 操作显示 **"工作流任务"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-104">You can use the **WorkflowTasks** action to display the **Workflow Task** dialog box.</span></span>

## <a name="setting"></a><span data-ttu-id="0ed9a-105">设置</span><span class="sxs-lookup"><span data-stu-id="0ed9a-105">Setting</span></span>

<span data-ttu-id="0ed9a-106">**WorkflowTasks** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-106">The **WorkflowTasks** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0ed9a-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="0ed9a-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="0ed9a-108">说明</span><span class="sxs-lookup"><span data-stu-id="0ed9a-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ed9a-109"><strong>记录号</strong></span><span class="sxs-lookup"><span data-stu-id="0ed9a-109"><strong>Record Number</strong></span></span></p></td>
<td><p><span data-ttu-id="0ed9a-110">在 Microsoft SharePoint Foundation 列表中，启动与列表中的第一项<strong>1</strong> 、 <strong>2</strong>的第二个项目，依次类推项的位置。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-110">The position of the item in the Microsoft SharePoint Foundation list, starting with <strong>1</strong> for the first item in the list, <strong>2</strong> for the second item, and so on.</span></span> <span data-ttu-id="0ed9a-111">您还可以输入一个表达式为此参数。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-111">You can also enter an expression for this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="0ed9a-112">说明</span><span class="sxs-lookup"><span data-stu-id="0ed9a-112">Remarks</span></span>

  - <span data-ttu-id="0ed9a-p102">**WorkflowTasks** 操作可打开 **"工作流任务"** 对话框。此对话框显示可用于指定的项的所有任务。必须为 SharePoint Foundation 中的列表定义工作流。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-p102">The **WorkflowTasks** action opens the **Workflow Tasks** dialog box. This dialog box displays all tasks that are available for the specified item. A workflow must be defined for the list in SharePoint Foundation.</span></span>

  - <span data-ttu-id="0ed9a-p103">只有在打开并选择了链接的 SharePoint Foundation 列表后，才可以使用 **WorkflowTasks** 操作。若要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-p103">The **WorkflowTasks** action can only be used after a linked SharePoint Foundation list has been opened and selected. To open and select the linked list, use the **OpenTable** action. If the list is already open, use the **SelectObject** action to select it.</span></span>

  - <span data-ttu-id="0ed9a-119">**WorkflowTasks** 操作等效于以下操作：当链接的 SharePoint Foundation 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"工作流任务"**。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-119">The **WorkflowTasks** action has the same effect as right-clicking any cell in a linked SharePoint Foundation list while it is open in datasheet view, pointing to **Workflow**, and then clicking **Workflow Tasks**.</span></span>

  - <span data-ttu-id="0ed9a-120">要在 VBA 模块中运行 **WorkflowTasks** 操作，请使用 **DoCmd** 对象的 **WorkflowTasks** 方法。</span><span class="sxs-lookup"><span data-stu-id="0ed9a-120">To run the **WorkflowTasks** action in a VBA module, use the **WorkflowTasks** method of the **DoCmd** object.</span></span>

