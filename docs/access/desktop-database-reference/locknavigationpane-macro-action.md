---
title: LockNavigationPane 宏操作
TOCTitle: LockNavigationPane macro action
ms:assetid: abf7a989-c7cf-3efa-8df4-3c5b075d0e5f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821487(v=office.15)
ms:contentKeyID: 48546986
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm172454
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7f6ee19edaf2efdc03301e98e709db6dd69f101a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717802"
---
# <a name="locknavigationpane-macro-action"></a><span data-ttu-id="12882-102">LockNavigationPane 宏操作</span><span class="sxs-lookup"><span data-stu-id="12882-102">LockNavigationPane macro action</span></span>


<span data-ttu-id="12882-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="12882-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="12882-104">可以使用 **LockNavigationPane** 操作防止用户删除导航窗格中显示的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="12882-104">You can use the **LockNavigationPane** action to prevent users from deleting database objects that are displayed in the Navigation Pane.</span></span>

## <a name="setting"></a><span data-ttu-id="12882-105">设置</span><span class="sxs-lookup"><span data-stu-id="12882-105">Setting</span></span>

<span data-ttu-id="12882-106">**LockNavigationPane** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="12882-106">The **LockNavigationPane** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="12882-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="12882-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="12882-108">说明</span><span class="sxs-lookup"><span data-stu-id="12882-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12882-109"><strong>Lock</strong></span><span class="sxs-lookup"><span data-stu-id="12882-109"><strong>Lock</strong></span></span></p></td>
<td><p><span data-ttu-id="12882-110">选择<strong>是</strong>可锁定导航窗格中，或<strong>否</strong>可解除锁定导航窗格。</span><span class="sxs-lookup"><span data-stu-id="12882-110">Select <strong>Yes</strong> to lock the Navigation Pane, or <strong>No</strong> to unlock the Navigation Pane.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="12882-111">说明</span><span class="sxs-lookup"><span data-stu-id="12882-111">Remarks</span></span>

<span data-ttu-id="12882-112">通过锁定导航窗格，可防止删除数据库对象或将数据库对象剪切到剪贴板中。</span><span class="sxs-lookup"><span data-stu-id="12882-112">Locking the Navigation Pane prevents you from deleting database objects or cutting database objects to the clipboard.</span></span> <span data-ttu-id="12882-113">但*不*阻止您执行任何以下操作：</span><span class="sxs-lookup"><span data-stu-id="12882-113">It does *not* prevent you from performing any of the following operations:</span></span>

  - <span data-ttu-id="12882-114">将数据库对象复制到剪贴板中</span><span class="sxs-lookup"><span data-stu-id="12882-114">Copying database objects to the clipboard</span></span>

  - <span data-ttu-id="12882-115">粘贴剪贴板上的数据库对象</span><span class="sxs-lookup"><span data-stu-id="12882-115">Pasting database objects from the clipboard</span></span>

  - <span data-ttu-id="12882-116">显示或隐藏导航窗格</span><span class="sxs-lookup"><span data-stu-id="12882-116">Displaying or hiding the Navigation Pane</span></span>

  - <span data-ttu-id="12882-117">选择不同的导航窗格组织方案</span><span class="sxs-lookup"><span data-stu-id="12882-117">Selecting different Navigation Pane organization schemes</span></span>

  - <span data-ttu-id="12882-118">显示或隐藏导航窗格的某些部分</span><span class="sxs-lookup"><span data-stu-id="12882-118">Showing or hiding sections of the Navigation Pane</span></span>

<span data-ttu-id="12882-119">要在 VBA 模块中运行 **LockNavigationPane** 操作，请使用 **DoCmd** 对象的 **LockNavigationPane** 方法。</span><span class="sxs-lookup"><span data-stu-id="12882-119">To run the **LockNavigationPane** action in a VBA module, use the **LockNavigationPane** method of the **DoCmd** object.</span></span>

