---
title: SetWarnings 宏操作
TOCTitle: SetWarnings macro action
ms:assetid: ff95b919-b1ee-c0a0-851d-71894851bb1d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837313(v=office.15)
ms:contentKeyID: 48548965
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm165020
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d72a594a09196f5061ede52b4fbcbbc2cf96253c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923159"
---
# <a name="setwarnings-macro-action"></a><span data-ttu-id="22d09-102">SetWarnings 宏操作</span><span class="sxs-lookup"><span data-stu-id="22d09-102">SetWarnings macro action</span></span>


<span data-ttu-id="22d09-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="22d09-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="22d09-104">可以使用 **SetWarnings** 操作打开或者关闭系统消息。</span><span class="sxs-lookup"><span data-stu-id="22d09-104">You can use the **SetWarnings** action to turn system messages on or off.</span></span>


> [!NOTE]
> <P><span data-ttu-id="22d09-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="22d09-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="22d09-107">设置</span><span class="sxs-lookup"><span data-stu-id="22d09-107">Setting</span></span>

<span data-ttu-id="22d09-108">**SetWarnings** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="22d09-108">The **SetWarnings** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="22d09-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="22d09-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="22d09-110">说明</span><span class="sxs-lookup"><span data-stu-id="22d09-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22d09-111"><strong>打开警告</strong></span><span class="sxs-lookup"><span data-stu-id="22d09-111"><strong>Warnings On</strong></span></span></p></td>
<td><p><span data-ttu-id="22d09-p102">指定是否显示系统消息。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“打开警告”</strong>框中单击<strong>“是”</strong>（打开系统消息）或<strong>“否”</strong>（关闭系统消息）。默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="22d09-p102">Specifies whether system messages are displayed. Click <strong>Yes</strong> (to turn on system messages) or <strong>No</strong> (to turn off system messages) in the <strong>Warnings On</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder Pane. The default is <strong>No</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="22d09-115">说明</span><span class="sxs-lookup"><span data-stu-id="22d09-115">Remarks</span></span>

<span data-ttu-id="22d09-p103">可以使用此操作防止模式警告框和消息框使宏停止执行。不过，始终都会显示错误消息。另外，Microsoft Access 除了不显示只需选择一个按钮（例如， **"确定"**、 **"取消"**、 **"是"** 或 **"否"**）的对话框外，会显示任何需要输入的对话框，例如任何需要您输入文本或者选择多个选项之一的对话框。</span><span class="sxs-lookup"><span data-stu-id="22d09-p103">You can use this action to prevent modal warnings and message boxes from stopping the macro. However, error messages are always displayed. Also, Microsoft Access displays any dialog boxes that require input other than just choosing a button (such as **OK**, **Cancel**, **Yes**, or **No**) — for example, any dialog box that requires you to enter text or select one of several options.</span></span>

<span data-ttu-id="22d09-119">执行此操作与**警告**参数设置为**否**时显示警告或消息框中，按 ENTER 的效果相同。</span><span class="sxs-lookup"><span data-stu-id="22d09-119">Carrying out this action with the **Warnings On** argument set to **No** has the same effect as pressing ENTER whenever a warning or message box is displayed.</span></span> <span data-ttu-id="22d09-120">通常，响应警告或消息是选择**确定**或**是**按钮。</span><span class="sxs-lookup"><span data-stu-id="22d09-120">Typically, an **OK** or **Yes** button is chosen in response to the warning or message.</span></span>

<span data-ttu-id="22d09-121">在宏执行完后，Access 会自动打开系统消息的显示。</span><span class="sxs-lookup"><span data-stu-id="22d09-121">When the macro finishes, Access automatically turns the display of system messages back on.</span></span>

<span data-ttu-id="22d09-p105">通常，此操作将与 **Echo** 操作一起使用，后者将一直隐藏宏的执行结果，直到宏执行完。也可以使用 **SetWarnings** 操作来隐藏警告框和消息框。</span><span class="sxs-lookup"><span data-stu-id="22d09-p105">Often, you'll use this action with the **Echo** action, which hides the results of a macro until it's finished. You can use the **SetWarnings** action to hide the warnings and message boxes as well.</span></span>


> [!WARNING]
> <P><span data-ttu-id="22d09-p106">[!警告] 虽然 <STRONG>SetWarnings</STRONG> 操作可以简化与宏之间的交互，但对于关闭系统消息必须要谨慎。在一些情况下，如果出现某条警告消息，您将不希望再继续执行宏。除非您对所有宏操作的执行结果有把握，否则应该避免使用此操作。</span><span class="sxs-lookup"><span data-stu-id="22d09-p106">Although the <STRONG>SetWarnings</STRONG> action can simplify interactions with macros, you must be careful about turning system messages off. In some situations, you won't want to continue a macro if a certain warning message is displayed. Unless you're confident of the outcome of all macro actions, you should avoid using this action.</span></span></P>



<span data-ttu-id="22d09-127">要在 Visual Basic for Applications (VBA) 模块中运行 **SetWarnings** 操作，请使用 **DoCmd** 对象的 **SetWarnings** 方法。</span><span class="sxs-lookup"><span data-stu-id="22d09-127">To run the **SetWarnings** action in a Visual Basic for Applications (VBA) module, use the **SetWarnings** method of the **DoCmd** object.</span></span>

