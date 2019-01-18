---
title: RestoreWindow 宏操作
TOCTitle: RestoreWindow macro action
ms:assetid: 507a6452-2be0-a523-1201-0108d2b9d23c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193815(v=office.15)
ms:contentKeyID: 48544796
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm11103
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 35637781035b7a449ba574cf5f6c84f2cb5223db
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718831"
---
# <a name="restorewindow-macro-action"></a><span data-ttu-id="3e0d9-102">RestoreWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="3e0d9-102">RestoreWindow macro action</span></span>

<span data-ttu-id="3e0d9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3e0d9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3e0d9-104">可以使用 **RestoreWindow** 操作将已最大化或最小化的窗口还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-104">You can use the **RestoreWindow** action to restore a maximized or minimized window to its previous size.</span></span>

> [!NOTE]
> <span data-ttu-id="3e0d9-p101">[!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 **WindowState** 属性主题。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-p101">This action can't be applied to code windows in the Visual Basic Editor. For information about how to affect code windows, see the **WindowState** property topic.</span></span>

## <a name="setting"></a><span data-ttu-id="3e0d9-107">设置</span><span class="sxs-lookup"><span data-stu-id="3e0d9-107">Setting</span></span>

<span data-ttu-id="3e0d9-108">**RestoreWindow** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-108">The **RestoreWindow** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e0d9-109">说明</span><span class="sxs-lookup"><span data-stu-id="3e0d9-109">Remarks</span></span>

<span data-ttu-id="3e0d9-p102">此操作对所选的数据库对象有效。如果对象已经最小化，可以先用 **SelectObject** 操作选定它，然后使用 **RestoreWindow** 操作将它还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-p102">This action works on the selected object. If an object has been minimized, you can first select it by using the **SelectObject** action and then restore it to its previous size by using the **RestoreWindow** action.</span></span>

<span data-ttu-id="3e0d9-112">可以使用 **MoveAndSizeWindow** 操作移动已经还原的窗口或者调整其大小。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-112">You can use the **MoveAndSizeWindow** action to move or size a window that you have restored.</span></span>

<span data-ttu-id="3e0d9-113">**RestoreWindow** 操作等效于单击窗口右上角的 **"还原"** 按钮或者单击窗口 **"控件"** 菜单上的 **"还原"** 命令。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-113">The **RestoreWindow** action has the same effect as clicking the **Restore** button in the window's upper-right corner or clicking the **Restore** command on the window's **Control** menu.</span></span>

<span data-ttu-id="3e0d9-114">若要在 Visual Basic for Applications (VBA) 模块中运行 **RestoreWindow** 操作，请使用 **DoCmd** 对象的 **Restore** 方法。</span><span class="sxs-lookup"><span data-stu-id="3e0d9-114">To run the **RestoreWindow** action in a Visual Basic for Applications (VBA) module, use the **Restore** method of the **DoCmd** object.</span></span>

