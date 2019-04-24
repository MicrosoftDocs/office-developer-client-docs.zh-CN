---
title: StartNewWorkflow 宏操作
TOCTitle: StartNewWorkflow macro action
ms:assetid: b3e81a11-b816-0eef-fc70-6d6da7a5a845
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822054(v=office.15)
ms:contentKeyID: 48547206
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm198223
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 1e37d72754531fc4dd51427eefb355a057d08073
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306396"
---
# <a name="startnewworkflow-macro-action"></a><span data-ttu-id="cea18-102">StartNewWorkflow 宏操作</span><span class="sxs-lookup"><span data-stu-id="cea18-102">StartNewWorkflow macro action</span></span>


<span data-ttu-id="cea18-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="cea18-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cea18-104">可以使用 **StartNewWorkflow** 操作为链接的 Microsoft SharePoint Foundation 列表中的项启动新工作流。</span><span class="sxs-lookup"><span data-stu-id="cea18-104">You can use the **StartNewWorkflow** action to start a new workflow for an item in a linked Microsoft SharePoint Foundation list.</span></span>

## <a name="setting"></a><span data-ttu-id="cea18-105">Setting</span><span class="sxs-lookup"><span data-stu-id="cea18-105">Setting</span></span>

<span data-ttu-id="cea18-106">**StartNewWorkflow** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="cea18-106">The **StartNewWorkflow** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cea18-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="cea18-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="cea18-108">说明</span><span class="sxs-lookup"><span data-stu-id="cea18-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cea18-109"><strong>记录号</strong></span><span class="sxs-lookup"><span data-stu-id="cea18-109"><strong>Record Number</strong></span></span></p></td>
<td><p><span data-ttu-id="cea18-110">项目在 SharePoint Foundation 列表中的位置, 从列表中的<strong></strong>第一个项目开始, 第一个项目为<strong>2</strong> , 依此类推。</span><span class="sxs-lookup"><span data-stu-id="cea18-110">The position of the item in the SharePoint Foundation list, starting with <strong>1</strong> for the first item in the list, <strong>2</strong> for the second item, and so on.</span></span> <span data-ttu-id="cea18-111">也可以为此参数输入表达式。</span><span class="sxs-lookup"><span data-stu-id="cea18-111">You can also enter an expression for this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="cea18-112">注解</span><span class="sxs-lookup"><span data-stu-id="cea18-112">Remarks</span></span>

  - <span data-ttu-id="cea18-p102">**StartNewWorkflow** 操作会打开 **"启动新工作流"** 对话框。此对话框显示可用于指定的项的所有工作流。必须先为 SharePoint Foundation 中的列表定义工作流，然后才能使用此操作启动工作流。</span><span class="sxs-lookup"><span data-stu-id="cea18-p102">The **StartNewWorkflow** action opens the **Start New Workflow** dialog box. This dialog box displays all workflows that are available for the specified item. A workflow must be defined for the list in SharePoint Foundation before you can start it using this action.</span></span>

  - <span data-ttu-id="cea18-p103">只有在打开并选择了链接的 SharePoint 列表后，才可以使用 **StartNewWorkflow** 操作。要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。</span><span class="sxs-lookup"><span data-stu-id="cea18-p103">The **StartNewWorkflow** action can only be used after a linked SharePoint list has been opened and selected. To open and select the linked list, use the **OpenTable** action. If the list is already open, use the **SelectObject** action to select it.</span></span>

  - <span data-ttu-id="cea18-119">**StartNewWorkflow** 操作等效于当链接的 SharePoint 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"启动新工作流"**。</span><span class="sxs-lookup"><span data-stu-id="cea18-119">The **StartNewWorkflow** action has the same effect as right-clicking any cell in a linked SharePoint list while it is open in Datasheet view, pointing to **Workflow**, and then clicking **Start New Workflow**.</span></span>

  - <span data-ttu-id="cea18-120">要在 VBA 模块中运行 **StartNewWorkflow** 操作，请使用 **DoCmd** 对象的 **StartNewWorkflow** 方法。</span><span class="sxs-lookup"><span data-stu-id="cea18-120">To run the **StartNewWorkflow** action in a VBA module, use the **StartNewWorkflow** method of the **DoCmd** object.</span></span>

