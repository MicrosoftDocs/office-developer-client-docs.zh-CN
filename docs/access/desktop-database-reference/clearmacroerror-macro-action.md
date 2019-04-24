---
title: ClearMacroError 宏操作
TOCTitle: ClearMacroError macro action
ms:assetid: 1091747e-e957-38c6-6454-5169f091323e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845338(v=office.15)
ms:contentKeyID: 48543296
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm109100
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f42386674ff76d550fb47a971860b4e1a5905236
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296372"
---
# <a name="clearmacroerror-macro-action"></a><span data-ttu-id="e647c-102">ClearMacroError 宏操作</span><span class="sxs-lookup"><span data-stu-id="e647c-102">ClearMacroError macro action</span></span>


<span data-ttu-id="e647c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e647c-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="e647c-104">可以使用 **ClearMacroError** 操作清除有关 **MacroError** 对象中所存储的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e647c-104">You can use the **ClearMacroError** action to clear information about an error that is stored in the **MacroError** object.</span></span>

## <a name="setting"></a><span data-ttu-id="e647c-105">Setting</span><span class="sxs-lookup"><span data-stu-id="e647c-105">Setting</span></span>

<span data-ttu-id="e647c-106">**ClearMacroError** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="e647c-106">The **ClearMacroError** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="e647c-107">注解</span><span class="sxs-lookup"><span data-stu-id="e647c-107">Remarks</span></span>

- <span data-ttu-id="e647c-108">宏错误时，错误的信息存储在 **MacroError** 对象。</span><span class="sxs-lookup"><span data-stu-id="e647c-108">When an error occurs in a macro, information about the error is stored in the **MacroError** object.</span></span> <span data-ttu-id="e647c-109">如果您未使用**[OnError](onerror-macro-action.md)** 操作来禁止显示错误消息, 则宏将停止, 错误信息将显示在标准错误消息中。</span><span class="sxs-lookup"><span data-stu-id="e647c-109">If you have not used the **[OnError](onerror-macro-action.md)** action to suppress error messages, the macro stops and the error information is displayed in a standard error message.</span></span> <span data-ttu-id="e647c-110">但是, 如果您已使用**OnError**操作禁止显示错误消息, 则可能需要在条件中或自定义错误消息中使用存储在**MacroError**对象中的信息。</span><span class="sxs-lookup"><span data-stu-id="e647c-110">However, if you have used the **OnError** action to suppress error messages, you might want to use the information stored in the **MacroError** object in a condition or in a custom error message.</span></span>
    
  <span data-ttu-id="e647c-p102">在错误得到处理后， **MacroError** 对象中的信息将过期，因此最好使用 **ClearMacroError** 操作清除该对象。执行此操作会将 **MacroError** 对象的错误数量重置为 0，并清除有关存储在该对象中的错误的所有其他信息，例如错误说明、宏名称、操作名称、条件和参数。通过这种方式，可在以后重新检查 **MacroError** 对象，以确定是否发生了其他错误。</span><span class="sxs-lookup"><span data-stu-id="e647c-p102">After an error has been handled, the information in the **MacroError** object is out of date, so it is a good idea to clear the object by using the **ClearMacroError** action. Doing so resets the error number in the **MacroError** object to 0 and clears any other information about the error that is stored in the object, such as the error description, macro name, action name, condition, and arguments. This way, you can inspect the **MacroError** object again later to see if another error has occurred.</span></span>

- <span data-ttu-id="e647c-114">在任何宏结束时，都会自动清除 **MacroError** 对象，因此无需在宏末尾使用 **ClearMacroError** 操作。</span><span class="sxs-lookup"><span data-stu-id="e647c-114">The **MacroError** object is automatically cleared when any macro ends, so you do not need to use the **ClearMacroError** action at the end of a macro.</span></span>

- <span data-ttu-id="e647c-p103">**MacroError** 对象每次仅包含有关一个错误的信息。如果宏中发生了多个错误， **MacroError** 对象将仅包含有关最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e647c-p103">The **MacroError** object contains information about only one error at a time. If more than one error has occurred in a macro, the **MacroError** object contains information only about the last error.</span></span>

- <span data-ttu-id="e647c-117">要在 VBA 模块中运行 **ClearMacroError** 操作，请使用 **DoCmd** 对象的 **ClearMacroError** 方法。</span><span class="sxs-lookup"><span data-stu-id="e647c-117">To run the **ClearMacroError** action in a VBA module, use the **ClearMacroError** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="e647c-118">示例</span><span class="sxs-lookup"><span data-stu-id="e647c-118">Example</span></span>

<span data-ttu-id="e647c-119">The following macro uses the **OnError** action with the **Next** argument to suppress error messages, and then uses the **OpenForm** action to open a form.</span><span class="sxs-lookup"><span data-stu-id="e647c-119">The following macro uses the **OnError** action with the **Next** argument to suppress error messages, and then uses the **OpenForm** action to open a form.</span></span> <span data-ttu-id="e647c-120">For this example, an error is deliberately created by using the **GoToRecord** action to go to the previous record.</span><span class="sxs-lookup"><span data-stu-id="e647c-120">For this example, an error is deliberately created by using the **GoToRecord** action to go to the previous record.</span></span> <span data-ttu-id="e647c-121">条件\*\* \[MacroError\]。\[\>数字\]\<0**测试**MacroError\*\*对象。</span><span class="sxs-lookup"><span data-stu-id="e647c-121">The condition **\[MacroError\].\[Number\]\<\>0** tests the **MacroError** object.</span></span> <span data-ttu-id="e647c-122">If an error has occurred, the error number is non-zero, and the **MessageBox** action runs.</span><span class="sxs-lookup"><span data-stu-id="e647c-122">If an error has occurred, the error number is non-zero, and the **MessageBox** action runs.</span></span> <span data-ttu-id="e647c-123">The message box displays the name of the action that caused the error (in this case, the **GoToRecord** action), and the error number is displayed.</span><span class="sxs-lookup"><span data-stu-id="e647c-123">The message box displays the name of the action that caused the error (in this case, the **GoToRecord** action), and the error number is displayed.</span></span> <span data-ttu-id="e647c-124">此示例最后运行 **ClearMacroError** 操作清除 **MacroError** 对象。</span><span class="sxs-lookup"><span data-stu-id="e647c-124">Finally, running the **ClearMacroError** action clears the **MacroError** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e647c-125">条件</span><span class="sxs-lookup"><span data-stu-id="e647c-125">Condition</span></span></p></th>
<th><p><span data-ttu-id="e647c-126">操作</span><span class="sxs-lookup"><span data-stu-id="e647c-126">Action</span></span></p></th>
<th><p><span data-ttu-id="e647c-127">参数</span><span class="sxs-lookup"><span data-stu-id="e647c-127">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e647c-128"><strong>OnError</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-128"><strong>OnError</strong></span></span></p></td>
<td><p><span data-ttu-id="e647c-129"><strong>转至</strong>：<strong>“下一个”</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-129"><strong>Go to</strong>: <strong>Next</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="e647c-130"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-130"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="e647c-131"><strong>表单名称</strong>: 类别窗体<strong>View</strong>: <strong>FormWindow Mode</strong>: <strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-131"><strong>Form Name</strong>: CategoryForm<strong>View</strong>: <strong>FormWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e647c-132"><strong>GoToRecord</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-132"><strong>GoToRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="e647c-133"><strong>对象类型</strong>: <strong>FormObject Name</strong>: 类别窗体<strong>Record</strong>: Previous</span><span class="sxs-lookup"><span data-stu-id="e647c-133"><strong>Object Type</strong>: <strong>FormObject Name</strong>: CategoryForm<strong>Record</strong>: Previous</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e647c-134">[MacroError]。多种&lt; &gt;0</span><span class="sxs-lookup"><span data-stu-id="e647c-134">[MacroError].[Number]&lt;&gt;0</span></span></p></td>
<td><p><span data-ttu-id="e647c-135"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-135"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="e647c-136"><strong>消息</strong>: =&quot;错误 # &quot; &amp; [MacroError]。多种在 [MacroError &amp; ] 上。 &quot; &amp; &quot;ActionName&amp; &quot;操作。&quot;<strong>嘟嘟声</strong>: <strong>YesType</strong>: 信息</span><span class="sxs-lookup"><span data-stu-id="e647c-136"><strong>Message</strong>: =&quot;Error # &quot; &amp; [MacroError].[Number] &amp; &quot; on &quot; &amp; [MacroError].[ActionName] &amp; &quot; action.&quot;<strong>Beep</strong>: <strong>YesType</strong>: Information</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e647c-137"><strong>ClearMacroError</strong></span><span class="sxs-lookup"><span data-stu-id="e647c-137"><strong>ClearMacroError</strong></span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

