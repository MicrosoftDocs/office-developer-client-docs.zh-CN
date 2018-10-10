---
title: StopMacro Macro Action
TOCTitle: StopMacro Macro Action
ms:assetid: 6bbf9026-4536-43f2-aa43-3f2ecea01005
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195473(v=office.15)
ms:contentKeyID: 48545455
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a918fd128456450c21b5a36e74b7266df661cb75
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467236"
---
# <a name="stopmacro-macro-action"></a><span data-ttu-id="7ebea-102">StopMacro Macro Action</span><span class="sxs-lookup"><span data-stu-id="7ebea-102">StopMacro Macro Action</span></span>

<span data-ttu-id="7ebea-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7ebea-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7ebea-104">您可以使用**StopMacro**操作停止当前正在运行的宏。</span><span class="sxs-lookup"><span data-stu-id="7ebea-104">You can use the **StopMacro** action to stop the currently running macro.</span></span>

## <a name="setting"></a><span data-ttu-id="7ebea-105">设置</span><span class="sxs-lookup"><span data-stu-id="7ebea-105">Setting</span></span>

<span data-ttu-id="7ebea-106">**StopMacro**操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="7ebea-106">The **StopMacro** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ebea-107">说明</span><span class="sxs-lookup"><span data-stu-id="7ebea-107">Remarks</span></span>

<span data-ttu-id="7ebea-108">通常，当条件进行所需停止宏，可使用此操作。</span><span class="sxs-lookup"><span data-stu-id="7ebea-108">You typically use this action when a condition makes it necessary to stop the macro.</span></span> <span data-ttu-id="7ebea-109">可以在宏中包含此操作的操作行中使用条件表达式。</span><span class="sxs-lookup"><span data-stu-id="7ebea-109">You can use a conditional expression in the macro's action row that contains this action.</span></span> <span data-ttu-id="7ebea-110">当在表达式计算结果为**True** (– 1) 时，Microsoft Access 将停止宏。</span><span class="sxs-lookup"><span data-stu-id="7ebea-110">When the expression evaluates to **True** (–1), Microsoft Access stops the macro.</span></span>

<span data-ttu-id="7ebea-111">例如，您可能会创建的宏，打开一个窗体显示每日的顺序总计的自定义对话框中输入的日期。</span><span class="sxs-lookup"><span data-stu-id="7ebea-111">For example, you might create a macro that opens a form showing the daily order totals for the date entered in a custom dialog box.</span></span> <span data-ttu-id="7ebea-112">您可以使用的条件表达式以确保对话框上的**订单日期**控件包含有效的日期。</span><span class="sxs-lookup"><span data-stu-id="7ebea-112">You could use a conditional expression to be sure that the **Order Date** control on the dialog box contains a valid date.</span></span> <span data-ttu-id="7ebea-113">如果没有， **MessageBox**操作可以显示一条错误消息和**StopMacro**操作可以停止宏。</span><span class="sxs-lookup"><span data-stu-id="7ebea-113">If it doesn't, the **MessageBox** action can display an error message and the **StopMacro** action can stop the macro.</span></span>

<span data-ttu-id="7ebea-114">如果宏已经使用**Echo**或**SetWarnings**操作回响或系统消息的显示， **StopMacro**操作会自动将它们再打开。</span><span class="sxs-lookup"><span data-stu-id="7ebea-114">If the macro has used the **Echo** or **SetWarnings** actions to turn echo or the display of system messages off, the **StopMacro** action automatically turns them back on.</span></span>

<span data-ttu-id="7ebea-115">此操作在 Visual Basic for Applications (VBA) 模块中不可用。</span><span class="sxs-lookup"><span data-stu-id="7ebea-115">This action isn't available in a Visual Basic for Applications (VBA) module.</span></span>

## <a name="example"></a><span data-ttu-id="7ebea-116">示例</span><span class="sxs-lookup"><span data-stu-id="7ebea-116">Example</span></span>

<span data-ttu-id="7ebea-117">下面的宏演示如何使用 **OnError** 操作。</span><span class="sxs-lookup"><span data-stu-id="7ebea-117">The following macro demonstrates the use of the **OnError** action.</span></span> <span data-ttu-id="7ebea-118">在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。</span><span class="sxs-lookup"><span data-stu-id="7ebea-118">In this example, the **OnError** action specifies that Access run a custom error handling macro named ErrorHandler when an error occurs.</span></span> <span data-ttu-id="7ebea-119">发生错误时，调用 CatchErrors submacro。</span><span class="sxs-lookup"><span data-stu-id="7ebea-119">When an error occurs, the CatchErrors submacro is called.</span></span> <span data-ttu-id="7ebea-120">如果错误号，2102年显示特定的邮件和暂停宏执行。</span><span class="sxs-lookup"><span data-stu-id="7ebea-120">If the error number is 2102, a specific message is displayed and macro execution is halted.</span></span> <span data-ttu-id="7ebea-121">否则为显示一条描述错误消息，并将暂停该宏，以便您可以执行其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="7ebea-121">Otherwise, a message describing the error is displayed and the macro is paused so that you can perform additional troubleshooting.</span></span> <span data-ttu-id="7ebea-122">ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="7ebea-122">The ErrorHandler macro displays a message box that refers to the **MacroError** object to display information about the error.</span></span>

<span data-ttu-id="7ebea-123">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="7ebea-123">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
