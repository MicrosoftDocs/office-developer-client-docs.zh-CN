---
title: CancelEvent 宏操作
TOCTitle: CancelEvent Macro Action
ms:assetid: d9d3ea99-c9fb-2524-c570-e3ee6d20af98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835110(v=office.15)
ms:contentKeyID: 48548066
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm78430
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 52822d45b30c631dcabe3c38b6722398e96f489f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468080"
---
# <a name="cancelevent-macro-action"></a><span data-ttu-id="3b68e-102">CancelEvent 宏操作</span><span class="sxs-lookup"><span data-stu-id="3b68e-102">CancelEvent Macro Action</span></span>


<span data-ttu-id="3b68e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3b68e-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="3b68e-104">您可以使用**CancelEvent**操作取消导致访问权限才能运行包含此操作的宏的事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-104">You can use the **CancelEvent** action to cancel the event that caused Access to run the macro containing this action.</span></span> <span data-ttu-id="3b68e-105">宏名称是 **BeforeUpdate** 、 **OnOpen** 、 **OnUnload** 或 **OnPrint** 等事件属性的设置。</span><span class="sxs-lookup"><span data-stu-id="3b68e-105">The macro name is the setting of an event property such as **BeforeUpdate**, **OnOpen**, **OnUnload**, or **OnPrint**.</span></span>

## <a name="setting"></a><span data-ttu-id="3b68e-106">设置</span><span class="sxs-lookup"><span data-stu-id="3b68e-106">Setting</span></span>

<span data-ttu-id="3b68e-107">**CancelEvent** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="3b68e-107">The **CancelEvent** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b68e-108">说明</span><span class="sxs-lookup"><span data-stu-id="3b68e-108">Remarks</span></span>

<span data-ttu-id="3b68e-p102">在窗体中，通常是在验证宏中将 **CancelEvent** 操作与 **BeforeUpdate** 事件属性搭配使用。当用户在控件或记录中输入数据时，Access 会先运行该宏，然后再将数据添加到数据库中。如果数据不符合该宏中的验证条件， **CancelEvent** 操作将在更新进程开始前将其取消。</span><span class="sxs-lookup"><span data-stu-id="3b68e-p102">In a form, you typically use the **CancelEvent** action in a validation macro with the **BeforeUpdate** event property. When a user enters data in a control or record, Access runs the macro before adding the data to the database. If the data fails the validation conditions in the macro, the **CancelEvent** action cancels the update process before it starts.</span></span>

<span data-ttu-id="3b68e-112">此操作通常与 **MessageBox** 操作搭配使用，以指示数据不符合验证条件，并提供有关应输入何种数据类型的帮助信息。</span><span class="sxs-lookup"><span data-stu-id="3b68e-112">Often, you use this action with the **MessageBox** action to indicate that the data has failed the validation conditions and to provide helpful information about the kind of data that should be entered.</span></span>

<span data-ttu-id="3b68e-113">以下事件可由 **CancelEvent** 操作取消。</span><span class="sxs-lookup"><span data-stu-id="3b68e-113">The following events can be canceled by the **CancelEvent** action.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-114"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-114"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-115"><strong>Dirty</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-115"><strong>Dirty</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-116"><strong>MouseDown</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-116"><strong>MouseDown</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-117"><strong>BeforeDelConfirm</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-117"><strong>BeforeDelConfirm</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-118"><strong>退出</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-118"><strong>Exit</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-119"><strong>NoData</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-119"><strong>NoData</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-120"><strong>BeforeInsert</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-120"><strong>BeforeInsert</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-121"><strong>Filter</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-121"><strong>Filter</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-122"><strong>Open</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-122"><strong>Open</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-123"><strong>BeforeUpdate</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-123"><strong>BeforeUpdate</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-124"><strong>Format</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-124"><strong>Format</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-125"><strong>Print</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-125"><strong>Print</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-126"><strong>DblClick</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-126"><strong>DblClick</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-127"><strong>KeyPress</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-127"><strong>KeyPress</strong></span></span></p></td>
<td><p><span data-ttu-id="3b68e-128"><strong>卸载</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-128"><strong>Unload</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-129"><strong>Delete</strong></span><span class="sxs-lookup"><span data-stu-id="3b68e-129"><strong>Delete</strong></span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="3b68e-130">[!注释] 对 <STRONG>MouseDown</STRONG> 事件应用 <STRONG>CancelEvent</STRONG> 操作时，只能取消右键单击对象时发生的事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-130">You can use the <STRONG>CancelEvent</STRONG> action with the <STRONG>MouseDown</STRONG> event only to cancel the event that occurs when you right-click an object.</span></span></P>



<span data-ttu-id="3b68e-131">如果控件的 **OnDblClick** 事件属性设置指定了一个包含 **CancelEvent** 操作的宏，该操作会取消 **DblClick** 事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-131">If a control's **OnDblClick** event property setting specifies a macro containing the **CancelEvent** action, the action cancels the **DblClick** event.</span></span>

<span data-ttu-id="3b68e-p103">对于可被取消的事件，在对其运行相应的宏后，将会发生该事件的默认行为（即 Access 在事件发生时的通常处理方式）。您可以基于此机制取消默认行为。例如，在双击插入点位于文本框中的某个单词时，Access 通常会选中该单词。您可以在 **DblClick** 事件的宏中取消此默认行为并执行某种其他操作，例如打开一个包含有关文本框中的数据的信息的窗体。对于无法取消的事件，则会在宏运行前发生默认行为。</span><span class="sxs-lookup"><span data-stu-id="3b68e-p103">For events that can be canceled, the default behavior for the event (that is, what Access typically does when the event occurs) occurs after the macro for the event runs. This enables you to cancel the default behavior. For example, when you double-click a word that the insertion point is on in a text box, Access normally selects the word. You can cancel this default behavior in the macro for the **DblClick** event and perform some other action, such as opening a form containing information about the data in the text box. For events that can't be canceled, the default behavior occurs before the macro runs.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3b68e-p104">[!注释] 如果窗体的 <STRONG>OnUnload</STRONG> 事件属性指定了一个执行 <STRONG>CancelEvent</STRONG> 操作的宏，则无法关闭该窗体。您必须更正导致执行 <STRONG>CancelEvent</STRONG> 操作的条件，或打开该宏并删除 <STRONG>CancelEvent</STRONG> 操作。如果该窗体是一个模式窗体，则无法打开该宏。</span><span class="sxs-lookup"><span data-stu-id="3b68e-p104">If a form's <STRONG>OnUnload</STRONG> event property specifies a macro that carries out a <STRONG>CancelEvent</STRONG> action, you won't be able to close the form. You must either correct the condition that caused the <STRONG>CancelEvent</STRONG> action to be carried out or open the macro and delete the <STRONG>CancelEvent</STRONG> action. If the form is a modal form, you won't be able to open the macro.</span></span></P>



<span data-ttu-id="3b68e-140">要在 Visual Basic for Applications (VBA) 模块中执行 **CancelEvent** 操作，请使用 **DoCmd** 对象的 **CancelEvent** 方法。</span><span class="sxs-lookup"><span data-stu-id="3b68e-140">To carry out the **CancelEvent** action in a Visual Basic for Applications (VBA) module, use the **CancelEvent** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="3b68e-141">示例</span><span class="sxs-lookup"><span data-stu-id="3b68e-141">Example</span></span>

<span data-ttu-id="3b68e-142"> 使用宏验证数据</span><span class="sxs-lookup"><span data-stu-id="3b68e-142">Validate data by using a macro</span></span>

<span data-ttu-id="3b68e-p105">下面的验证宏会检查在"供应商"窗体中输入的邮政编码。它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。如果邮政编码的格式与国家/地区不符，该宏将显示一个消息框并取消对该记录的保存操作。随后将返回到"邮政编码"控件，以便您更正错误。此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。</span><span class="sxs-lookup"><span data-stu-id="3b68e-p105">The following validation macro checks the postal codes entered in a Suppliers form. It shows the use of the **StopMacro**, **MessageBox**, **CancelEvent**, and **GoToControl** actions. A conditional expression checks the country/region and postal code entered in a record on the form. If the postal code is not in the right format for the country/region, the macro displays a message box and cancels saving the record. It then returns you to the Postal Code control, where you can correct the error. This macro should be attached to the **BeforeUpdate** property of the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3b68e-149">条件</span><span class="sxs-lookup"><span data-stu-id="3b68e-149">Condition</span></span></p></th>
<th><p><span data-ttu-id="3b68e-150">操作</span><span class="sxs-lookup"><span data-stu-id="3b68e-150">Action</span></span></p></th>
<th><p><span data-ttu-id="3b68e-151">参数：设置</span><span class="sxs-lookup"><span data-stu-id="3b68e-151">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="3b68e-152">注释</span><span class="sxs-lookup"><span data-stu-id="3b68e-152">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-153">IsNull([CountryRegion])</span><span class="sxs-lookup"><span data-stu-id="3b68e-153">IsNull([CountryRegion])</span></span></p></td>
<td><p><span data-ttu-id="3b68e-154">StopMacro</span><span class="sxs-lookup"><span data-stu-id="3b68e-154">StopMacro</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-155">国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</span><span class="sxs-lookup"><span data-stu-id="3b68e-155">If CountryRegion is <strong>Null</strong>, postal code can't be validated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-156">[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) And Len （[邮政编码]） &lt; &gt; 5</span><span class="sxs-lookup"><span data-stu-id="3b68e-156">[CountryRegion] In (&quot;France&quot;,&quot;Italy&quot;,&quot;Spain&quot;) And Len([Postal Code]) &lt;&gt; 5</span></span></p></td>
<td><p><span data-ttu-id="3b68e-157">MessageBox</span><span class="sxs-lookup"><span data-stu-id="3b68e-157">MessageBox</span></span></p></td>
<td><p><span data-ttu-id="3b68e-158">消息：邮政编码必须为 5 个字符。 

</span><span class="sxs-lookup"><span data-stu-id="3b68e-158">Message: The postal code must be 5 characters.</span></span> <span data-ttu-id="3b68e-159">发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="3b68e-159">Beep: <strong>Yes</strong> Type: <strong>Information</strong> Title: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3b68e-160">如果邮政编码不是 5 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="3b68e-160">If the postal code isn't 5 characters, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-161">...</span><span class="sxs-lookup"><span data-stu-id="3b68e-161"></span></span></p></td>
<td><p><span data-ttu-id="3b68e-162">CancelEvent</span><span class="sxs-lookup"><span data-stu-id="3b68e-162">CancelEvent</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-163">取消事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-163">Cancel the event.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-164">GoToControl</span><span class="sxs-lookup"><span data-stu-id="3b68e-164">GoToControl</span></span></p></td>
<td><p><span data-ttu-id="3b68e-165">控件名称：邮政编码</span><span class="sxs-lookup"><span data-stu-id="3b68e-165">Control Name: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-166">[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) And Len （[邮政编码]） &lt; &gt; 4</span><span class="sxs-lookup"><span data-stu-id="3b68e-166">[CountryRegion] In (&quot;Australia&quot;,&quot;Singapore&quot;) And Len([Postal Code]) &lt;&gt; 4</span></span></p></td>
<td><p><span data-ttu-id="3b68e-167">MessageBox</span><span class="sxs-lookup"><span data-stu-id="3b68e-167">MessageBox</span></span></p></td>
<td><p><span data-ttu-id="3b68e-168">消息：邮政编码必须为 4 个字符。 

</span><span class="sxs-lookup"><span data-stu-id="3b68e-168">Message: The postal code must be 4 characters.</span></span> <span data-ttu-id="3b68e-169">发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="3b68e-169">Beep: <strong>Yes</strong> Type: <strong>Information</strong> Title: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3b68e-170">如果邮政编码不是 4 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="3b68e-170">If the postal code isn't 4 characters, display a message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-171">...</span><span class="sxs-lookup"><span data-stu-id="3b68e-171"></span></span></p></td>
<td><p><span data-ttu-id="3b68e-172">CancelEvent</span><span class="sxs-lookup"><span data-stu-id="3b68e-172">CancelEvent</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-173">取消事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-173">Cancel the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-174">GoToControl</span><span class="sxs-lookup"><span data-stu-id="3b68e-174">GoToControl</span></span></p></td>
<td><p><span data-ttu-id="3b68e-175">控件名称：邮政编码</span><span class="sxs-lookup"><span data-stu-id="3b68e-175">Control Name: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b68e-176">([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</span><span class="sxs-lookup"><span data-stu-id="3b68e-176">([CountryRegion] = &quot;Canada&quot;) And ([Postal Code] Not Like&quot;[A-Z][0-9][A-Z] [0-9][A-Z][0-9]&quot;)</span></span></p></td>
<td><p><span data-ttu-id="3b68e-177">MessageBox</span><span class="sxs-lookup"><span data-stu-id="3b68e-177">MessageBox</span></span></p></td>
<td><p><span data-ttu-id="3b68e-178">消息： 邮政编码不是有效的。</span><span class="sxs-lookup"><span data-stu-id="3b68e-178">Message: The postal code is not valid.</span></span> <span data-ttu-id="3b68e-179">加拿大代码示例： H1J 1c3 发嘟嘟声:<strong>是</strong>类型：<strong>信息</strong>标题： 邮政编码代码错误</span><span class="sxs-lookup"><span data-stu-id="3b68e-179">Example of Canadian code: H1J 1C3 Beep: <strong>Yes</strong> Type: <strong>Information</strong> Title: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="3b68e-p109">如果邮政编码不符合加拿大格式，则显示一条消息。（加拿大邮政编码示例：H1J 1C3）</span><span class="sxs-lookup"><span data-stu-id="3b68e-p109">If the postal code isn't correct for Canada, display a message. (Example of Canadian code: H1J 1C3)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b68e-182">...</span><span class="sxs-lookup"><span data-stu-id="3b68e-182"></span></span></p></td>
<td><p><span data-ttu-id="3b68e-183">CancelEvent</span><span class="sxs-lookup"><span data-stu-id="3b68e-183">CancelEvent</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="3b68e-184">取消事件。</span><span class="sxs-lookup"><span data-stu-id="3b68e-184">Cancel the event.</span></span></p></td>
</tr>
</tbody>
</table>
