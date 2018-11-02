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
ms.openlocfilehash: 38dc9491a03d2bfa043bddec84efd7fc12c5d08a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919120"
---
# <a name="onerror-macro-action"></a><span data-ttu-id="4b30d-102">OnError 宏操作</span><span class="sxs-lookup"><span data-stu-id="4b30d-102">OnError macro action</span></span>

<span data-ttu-id="4b30d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4b30d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4b30d-104">可以使用 **OnError** 操作指定在宏中发生错误时应出现的情况。</span><span class="sxs-lookup"><span data-stu-id="4b30d-104">You can use the **OnError** action to specify what should happen when an error occurs in a macro.</span></span>

## <a name="setting"></a><span data-ttu-id="4b30d-105">设置</span><span class="sxs-lookup"><span data-stu-id="4b30d-105">Setting</span></span>

<span data-ttu-id="4b30d-106">**OnError** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="4b30d-106">The **OnError** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4b30d-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="4b30d-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4b30d-108">说明</span><span class="sxs-lookup"><span data-stu-id="4b30d-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b30d-109">转至</span><span class="sxs-lookup"><span data-stu-id="4b30d-109">Go to</span></span></p></td>
<td><p><span data-ttu-id="4b30d-p101">指定在遇到错误时所应发生的一般行为。请单击下拉箭头，然后单击下列设置之一：</span><span class="sxs-lookup"><span data-stu-id="4b30d-p101">Specify the general behavior that should occur when an error is encountered. Click the drop-down arrow and then click one of the following settings:</span></span></p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4b30d-112">设置</span><span class="sxs-lookup"><span data-stu-id="4b30d-112">Setting</span></span></p></th>
<th><p><span data-ttu-id="4b30d-113">说明</span><span class="sxs-lookup"><span data-stu-id="4b30d-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b30d-114"><strong>下一步</strong></span><span class="sxs-lookup"><span data-stu-id="4b30d-114"><strong>Next</strong></span></span></p></td>
<td><p><span data-ttu-id="4b30d-p102">Microsoft Office Access 2007 在 <strong>MacroError</strong> 对象中记录错误的详细信息，但不会停止该宏。该宏将继续执行下一操作。</span><span class="sxs-lookup"><span data-stu-id="4b30d-p102">Microsoft Office Access 2007 records the details of the error in the <strong>MacroError</strong> object but does not stop the macro. The macro continues with the next action.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b30d-117"><strong>宏名</strong></span><span class="sxs-lookup"><span data-stu-id="4b30d-117"><strong>Macro Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4b30d-118">Access 停止当前的宏并运行宏的名为<strong>宏名称</strong>参数中。</span><span class="sxs-lookup"><span data-stu-id="4b30d-118">Access stops the current macro and runs the macro that is named in the <strong>Macro Name</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b30d-119"><strong>失败</strong></span><span class="sxs-lookup"><span data-stu-id="4b30d-119"><strong>Fail</strong></span></span></p></td>
<td><p><span data-ttu-id="4b30d-120">Access 停止当前的宏并显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="4b30d-120">Access stops the current macro and displays an error message.</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b30d-121">宏名</span><span class="sxs-lookup"><span data-stu-id="4b30d-121">Macro Name</span></span></p></td>
<td><p><span data-ttu-id="4b30d-122">如果将转到参数设置为宏名，键入要用于错误处理的宏的名称。</span><span class="sxs-lookup"><span data-stu-id="4b30d-122">If the Go to argument is set to Macro Name, type the name of the macro to be used for error handling.</span></span> <span data-ttu-id="4b30d-123">键入的名称必须与当前的宏;<strong>宏名称</strong>列中的名称相匹配不能输入不同宏对象的名称。</span><span class="sxs-lookup"><span data-stu-id="4b30d-123">The name you type must match a name in the <strong>Macro Name</strong> column of the current macro; you can't enter the name of a different macro object.</span></span> <span data-ttu-id="4b30d-124">在下面的示例中， <strong>ErrorHandler</strong>宏包含在相同<strong>OnError</strong>操作的宏对象。</span><span class="sxs-lookup"><span data-stu-id="4b30d-124">In the example below, the <strong>ErrorHandler</strong> macro is contained in the same macro object as the <strong>OnError</strong> action.</span></span> <span data-ttu-id="4b30d-125">必须将此参数留空将转到参数设置为<strong>下一步</strong>或<strong>失败</strong>。</span><span class="sxs-lookup"><span data-stu-id="4b30d-125">This argument must be left blank if the Go to argument is set to <strong>Next</strong> or <strong>Fail</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4b30d-126">说明</span><span class="sxs-lookup"><span data-stu-id="4b30d-126">Remarks</span></span>

- <span data-ttu-id="4b30d-p104">**OnError** 操作通常放在宏的开头，但您也可以将该操作放在宏中比较靠后的位置。该操作建立的规则会在其每次运行时生效。</span><span class="sxs-lookup"><span data-stu-id="4b30d-p104">The **OnError** action is usually placed at the beginning of a macro, but you can also place the action later in the macro. The rules established by the action will take effect whenever the action is run.</span></span>

- <span data-ttu-id="4b30d-129">如果您将转到设置为**失败**参数时，访问同样的行为方式如果没有在宏中没有**OnError**操作。</span><span class="sxs-lookup"><span data-stu-id="4b30d-129">If you set the Go to argument to **Fail**, Access behaves the same way it would if there were no **OnError** action in the macro.</span></span> <span data-ttu-id="4b30d-130">也就是说，如果遇到错误，Access 将停止宏，并显示标准错误消息。</span><span class="sxs-lookup"><span data-stu-id="4b30d-130">That is, if an error is encountered, Access stops the macro and displays a standard error message.</span></span> <span data-ttu-id="4b30d-131">对于**失败**设置的主要用途是关闭之前在宏中建立的任何错误处理。</span><span class="sxs-lookup"><span data-stu-id="4b30d-131">The main use for the **Fail** setting is to turn off any error handling that you established earlier in a macro.</span></span>

## <a name="example"></a><span data-ttu-id="4b30d-132">示例</span><span class="sxs-lookup"><span data-stu-id="4b30d-132">Example</span></span>

<span data-ttu-id="4b30d-133">下面的宏演示如何使用 **OnError** 操作。</span><span class="sxs-lookup"><span data-stu-id="4b30d-133">The following macro demonstrates the use of the **OnError** action.</span></span> <span data-ttu-id="4b30d-134">在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。</span><span class="sxs-lookup"><span data-stu-id="4b30d-134">In this example, the **OnError** action specifies that Access run a custom error handling macro named ErrorHandler when an error occurs.</span></span> <span data-ttu-id="4b30d-135">发生错误时，调用 CatchErrors submacro。</span><span class="sxs-lookup"><span data-stu-id="4b30d-135">When an error occurs, the CatchErrors submacro is called.</span></span> <span data-ttu-id="4b30d-136">如果错误号，2102年显示特定的邮件和暂停宏执行。</span><span class="sxs-lookup"><span data-stu-id="4b30d-136">If the error number is 2102, a specific message is displayed and macro execution is halted.</span></span> <span data-ttu-id="4b30d-137">否则为显示一条描述错误消息，并将暂停该宏，以便您可以执行其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="4b30d-137">Otherwise, a message describing the error is displayed and the macro is paused so that you can perform additional troubleshooting.</span></span> <span data-ttu-id="4b30d-138">ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4b30d-138">The ErrorHandler macro displays a message box that refers to the **MacroError** object to display information about the error.</span></span>

<span data-ttu-id="4b30d-139">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="4b30d-139">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
