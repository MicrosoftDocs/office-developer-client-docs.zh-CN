---
title: MaximizeWindow 宏操作
TOCTitle: MaximizeWindow Macro Action
ms:assetid: 79c9e430-07a7-02b2-ff5a-c6b9ec32c5b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196171(v=office.15)
ms:contentKeyID: 48545778
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm196948
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b612d050d6c523ae836b21aa27826ff180e8f977
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467005"
---
# <a name="maximizewindow-macro-action"></a><span data-ttu-id="12368-102">MaximizeWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="12368-102">MaximizeWindow Macro Action</span></span>


<span data-ttu-id="12368-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="12368-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="12368-104">如果访问配置为使用重叠窗口而不是选项卡式文档，您可以使用**MaximizeWindow**操作放大活动窗口，使其填充 Access 窗口。</span><span class="sxs-lookup"><span data-stu-id="12368-104">If Access is configured to use overlapping windows instead of tabbed documents, you can use the **MaximizeWindow** action to enlarge the active window so that it fills the Access window.</span></span> <span data-ttu-id="12368-105">此操作可使您看到活动窗口中尽可能多的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="12368-105">This action will allow you to see as much of the object in the active window as possible.</span></span>


> [!NOTE]
> <P><span data-ttu-id="12368-p102">[!注释] 此操作不能应用于 Visual Basic 编辑器中的代码窗口。有关如何影响代码窗口的信息，请参阅 <STRONG>WindowState</STRONG> 属性主题。</span><span class="sxs-lookup"><span data-stu-id="12368-p102">This action can't be applied to code windows in the Visual Basic Editor. For information about how to affect code windows, see the <STRONG>WindowState</STRONG> property topic.</span></span></P>



## <a name="setting"></a><span data-ttu-id="12368-108">设置</span><span class="sxs-lookup"><span data-stu-id="12368-108">Setting</span></span>

<span data-ttu-id="12368-109">**MaximizeWindow** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="12368-109">The **MaximizeWindow** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="12368-110">说明</span><span class="sxs-lookup"><span data-stu-id="12368-110">Remarks</span></span>

<span data-ttu-id="12368-111">此操作等效于单击窗口右上角中的 **"最大化"** 按钮或单击窗口 **"控件"** 菜单上的 **"最大化"**。</span><span class="sxs-lookup"><span data-stu-id="12368-111">This action has the same effect as clicking the **Maximize** button in the window's upper-right corner or clicking **Maximize** on the window's **Control** menu.</span></span>

<span data-ttu-id="12368-112">可以使用 **RestoreWindow** 操作使最大化窗口还原为其原来的大小。</span><span class="sxs-lookup"><span data-stu-id="12368-112">You can use the **RestoreWindow** action to restore a maximized window to its previous size.</span></span>

<span data-ttu-id="12368-113">**提示**</span><span class="sxs-lookup"><span data-stu-id="12368-113">**Tips**</span></span>

  - <span data-ttu-id="12368-114">如果要最大化的窗口不是活动窗口，可能需要使用 **SelectObject** 操作。</span><span class="sxs-lookup"><span data-stu-id="12368-114">You may need to use the **SelectObject** action if the window you want to maximize isn't the active window.</span></span>

  - <span data-ttu-id="12368-115">当在 Access 窗口最大化时，所有其他窗口不会最大化时所打开或切换到它们。</span><span class="sxs-lookup"><span data-stu-id="12368-115">When you maximize a window in Access, all other windows are also maximized when you open them or switch to them.</span></span> <span data-ttu-id="12368-116">不过，弹出式窗体不会最大化。</span><span class="sxs-lookup"><span data-stu-id="12368-116">However, pop-up forms aren't maximized.</span></span> <span data-ttu-id="12368-117">如果您希望在其他窗口最大化时保持其大小的窗体，，设置其**PopUp**属性为**是**。</span><span class="sxs-lookup"><span data-stu-id="12368-117">If you want a form to maintain its size when other windows are maximized, set its **PopUp** property to **Yes**.</span></span>

<span data-ttu-id="12368-118">若要在 Visual Basic for Applications 模块中运行 **MaximizeWindow** 操作，请使用 **DoCmd** 对象的 **Maximize** 方法。</span><span class="sxs-lookup"><span data-stu-id="12368-118">To run the **MaximizeWindow** action in a Visual Basic for Applications module, use the **Maximize** method of the **DoCmd** object.</span></span>

