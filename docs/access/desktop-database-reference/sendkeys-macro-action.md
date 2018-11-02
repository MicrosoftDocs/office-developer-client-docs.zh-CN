---
title: SendKeys 宏操作
TOCTitle: SendKeys macro action
ms:assetid: 3b06fcfc-ea64-c780-b5fc-6fc72853f524
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192656(v=office.15)
ms:contentKeyID: 48544275
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm183441
f1_categories:
- Office.Version=v15
ms.openlocfilehash: aa029e3a81670746cdc467ddf7578c5900b58b29
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929032"
---
# <a name="sendkeys-macro-action"></a><span data-ttu-id="530f9-102">SendKeys 宏操作</span><span class="sxs-lookup"><span data-stu-id="530f9-102">SendKeys macro action</span></span>


<span data-ttu-id="530f9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="530f9-103">**Applies to**: Access 2013, Office 2013</span></span>

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全说明" alt="Security note" /><span data-ttu-id="530f9-105"><strong>安全注释</strong></span><span class="sxs-lookup"><span data-stu-id="530f9-105"><strong>Security Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="530f9-p101">
      避免使用 <strong>SendKeys</strong> 语句或带敏感或机密信息的 AutoKeys 宏。恶意用户可能会拦截键击并损害您的计算机和数据的安全性。
</span><span class="sxs-lookup"><span data-stu-id="530f9-p101">Avoid using the <strong>SendKeys</strong> statement or an AutoKeys macro with sensitive or confidential information. A malicious user could intercept the keystrokes and compromise the security of your computer and data.</span></span></td>
</tr>
</tbody>
</table>


<span data-ttu-id="530f9-108">可以使用 **SendKeys** 操作直接向 Microsoft Access 或基于 Windows 的活动应用程序发送键击。</span><span class="sxs-lookup"><span data-stu-id="530f9-108">You can use the **SendKeys** action to send keystrokes directly to Microsoft Access or to an active Windows-based application.</span></span>


> [!NOTE]
> <P><span data-ttu-id="530f9-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="530f9-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="530f9-111">设置</span><span class="sxs-lookup"><span data-stu-id="530f9-111">Setting</span></span>

<span data-ttu-id="530f9-112">**SendKeys** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="530f9-112">The **SendKeys** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="530f9-113">操作参数</span><span class="sxs-lookup"><span data-stu-id="530f9-113">Action argument</span></span></p></th>
<th><p><span data-ttu-id="530f9-114">说明</span><span class="sxs-lookup"><span data-stu-id="530f9-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="530f9-115"><strong>键击</strong></span><span class="sxs-lookup"><span data-stu-id="530f9-115"><strong>Keystrokes</strong></span></span></p></td>
<td><p><span data-ttu-id="530f9-p103">想让 Access 或其他应用程序处理的键击。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“键击”</strong>框中输入键击。最多可以键入 255 个字符。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="530f9-p103">The keystrokes you want Access or the application to process. Enter the keystrokes in the <strong>Keystrokes</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. You can type up to 255 characters. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="530f9-120"><strong>Wait</strong></span><span class="sxs-lookup"><span data-stu-id="530f9-120"><strong>Wait</strong></span></span></p></td>
<td><p><span data-ttu-id="530f9-p104">指定在处理完键击之前宏是否应该暂停。请单击<strong>“是”</strong>（暂停）或<strong>“否”</strong>（不暂停）。默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="530f9-p104">Specifies whether the macro should pause until the keystrokes have been processed. Click <strong>Yes</strong> (to pause) or <strong>No</strong> (to not pause). The default is <strong>No</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="530f9-124">说明</span><span class="sxs-lookup"><span data-stu-id="530f9-124">Remarks</span></span>

<span data-ttu-id="530f9-125">Access 处理通过 **SendKeys** 操作接收的键击，就好像您已经直接在 Access 窗口中键入它们一样。</span><span class="sxs-lookup"><span data-stu-id="530f9-125">Access processes the keystrokes it receives through the **SendKeys** action exactly as if you had typed them directly in an Access window.</span></span>

<span data-ttu-id="530f9-126">要指定键击，请使用用于 **SendKeys** 语句的语法。</span><span class="sxs-lookup"><span data-stu-id="530f9-126">To specify the keystrokes, use the same syntax as you would for the **SendKeys** statement.</span></span>


> [!NOTE]
> <P><span data-ttu-id="530f9-127">如果<STRONG>键击</STRONG>参数包含不正确的语法、 拼写错误的文本或其他不适合键击发送到的窗口的值，则可以发生错误。</span><span class="sxs-lookup"><span data-stu-id="530f9-127">An error can occur if the <STRONG>Keystrokes</STRONG> argument contains incorrect syntax, misspelled text, or other values that aren't appropriate for the window the keystrokes are sent to.</span></span></P>



<span data-ttu-id="530f9-p105">可以使用此操作在对话框中输入信息，尤其是在您不想中断宏的执行来手动响应对话框时。有些 Access 操作（例如 **PrintOut** 和 **FindRecord** ）会自动选择某些常用对话框中的选项。可以使用 **SendKeys** 操作选择不常用的对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="530f9-p105">You can use this action to enter information in a dialog box, particularly if you don't want to interrupt the macro to respond manually to the dialog box. Some Access actions, such as **PrintOut** and **FindRecord**, automatically select the options in certain frequently used dialog boxes. You can use the **SendKeys** action to select the options in less commonly used dialog boxes.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="530f9-131">由于对话框会暂停宏，您必须将<STRONG>SendKeys</STRONG>操作之前，导致对话框打开并将<STRONG>等待</STRONG>参数设置为<STRONG>否</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="530f9-131">Because the dialog box suspends the macro, you must put the <STRONG>SendKeys</STRONG> action before the action that causes the dialog box to open and set the <STRONG>Wait</STRONG> argument to <STRONG>No</STRONG>.</span></span></P>
> <LI>
> <P><span data-ttu-id="530f9-p106">键击到达 Access 或其他应用程序的时间难以确定。因此，在有其他方法（如 <STRONG>FindRecord</STRONG> 操作）可用来完成需要的任务时，建议您使用其他方法，而不要使用 <STRONG>SendKeys</STRONG> 操作来填写对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="530f9-p106">The timing of the keystrokes reaching Access or another application can be tricky. As a result, it's recommended that if there's some other method (such as the <STRONG>FindRecord</STRONG> action) you can use to achieve a desired task, use that method rather than using the <STRONG>SendKeys</STRONG> action to fill in the options in a dialog box.</span></span></P></LI></UL>



<span data-ttu-id="530f9-134">如果希望向 Access 或其他基于 Windows 的应用程序发送 255 个以上字符，可以在宏中连续使用多个 **SendKeys** 操作。</span><span class="sxs-lookup"><span data-stu-id="530f9-134">If you want to send more than 255 characters to Access or another Windows-based application, you can use several **SendKeys** actions in succession in a macro.</span></span>

<span data-ttu-id="530f9-p107">使用 **SendKeys** 操作发送键击会触发相应的 **KeyDown** 、 **KeyUp** 和 **KeyPress** 事件。发送非 ANSI 键击（如功能键）不会触发 **KeyPress** 事件。</span><span class="sxs-lookup"><span data-stu-id="530f9-p107">Using the **SendKeys** action to send keystrokes triggers the appropriate **KeyDown**, **KeyUp**, and **KeyPress** events. Sending non-ANSI keystrokes (such as a function key) doesn't trigger the **KeyPress** event.</span></span>

<span data-ttu-id="530f9-p108">此操作在 Visual Basic for Applications (VBA) 模块中不可用。请改用 **SendKeys** 语句。</span><span class="sxs-lookup"><span data-stu-id="530f9-p108">This action isn't available from a Visual Basic for Applications (VBA) module. Use the **SendKeys** statement instead.</span></span>

