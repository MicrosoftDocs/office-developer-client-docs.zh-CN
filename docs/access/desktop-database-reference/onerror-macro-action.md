---
title: OnError 宏操作
TOCTitle: OnError macro action
ms:assetid: 5c6073c4-2c0f-0ed2-83b0-477636e2d81c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194562(v=office.15)
ms:contentKeyID: 48545088
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm62274
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a2288d64241f3289505a8b0fafb98062830b0e97
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288453"
---
# <a name="onerror-macro-action"></a><span data-ttu-id="87a3c-102">OnError 宏操作</span><span class="sxs-lookup"><span data-stu-id="87a3c-102">OnError macro action</span></span>

<span data-ttu-id="87a3c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="87a3c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="87a3c-104">可以使用 **OnError** 操作指定在宏中发生错误时应出现的情况。</span><span class="sxs-lookup"><span data-stu-id="87a3c-104">You can use the **OnError** action to specify what should happen when an error occurs in a macro.</span></span>

## <a name="setting"></a><span data-ttu-id="87a3c-105">Setting</span><span class="sxs-lookup"><span data-stu-id="87a3c-105">Setting</span></span>

<span data-ttu-id="87a3c-106">**OnError** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="87a3c-106">The **OnError** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="87a3c-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="87a3c-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="87a3c-108">说明</span><span class="sxs-lookup"><span data-stu-id="87a3c-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a3c-109">转到</span><span class="sxs-lookup"><span data-stu-id="87a3c-109">Go to</span></span></p></td>
<td><p><span data-ttu-id="87a3c-p101">指定在遇到错误时所应发生的一般行为。请单击下拉箭头，然后单击下列设置之一：</span><span class="sxs-lookup"><span data-stu-id="87a3c-p101">Specify the general behavior that should occur when an error is encountered. Click the drop-down arrow and then click one of the following settings:</span></span></p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="87a3c-112">Setting</span><span class="sxs-lookup"><span data-stu-id="87a3c-112">Setting</span></span></p></th>
<th><p><span data-ttu-id="87a3c-113">说明</span><span class="sxs-lookup"><span data-stu-id="87a3c-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a3c-114"><strong>Next</strong></span><span class="sxs-lookup"><span data-stu-id="87a3c-114"><strong>Next</strong></span></span></p></td>
<td><p><span data-ttu-id="87a3c-p102">Microsoft Office Access 2007 在 <strong>MacroError</strong> 对象中记录错误的详细信息，但不会停止该宏。该宏将继续执行下一操作。</span><span class="sxs-lookup"><span data-stu-id="87a3c-p102">Microsoft Office Access 2007 records the details of the error in the <strong>MacroError</strong> object but does not stop the macro. The macro continues with the next action.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a3c-117"><strong>宏名</strong></span><span class="sxs-lookup"><span data-stu-id="87a3c-117"><strong>Macro Name</strong></span></span></p></td>
<td><p><span data-ttu-id="87a3c-118">Access 停止当前的宏并运行在“宏名”<strong></strong>参数中命名的宏。</span><span class="sxs-lookup"><span data-stu-id="87a3c-118">Access stops the current macro and runs the macro that is named in the <strong>Macro Name</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87a3c-119"><strong>失败</strong></span><span class="sxs-lookup"><span data-stu-id="87a3c-119"><strong>Fail</strong></span></span></p></td>
<td><p><span data-ttu-id="87a3c-120">Access 停止当前的宏并显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="87a3c-120">Access stops the current macro and displays an error message.</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a3c-121">宏名</span><span class="sxs-lookup"><span data-stu-id="87a3c-121">Macro Name</span></span></p></td>
<td><p><span data-ttu-id="87a3c-122">如果 "转到" 参数设置为 "宏名", 请键入要用于错误处理的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="87a3c-122">If the Go to argument is set to Macro Name, type the name of the macro to be used for error handling.</span></span> <span data-ttu-id="87a3c-123">键入的名称必须与当前宏的 "<strong>宏名称</strong>" 列中的名称相匹配;不能输入一个不同的宏对象的名称。</span><span class="sxs-lookup"><span data-stu-id="87a3c-123">The name you type must match a name in the <strong>Macro Name</strong> column of the current macro; you can't enter the name of a different macro object.</span></span> <span data-ttu-id="87a3c-124">在下面的示例中, <strong>ErrorHandler</strong>宏包含在与<strong>OnError</strong>操作相同的宏对象中。</span><span class="sxs-lookup"><span data-stu-id="87a3c-124">In the example below, the <strong>ErrorHandler</strong> macro is contained in the same macro object as the <strong>OnError</strong> action.</span></span> <span data-ttu-id="87a3c-125">如果 "转到" 参数设置为 "<strong>下一个</strong>" 或 "<strong>失败</strong>", 则此参数必须为空。</span><span class="sxs-lookup"><span data-stu-id="87a3c-125">This argument must be left blank if the Go to argument is set to <strong>Next</strong> or <strong>Fail</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="87a3c-126">注解</span><span class="sxs-lookup"><span data-stu-id="87a3c-126">Remarks</span></span>

- <span data-ttu-id="87a3c-p104">**OnError** 操作通常放在宏的开头，但您也可以将该操作放在宏中比较靠后的位置。该操作建立的规则会在其每次运行时生效。</span><span class="sxs-lookup"><span data-stu-id="87a3c-p104">The **OnError** action is usually placed at the beginning of a macro, but you can also place the action later in the macro. The rules established by the action will take effect whenever the action is run.</span></span>

- <span data-ttu-id="87a3c-129">If you set the Go to argument to **Fail**, Access behaves the same way it would if there were no **OnError** action in the macro.</span><span class="sxs-lookup"><span data-stu-id="87a3c-129">If you set the Go to argument to **Fail**, Access behaves the same way it would if there were no **OnError** action in the macro.</span></span> <span data-ttu-id="87a3c-130">That is, if an error is encountered, Access stops the macro and displays a standard error message.</span><span class="sxs-lookup"><span data-stu-id="87a3c-130">That is, if an error is encountered, Access stops the macro and displays a standard error message.</span></span> <span data-ttu-id="87a3c-131">The main use for the **Fail** setting is to turn off any error handling that you established earlier in a macro.</span><span class="sxs-lookup"><span data-stu-id="87a3c-131">The main use for the **Fail** setting is to turn off any error handling that you established earlier in a macro.</span></span>

## <a name="example"></a><span data-ttu-id="87a3c-132">示例</span><span class="sxs-lookup"><span data-stu-id="87a3c-132">Example</span></span>

<span data-ttu-id="87a3c-133">下面的宏演示如何使用 **OnError** 操作。</span><span class="sxs-lookup"><span data-stu-id="87a3c-133">The following macro demonstrates the use of the **OnError** action.</span></span> <span data-ttu-id="87a3c-134">在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。</span><span class="sxs-lookup"><span data-stu-id="87a3c-134">In this example, the **OnError** action specifies that Access run a custom error handling macro named ErrorHandler when an error occurs.</span></span> <span data-ttu-id="87a3c-135">发生错误时, 将调用 CatchErrors submacro。</span><span class="sxs-lookup"><span data-stu-id="87a3c-135">When an error occurs, the CatchErrors submacro is called.</span></span> <span data-ttu-id="87a3c-136">如果错误号为 2102, 则显示一条特定消息, 并停止宏的执行。</span><span class="sxs-lookup"><span data-stu-id="87a3c-136">If the error number is 2102, a specific message is displayed and macro execution is halted.</span></span> <span data-ttu-id="87a3c-137">否则, 将显示描述错误的消息, 并暂停宏, 以便您可以执行其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="87a3c-137">Otherwise, a message describing the error is displayed and the macro is paused so that you can perform additional troubleshooting.</span></span> <span data-ttu-id="87a3c-138">ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="87a3c-138">The ErrorHandler macro displays a message box that refers to the **MacroError** object to display information about the error.</span></span>

<span data-ttu-id="87a3c-139">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="87a3c-139">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    /* MACRO: mcrThrowErrors                                  */
    /* PURPOSE: Error handling using macros in Access 2010    */
    
    OnError
        Go to Macro Name
        Macro Name CatchErrors
    
    OpenForm 
        Form Name frmSamples
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    MessageBox 
        Message This message appears after the OpenForm action
        Beep Yes
        Type None
        Title
    
    
    /* SUBMACRO: CatchErrors                                   */
    
    SubMacro: CatchErrors
        If [MacroError].[Number]=2101 Then
            MessageBox
                Message Cannot find the specified form!
                Beep Yes
                Type Critical
                Title
            StopMacro
    
        Else
            MessageBox
                Message =[MacroErro].[Description]
                Beep Yes
                Type None
                Title Unhandled Error
    
            SingleStep
        End If
    
    End SubMacro
```
