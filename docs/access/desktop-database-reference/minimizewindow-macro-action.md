---
title: MinimizeWindow 宏操作
TOCTitle: MinimizeWindow Macro Action
ms:assetid: 3a92b654-15ce-1ed1-63e0-eed927dbe26c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192648(v=office.15)
ms:contentKeyID: 48544265
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm174420
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fd70c3fb41b65ae9c21b1651a6af64912b9c3c7c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890888"
---
# <a name="minimizewindow-macro-action"></a><span data-ttu-id="7f858-102">MinimizeWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="7f858-102">MinimizeWindow Macro Action</span></span>


<span data-ttu-id="7f858-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7f858-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7f858-104">如果访问配置为使用重叠窗口而不是选项卡式文档，您可以使用**MinimizeWindow**操作以减少于 Access 窗口的底部小型标题栏的活动窗口。</span><span class="sxs-lookup"><span data-stu-id="7f858-104">If Access is configured to use overlapping windows instead of tabbed documents, you can use the **MinimizeWindow** action to reduce the active window to a small title bar at the bottom of the Access window.</span></span>


> [!NOTE]
> <P><span data-ttu-id="7f858-p101">[!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 <STRONG>WindowState</STRONG> 属性主题。</span><span class="sxs-lookup"><span data-stu-id="7f858-p101">This action can't be applied to code windows in the Visual Basic Editor. For information about how to affect code windows, see the <STRONG>WindowState</STRONG> property topic.</span></span></P>



## <a name="setting"></a><span data-ttu-id="7f858-107">设置</span><span class="sxs-lookup"><span data-stu-id="7f858-107">Setting</span></span>

<span data-ttu-id="7f858-108">**MinimizeWindow** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="7f858-108">The **MinimizeWindow** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f858-109">说明</span><span class="sxs-lookup"><span data-stu-id="7f858-109">Remarks</span></span>

<span data-ttu-id="7f858-p102">可以使用此操作从屏幕中移除窗口，同时使该数据库对象保持打开状态。还可以使用此操作打开对象而不显示其窗口。若要显示对象，请将 **SelectObject** 操作与 **MaximizeWindow** 或 **RestoreWindow** 操作结合使用。 **RestoreWindow** 操作可将最小化窗口还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="7f858-p102">You can use this action to remove a window from the screen while leaving the object open. You can also use this action to open an object without displaying its window. To display the object, use the **SelectObject** action with either the **MaximizeWindow** or **RestoreWindow** action. The **RestoreWindow** action restores a minimized window to its previous size.</span></span>

<span data-ttu-id="7f858-114">**MinimizeWindow** 操作等效于单击窗口右上角的 **"最小化"** 按钮或单击窗口 **"控件"** 菜单上的 **"最小化"**。</span><span class="sxs-lookup"><span data-stu-id="7f858-114">The **MinimizeWindow** action has the same effect as clicking the **Minimize** button in the window's upper-right corner or clicking **Minimize** on the window's **Control** menu.</span></span>

<span data-ttu-id="7f858-115">**提示**</span><span class="sxs-lookup"><span data-stu-id="7f858-115">**Tips**</span></span>

  - <span data-ttu-id="7f858-116">如果要最小化的窗口不是活动窗口，则可能需要先使用 **SelectObject** 操作。</span><span class="sxs-lookup"><span data-stu-id="7f858-116">You may first need to use the **SelectObject** action if the window you want to minimize isn't the active window.</span></span>

  - <span data-ttu-id="7f858-117">若要隐藏导航窗格中，请在导航窗格中参数设置为**是**，然后使用**MinimizeWindow**操作与使用**SelectObject**操作。</span><span class="sxs-lookup"><span data-stu-id="7f858-117">To hide the Navigation Pane, use the **SelectObject** action with the In Navigation Pane argument set to **Yes** and then use the **MinimizeWindow** action.</span></span> <span data-ttu-id="7f858-118">**SelectObject**操作中选择的对象可以是在数据库中的任何对象。</span><span class="sxs-lookup"><span data-stu-id="7f858-118">The object you select in the **SelectObject** action can be any object in the database.</span></span>

  - <span data-ttu-id="7f858-p104">通过单击 **"视图"** 菜单上的 **"管理此窗口"**，然后单击 **"隐藏"**，可隐藏活动窗口。此时，窗口不是缩小为图标，而是从视图中消失。使用同一菜单上的 **"取消隐藏"** 命令可使该窗口重新显示出来。您可以使用 **RunMenuCommand** 操作通过宏执行上述任一命令。</span><span class="sxs-lookup"><span data-stu-id="7f858-p104">You can hide the active window by clicking **Manage This Window** on the **View** menu, and then clicking **Hide**. Instead of being reduced to an icon, the window becomes invisible. Use the **Unhide** command on the same menu to make the window reappear. You can use the **RunMenuCommand** action to carry out either of these commands from a macro.</span></span>

  - <span data-ttu-id="7f858-123">还可以使用 **SetValue** 操作设置窗体的 **"Visible"** 属性，以隐藏或显示窗体的窗口。</span><span class="sxs-lookup"><span data-stu-id="7f858-123">You can also use the **SetValue** action to set a form's **Visible** property to hide or show the form's window.</span></span>

<span data-ttu-id="7f858-124">若要在 Visual Basic for Applications (VBA) 模块中运行 **MinimizeWindow** 操作，请使用 **DoCmd** 对象的 **Minimize** 方法。</span><span class="sxs-lookup"><span data-stu-id="7f858-124">To run the **MinimizeWindow** action in a Visual Basic for Applications (VBA) module, use the **Minimize** method of the **DoCmd** object.</span></span>

