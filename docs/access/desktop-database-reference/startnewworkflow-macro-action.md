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
ms.openlocfilehash: ed3c508f4799b2ef1f9939de8ce212ab11833353
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925490"
---
# <a name="startnewworkflow-macro-action"></a><span data-ttu-id="ff71a-102">StartNewWorkflow 宏操作</span><span class="sxs-lookup"><span data-stu-id="ff71a-102">StartNewWorkflow macro action</span></span>


<span data-ttu-id="ff71a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff71a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ff71a-104">可以使用 **StartNewWorkflow** 操作为链接的 Microsoft SharePoint Foundation 列表中的项启动新工作流。</span><span class="sxs-lookup"><span data-stu-id="ff71a-104">You can use the **StartNewWorkflow** action to start a new workflow for an item in a linked Microsoft SharePoint Foundation list.</span></span>

## <a name="setting"></a><span data-ttu-id="ff71a-105">设置</span><span class="sxs-lookup"><span data-stu-id="ff71a-105">Setting</span></span>

<span data-ttu-id="ff71a-106">**StartNewWorkflow** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="ff71a-106">The **StartNewWorkflow** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ff71a-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="ff71a-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="ff71a-108">说明</span><span class="sxs-lookup"><span data-stu-id="ff71a-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff71a-109"><strong>记录号</strong></span><span class="sxs-lookup"><span data-stu-id="ff71a-109"><strong>Record Number</strong></span></span></p></td>
<td><p><span data-ttu-id="ff71a-110">在 SharePoint Foundation 列表中，启动与列表中的第一项<strong>1</strong> 、 <strong>2</strong>的第二个项目，依次类推项的位置。</span><span class="sxs-lookup"><span data-stu-id="ff71a-110">The position of the item in the SharePoint Foundation list, starting with <strong>1</strong> for the first item in the list, <strong>2</strong> for the second item, and so on.</span></span> <span data-ttu-id="ff71a-111">您还可以输入一个表达式为此参数。</span><span class="sxs-lookup"><span data-stu-id="ff71a-111">You can also enter an expression for this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ff71a-112">说明</span><span class="sxs-lookup"><span data-stu-id="ff71a-112">Remarks</span></span>

  - <span data-ttu-id="ff71a-p102">**StartNewWorkflow** 操作会打开 **"启动新工作流"** 对话框。此对话框显示可用于指定的项的所有工作流。必须先为 SharePoint Foundation 中的列表定义工作流，然后才能使用此操作启动工作流。</span><span class="sxs-lookup"><span data-stu-id="ff71a-p102">The **StartNewWorkflow** action opens the **Start New Workflow** dialog box. This dialog box displays all workflows that are available for the specified item. A workflow must be defined for the list in SharePoint Foundation before you can start it using this action.</span></span>

  - <span data-ttu-id="ff71a-p103">只有在打开并选择了链接的 SharePoint 列表后，才可以使用 **StartNewWorkflow** 操作。要打开并选择链接的列表，请使用 **OpenTable** 操作。如果该列表已经打开，请使用 **SelectObject** 操作选择它。</span><span class="sxs-lookup"><span data-stu-id="ff71a-p103">The **StartNewWorkflow** action can only be used after a linked SharePoint list has been opened and selected. To open and select the linked list, use the **OpenTable** action. If the list is already open, use the **SelectObject** action to select it.</span></span>

  - <span data-ttu-id="ff71a-119">**StartNewWorkflow** 操作等效于当链接的 SharePoint 列表在数据表视图中处于打开状态时右键单击其中的任意单元格，指向 **"工作流"**，然后单击 **"启动新工作流"**。</span><span class="sxs-lookup"><span data-stu-id="ff71a-119">The **StartNewWorkflow** action has the same effect as right-clicking any cell in a linked SharePoint list while it is open in Datasheet view, pointing to **Workflow**, and then clicking **Start New Workflow**.</span></span>

  - <span data-ttu-id="ff71a-120">要在 VBA 模块中运行 **StartNewWorkflow** 操作，请使用 **DoCmd** 对象的 **StartNewWorkflow** 方法。</span><span class="sxs-lookup"><span data-stu-id="ff71a-120">To run the **StartNewWorkflow** action in a VBA module, use the **StartNewWorkflow** method of the **DoCmd** object.</span></span>

