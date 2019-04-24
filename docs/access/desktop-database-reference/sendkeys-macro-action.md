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
localization_priority: Normal
ms.openlocfilehash: f8c45cdf0d9cf588f61d1b51b728a8a15f6d7e12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308748"
---
# <a name="sendkeys-macro-action"></a><span data-ttu-id="fa7d7-102">SendKeys 宏操作</span><span class="sxs-lookup"><span data-stu-id="fa7d7-102">SendKeys macro action</span></span>

<span data-ttu-id="fa7d7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa7d7-103">**Applies to**: Access 2013, Office 2013</span></span>

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全注释" alt="Security note" /><span data-ttu-id="fa7d7-105"><strong>安全说明</strong></span><span class="sxs-lookup"><span data-stu-id="fa7d7-105"><strong>Security Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="fa7d7-p101">避免使用带敏感信息或机密信息的 <strong>SendKeys</strong> 语句或 AutoKeys 宏。恶意用户会截取键击，从而危及计算机和数据的安全性。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p101">Avoid using the <strong>SendKeys</strong> statement or an AutoKeys macro with sensitive or confidential information. A malicious user could intercept the keystrokes and compromise the security of your computer and data.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fa7d7-108">可以使用 **SendKeys** 操作直接向 Microsoft Access 或基于 Windows 的活动应用程序发送键击。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-108">You can use the **SendKeys** action to send keystrokes directly to Microsoft Access or to an active Windows-based application.</span></span>

> [!NOTE]
> <span data-ttu-id="fa7d7-109">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-109">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="fa7d7-110">设置</span><span class="sxs-lookup"><span data-stu-id="fa7d7-110">Setting</span></span>

<span data-ttu-id="fa7d7-111">**SendKeys** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-111">The **SendKeys** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa7d7-112">操作参数</span><span class="sxs-lookup"><span data-stu-id="fa7d7-112">Action argument</span></span></p></th>
<th><p><span data-ttu-id="fa7d7-113">说明</span><span class="sxs-lookup"><span data-stu-id="fa7d7-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa7d7-114"><strong>键击</strong></span><span class="sxs-lookup"><span data-stu-id="fa7d7-114"><strong>Keystrokes</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7d7-p102">想让 Access 或其他应用程序处理的键击。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“键击”</strong>框中输入键击。最多可以键入 255 个字符。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p102">The keystrokes you want Access or the application to process. Enter the keystrokes in the <strong>Keystrokes</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. You can type up to 255 characters. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7d7-119"><strong>Wait</strong></span><span class="sxs-lookup"><span data-stu-id="fa7d7-119"><strong>Wait</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7d7-p103">指定在处理完键击之前宏是否应该暂停。请单击<strong>“是”</strong>（暂停）或<strong>“否”</strong>（不暂停）。默认值为<strong>“否”</strong>。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p103">Specifies whether the macro should pause until the keystrokes have been processed. Click <strong>Yes</strong> (to pause) or <strong>No</strong> (to not pause). The default is <strong>No</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="fa7d7-123">注解</span><span class="sxs-lookup"><span data-stu-id="fa7d7-123">Remarks</span></span>

<span data-ttu-id="fa7d7-124">Access 处理通过 **SendKeys** 操作接收的键击，就好像您已经直接在 Access 窗口中键入它们一样。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-124">Access processes the keystrokes it receives through the **SendKeys** action exactly as if you had typed them directly in an Access window.</span></span>

<span data-ttu-id="fa7d7-125">要指定键击，请使用用于 **SendKeys** 语句的语法。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-125">To specify the keystrokes, use the same syntax as you would for the **SendKeys** statement.</span></span>

> [!NOTE]
> <span data-ttu-id="fa7d7-126">如果“键击”\*\*\*\* 参数包含不正确的语法、拼写错误的文本或者其他不适合键击要发送到的窗口的值，则可能发生错误。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-126">An error can occur if the **Keystrokes** argument contains incorrect syntax, misspelled text, or other values that aren't appropriate for the window the keystrokes are sent to.</span></span>

<span data-ttu-id="fa7d7-p104">可以使用此操作在对话框中输入信息，尤其是在您不想中断宏的执行来手动响应对话框时。有些 Access 操作（例如 **PrintOut** 和 **FindRecord** ）会自动选择某些常用对话框中的选项。可以使用 **SendKeys** 操作选择不常用的对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p104">You can use this action to enter information in a dialog box, particularly if you don't want to interrupt the macro to respond manually to the dialog box. Some Access actions, such as **PrintOut** and **FindRecord**, automatically select the options in certain frequently used dialog boxes. You can use the **SendKeys** action to select the options in less commonly used dialog boxes.</span></span>

> [!NOTE]
> - <span data-ttu-id="fa7d7-130">Because the dialog box suspends the macro, you must put the **SendKeys** action before the action that causes the dialog box to open and set the **Wait** argument to **No**.</span><span class="sxs-lookup"><span data-stu-id="fa7d7-130">Because the dialog box suspends the macro, you must put the **SendKeys** action before the action that causes the dialog box to open and set the **Wait** argument to **No**.</span></span>
> - <span data-ttu-id="fa7d7-p105">键击到达 Access 或其他应用程序的时间难以确定。因此，在有其他方法（如 **FindRecord** 操作）可用来完成需要的任务时，建议您使用其他方法，而不要使用 **SendKeys** 操作来填写对话框中的选项。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p105">The timing of the keystrokes reaching Access or another application can be tricky. As a result, it's recommended that if there's some other method (such as the **FindRecord** action) you can use to achieve a desired task, use that method rather than using the **SendKeys** action to fill in the options in a dialog box.</span></span>

<span data-ttu-id="fa7d7-133">如果希望向 Access 或其他基于 Windows 的应用程序发送 255 个以上字符，可以在宏中连续使用多个 **SendKeys** 操作。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-133">If you want to send more than 255 characters to Access or another Windows-based application, you can use several **SendKeys** actions in succession in a macro.</span></span>

<span data-ttu-id="fa7d7-p106">使用 **SendKeys** 操作发送键击会触发相应的 **KeyDown** 、 **KeyUp** 和 **KeyPress** 事件。发送非 ANSI 键击（如功能键）不会触发 **KeyPress** 事件。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p106">Using the **SendKeys** action to send keystrokes triggers the appropriate **KeyDown**, **KeyUp**, and **KeyPress** events. Sending non-ANSI keystrokes (such as a function key) doesn't trigger the **KeyPress** event.</span></span>

<span data-ttu-id="fa7d7-p107">此操作在 Visual Basic for Applications (VBA) 模块中不可用。请改用 **SendKeys** 语句。</span><span class="sxs-lookup"><span data-stu-id="fa7d7-p107">This action isn't available from a Visual Basic for Applications (VBA) module. Use the **SendKeys** statement instead.</span></span>

