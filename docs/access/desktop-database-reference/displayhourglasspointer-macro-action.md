---
title: DisplayHourglassPointer 宏操作
TOCTitle: DisplayHourglassPointer Macro Action
ms:assetid: 2c93039a-f75c-abeb-1dfa-e632a5bdf6f2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192103(v=office.15)
ms:contentKeyID: 48543957
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm117200
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 003fb36fc876aa573419b963a9eca6f54332190a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467205"
---
# <a name="displayhourglasspointer-macro-action"></a><span data-ttu-id="55239-102">DisplayHourglassPointer 宏操作</span><span class="sxs-lookup"><span data-stu-id="55239-102">DisplayHourglassPointer Macro Action</span></span>


<span data-ttu-id="55239-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="55239-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="55239-p101">可以使用 **DisplayHourglassPointer** 操作在宏运行时将鼠标指针更改为沙漏图像（或选择的其他图标）。此操作可直观地指示宏正在运行。当宏操作或宏本身需要较长的运行时间时，这会特别有用。</span><span class="sxs-lookup"><span data-stu-id="55239-p101">You can use the **DisplayHourglassPointer** action to change the mouse pointer to an image of an hourglass (or another icon you've chosen) while a macro is running. This action can provide a visual indication that the macro is running. This is especially useful when a macro action or the macro itself takes a long time to run.</span></span>

## <a name="setting"></a><span data-ttu-id="55239-107">设置</span><span class="sxs-lookup"><span data-stu-id="55239-107">Setting</span></span>

<span data-ttu-id="55239-108">**DisplayHourglassPointer** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="55239-108">The **DisplayHourglassPointer** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="55239-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="55239-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="55239-110">说明</span><span class="sxs-lookup"><span data-stu-id="55239-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55239-111"><strong>显示沙漏</strong></span><span class="sxs-lookup"><span data-stu-id="55239-111"><strong>Hourglass On</strong></span></span></p></td>
<td><p><span data-ttu-id="55239-p102">请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“显示沙漏”</strong>框中单击<strong>“是”</strong>（显示图标）或<strong>“否”</strong>（显示正常的鼠标指针）。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="55239-p102">Click <strong>Yes</strong> (display the icon) or <strong>No</strong> (display the normal mouse pointer) in the <strong>Hourglass On</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="55239-114">说明</span><span class="sxs-lookup"><span data-stu-id="55239-114">Remarks</span></span>

<span data-ttu-id="55239-115">如果已使用 **Echo** 操作关闭回响，则通常要使用此操作。</span><span class="sxs-lookup"><span data-stu-id="55239-115">You often use this action if you have turned echo off by using the **Echo** action.</span></span> <span data-ttu-id="55239-116">回声关闭时，Access 将挂起屏幕更新，直到完成宏。</span><span class="sxs-lookup"><span data-stu-id="55239-116">When echo is off, Access suspends screen updates until the macro is finished.</span></span>

<span data-ttu-id="55239-117">当宏运行完毕时，access 会将**显示沙漏**参数自动重置为**否**。</span><span class="sxs-lookup"><span data-stu-id="55239-117">Access automatically resets the **Hourglass On** argument to **No** when the macro finishes running.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="55239-p104">在 Microsoft Windows 中，这是在 Windows 控制面板的 <STRONG>"鼠标属性"</STRONG>对话框中为 <STRONG>"忙"</STRONG>设置的图标。所有 Windows 操作系统的默认设置都是一个具有动画效果的沙漏图标。</span><span class="sxs-lookup"><span data-stu-id="55239-p104">In Microsoft Windows, this is the icon you set for <STRONG>Busy</STRONG> in the <STRONG>Mouse Properties</STRONG> dialog box of Windows Control Panel. The default for all Windows operating systems is an animated hourglass icon.</span></span></P>
> <LI>
> <P><span data-ttu-id="55239-120">您可以根据需要选择其他图标。</span><span class="sxs-lookup"><span data-stu-id="55239-120">You can choose another icon if you want.</span></span></P></LI></UL>



<span data-ttu-id="55239-121">若要在 Visual Basic for Applications (VBA) 模块中运行 **DisplayHourglassPointer** 操作，请使用 **DoCmd** 对象的 **Hourglass** 方法。</span><span class="sxs-lookup"><span data-stu-id="55239-121">To run the **DisplayHourglassPointer** action in a Visual Basic for Applications (VBA) module, use the **Hourglass** method of the **DoCmd** object.</span></span>

