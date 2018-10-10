---
title: ClearMacroError 宏操作
TOCTitle: ClearMacroError Macro Action
ms:assetid: 1091747e-e957-38c6-6454-5169f091323e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845338(v=office.15)
ms:contentKeyID: 48543296
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm109100
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8e5cf0b8cb7ac5b9c49e86ae3a0399d0222b3b04
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466625"
---
# <a name="clearmacroerror-macro-action"></a><span data-ttu-id="683e7-102">ClearMacroError 宏操作</span><span class="sxs-lookup"><span data-stu-id="683e7-102">ClearMacroError Macro Action</span></span>


<span data-ttu-id="683e7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="683e7-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="683e7-104">可以使用 **ClearMacroError** 操作清除有关 **MacroError** 对象中所存储的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="683e7-104">You can use the **ClearMacroError** action to clear information about an error that is stored in the **MacroError** object.</span></span>

## <a name="setting"></a><span data-ttu-id="683e7-105">设置</span><span class="sxs-lookup"><span data-stu-id="683e7-105">Setting</span></span>

<span data-ttu-id="683e7-106">**ClearMacroError** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="683e7-106">The **ClearMacroError** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="683e7-107">说明</span><span class="sxs-lookup"><span data-stu-id="683e7-107">Remarks</span></span>

  - <span data-ttu-id="683e7-108">宏错误时，错误的信息存储在 **MacroError** 对象。</span><span class="sxs-lookup"><span data-stu-id="683e7-108">When an error occurs in a macro, information about the error is stored in the **MacroError** object.</span></span> <span data-ttu-id="683e7-109">如果您已使用**[OnError](onerror-macro-action.md)** 操作来禁止显示错误消息，宏将停止错误信息是标准错误消息中显示。</span><span class="sxs-lookup"><span data-stu-id="683e7-109">If you have not used the **[OnError](onerror-macro-action.md)** action to suppress error messages, the macro stops and the error information is displayed in a standard error message.</span></span> <span data-ttu-id="683e7-110">但是，如果您已使用**OnError**操作禁止显示错误消息，您可能想要使用存储在**MacroError**对象中的条件或自定义错误消息中的信息。</span><span class="sxs-lookup"><span data-stu-id="683e7-110">However, if you have used the **OnError** action to suppress error messages, you might want to use the information stored in the **MacroError** object in a condition or in a custom error message.</span></span>
    
    <span data-ttu-id="683e7-p102">在错误得到处理后， **MacroError** 对象中的信息将过期，因此最好使用 **ClearMacroError** 操作清除该对象。执行此操作会将 **MacroError** 对象的错误数量重置为 0，并清除有关存储在该对象中的错误的所有其他信息，例如错误说明、宏名称、操作名称、条件和参数。通过这种方式，可在以后重新检查 **MacroError** 对象，以确定是否发生了其他错误。</span><span class="sxs-lookup"><span data-stu-id="683e7-p102">After an error has been handled, the information in the **MacroError** object is out of date, so it is a good idea to clear the object by using the **ClearMacroError** action. Doing so resets the error number in the **MacroError** object to 0 and clears any other information about the error that is stored in the object, such as the error description, macro name, action name, condition, and arguments. This way, you can inspect the **MacroError** object again later to see if another error has occurred.</span></span>

  - <span data-ttu-id="683e7-114">在任何宏结束时，都会自动清除 **MacroError** 对象，因此无需在宏末尾使用 **ClearMacroError** 操作。</span><span class="sxs-lookup"><span data-stu-id="683e7-114">The **MacroError** object is automatically cleared when any macro ends, so you do not need to use the **ClearMacroError** action at the end of a macro.</span></span>

  - <span data-ttu-id="683e7-p103">**MacroError** 对象每次仅包含有关一个错误的信息。如果宏中发生了多个错误， **MacroError** 对象将仅包含有关最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="683e7-p103">The **MacroError** object contains information about only one error at a time. If more than one error has occurred in a macro, the **MacroError** object contains information only about the last error.</span></span>

  - <span data-ttu-id="683e7-117">要在 VBA 模块中运行 **ClearMacroError** 操作，请使用 **DoCmd** 对象的 **ClearMacroError** 方法。</span><span class="sxs-lookup"><span data-stu-id="683e7-117">To run the **ClearMacroError** action in a VBA module, use the **ClearMacroError** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="683e7-118">示例</span><span class="sxs-lookup"><span data-stu-id="683e7-118">Example</span></span>

<span data-ttu-id="683e7-119">下面的宏使用**OnError**操作具有**下一步**参数来禁止显示错误消息，然后使用**OpenForm**操作打开窗体。</span><span class="sxs-lookup"><span data-stu-id="683e7-119">The following macro uses the **OnError** action with the **Next** argument to suppress error messages, and then uses the **OpenForm** action to open a form.</span></span> <span data-ttu-id="683e7-120">对于此示例中，使用**GoToRecord**操作以转到上一条记录特意创建错误。</span><span class="sxs-lookup"><span data-stu-id="683e7-120">For this example, an error is deliberately created by using the **GoToRecord** action to go to the previous record.</span></span> <span data-ttu-id="683e7-121">条件**\[MacroError\]。\[号码\]\<\>0**测试**MacroError**对象。</span><span class="sxs-lookup"><span data-stu-id="683e7-121">The condition **\[MacroError\].\[Number\]\<\>0** tests the **MacroError** object.</span></span> <span data-ttu-id="683e7-122">如果出现错误，错误号为非零值，并运行**MessageBox**操作。</span><span class="sxs-lookup"><span data-stu-id="683e7-122">If an error has occurred, the error number is non-zero, and the **MessageBox** action runs.</span></span> <span data-ttu-id="683e7-123">消息框显示操作导致 （在本例中**GoToRecord**操作），该错误的名称和显示的错误号。</span><span class="sxs-lookup"><span data-stu-id="683e7-123">The message box displays the name of the action that caused the error (in this case, the **GoToRecord** action), and the error number is displayed.</span></span> <span data-ttu-id="683e7-124">最后，运行**ClearMacroError**操作清除**MacroError**对象。</span><span class="sxs-lookup"><span data-stu-id="683e7-124">Finally, running the **ClearMacroError** action clears the **MacroError** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="683e7-125">条件</span><span class="sxs-lookup"><span data-stu-id="683e7-125">Condition</span></span></p></th>
<th><p><span data-ttu-id="683e7-126">操作</span><span class="sxs-lookup"><span data-stu-id="683e7-126">Action</span></span></p></th>
<th><p><span data-ttu-id="683e7-127">参数</span><span class="sxs-lookup"><span data-stu-id="683e7-127">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="683e7-128"><strong>OnError</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-128"><strong>OnError</strong></span></span></p></td>
<td><p><span data-ttu-id="683e7-129"><strong>转至</strong>：<strong>“下一个”</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-129"><strong>Go to</strong>: <strong>Next</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="683e7-130"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-130"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="683e7-131"><strong>窗体名称</strong>： 类别窗体<strong>视图</strong>： <strong>FormWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-131"><strong>Form Name</strong>: CategoryForm<strong>View</strong>: <strong>FormWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="683e7-132"><strong>GoToRecord</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-132"><strong>GoToRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="683e7-133"><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 类别窗体<strong>记录</strong>： 上一个</span><span class="sxs-lookup"><span data-stu-id="683e7-133"><strong>Object Type</strong>: <strong>FormObject Name</strong>: CategoryForm<strong>Record</strong>: Previous</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="683e7-134">[宏错误]。[Number]&lt; &gt;0</span><span class="sxs-lookup"><span data-stu-id="683e7-134">[MacroError].[Number]&lt;&gt;0</span></span></p></td>
<td><p><span data-ttu-id="683e7-135"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-135"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="683e7-136"><strong>消息</strong>: =&quot;错误 # &quot; &amp; [宏错误]。[Number]&amp; &quot;上&quot; &amp; [宏错误]。[ActionName]&amp; &quot;操作。&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>： 信息</span><span class="sxs-lookup"><span data-stu-id="683e7-136"><strong>Message</strong>: =&quot;Error # &quot; &amp; [MacroError].[Number] &amp; &quot; on &quot; &amp; [MacroError].[ActionName] &amp; &quot; action.&quot;<strong>Beep</strong>: <strong>YesType</strong>: Information</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="683e7-137"><strong>ClearMacroError</strong></span><span class="sxs-lookup"><span data-stu-id="683e7-137"><strong>ClearMacroError</strong></span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

