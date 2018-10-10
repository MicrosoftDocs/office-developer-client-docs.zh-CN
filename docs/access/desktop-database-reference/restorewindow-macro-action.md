---
title: RestoreWindow 宏操作
TOCTitle: RestoreWindow Macro Action
ms:assetid: 507a6452-2be0-a523-1201-0108d2b9d23c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193815(v=office.15)
ms:contentKeyID: 48544796
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm11103
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1dc6776310b0544b8bb807327612637a5fbcff67
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468485"
---
# <a name="restorewindow-macro-action"></a><span data-ttu-id="64d34-102">RestoreWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="64d34-102">RestoreWindow Macro Action</span></span>


<span data-ttu-id="64d34-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="64d34-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="64d34-104">可以使用 **RestoreWindow** 操作将已最大化或最小化的窗口还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="64d34-104">You can use the **RestoreWindow** action to restore a maximized or minimized window to its previous size.</span></span>


> [!NOTE]
> <P><span data-ttu-id="64d34-p101">[!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 <STRONG>WindowState</STRONG> 属性主题。</span><span class="sxs-lookup"><span data-stu-id="64d34-p101">This action can't be applied to code windows in the Visual Basic Editor. For information about how to affect code windows, see the <STRONG>WindowState</STRONG> property topic.</span></span></P>



## <a name="setting"></a><span data-ttu-id="64d34-107">设置</span><span class="sxs-lookup"><span data-stu-id="64d34-107">Setting</span></span>

<span data-ttu-id="64d34-108">**RestoreWindow** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="64d34-108">The **RestoreWindow** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="64d34-109">说明</span><span class="sxs-lookup"><span data-stu-id="64d34-109">Remarks</span></span>

<span data-ttu-id="64d34-p102">此操作对所选的数据库对象有效。如果对象已经最小化，可以先用 **SelectObject** 操作选定它，然后使用 **RestoreWindow** 操作将它还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="64d34-p102">This action works on the selected object. If an object has been minimized, you can first select it by using the **SelectObject** action and then restore it to its previous size by using the **RestoreWindow** action.</span></span>

<span data-ttu-id="64d34-112">可以使用 **MoveAndSizeWindow** 操作移动已经还原的窗口或者调整其大小。</span><span class="sxs-lookup"><span data-stu-id="64d34-112">You can use the **MoveAndSizeWindow** action to move or size a window that you have restored.</span></span>

<span data-ttu-id="64d34-113">**RestoreWindow** 操作等效于单击窗口右上角的 **"还原"** 按钮或者单击窗口 **"控件"** 菜单上的 **"还原"** 命令。</span><span class="sxs-lookup"><span data-stu-id="64d34-113">The **RestoreWindow** action has the same effect as clicking the **Restore** button in the window's upper-right corner or clicking the **Restore** command on the window's **Control** menu.</span></span>

<span data-ttu-id="64d34-114">若要在 Visual Basic for Applications (VBA) 模块中运行 **RestoreWindow** 操作，请使用 **DoCmd** 对象的 **Restore** 方法。</span><span class="sxs-lookup"><span data-stu-id="64d34-114">To run the **RestoreWindow** action in a Visual Basic for Applications (VBA) module, use the **Restore** method of the **DoCmd** object.</span></span>

