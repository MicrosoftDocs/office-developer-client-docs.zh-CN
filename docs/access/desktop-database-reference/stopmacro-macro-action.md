---
title: StopMacro 宏操作
TOCTitle: StopMacro macro action
ms:assetid: 6bbf9026-4536-43f2-aa43-3f2ecea01005
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195473(v=office.15)
ms:contentKeyID: 48545455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fe319e0f7a811d3bcd3b2fc18c4a3d951187fbe8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308496"
---
# <a name="stopmacro-macro-action"></a><span data-ttu-id="23037-102">StopMacro 宏操作</span><span class="sxs-lookup"><span data-stu-id="23037-102">StopMacro macro action</span></span>

<span data-ttu-id="23037-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="23037-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="23037-104">您可以使用**StopMacro**操作来停止当前正在运行的宏。</span><span class="sxs-lookup"><span data-stu-id="23037-104">You can use the **StopMacro** action to stop the currently running macro.</span></span>

## <a name="setting"></a><span data-ttu-id="23037-105">Setting</span><span class="sxs-lookup"><span data-stu-id="23037-105">Setting</span></span>

<span data-ttu-id="23037-106">**StopMacro**操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="23037-106">The **StopMacro** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="23037-107">注解</span><span class="sxs-lookup"><span data-stu-id="23037-107">Remarks</span></span>

<span data-ttu-id="23037-108">通常在条件导致需要停止宏时使用此操作。</span><span class="sxs-lookup"><span data-stu-id="23037-108">You typically use this action when a condition makes it necessary to stop the macro.</span></span> <span data-ttu-id="23037-109">可以在宏中包含此操作的操作行中使用条件表达式。</span><span class="sxs-lookup"><span data-stu-id="23037-109">You can use a conditional expression in the macro's action row that contains this action.</span></span> <span data-ttu-id="23037-110">当表达式的计算结果为**True** (– 1) 时, Microsoft Access 将停止宏。</span><span class="sxs-lookup"><span data-stu-id="23037-110">When the expression evaluates to **True** (–1), Microsoft Access stops the macro.</span></span>

<span data-ttu-id="23037-111">例如, 您可以创建一个宏, 打开一个窗体, 该窗体显示在自定义对话框中输入的日期的每日订单总数。</span><span class="sxs-lookup"><span data-stu-id="23037-111">For example, you might create a macro that opens a form showing the daily order totals for the date entered in a custom dialog box.</span></span> <span data-ttu-id="23037-112">您可以使用条件表达式, 以确保对话框上的 "**排序日期**" 控件包含有效的日期。</span><span class="sxs-lookup"><span data-stu-id="23037-112">You could use a conditional expression to be sure that the **Order Date** control on the dialog box contains a valid date.</span></span> <span data-ttu-id="23037-113">如果不是这样, 则**MessageBox**操作可以显示一条错误消息, 并且**StopMacro**操作可以停止宏。</span><span class="sxs-lookup"><span data-stu-id="23037-113">If it doesn't, the **MessageBox** action can display an error message and the **StopMacro** action can stop the macro.</span></span>

<span data-ttu-id="23037-114">如果宏已经使用**echo**或**SetWarnings**操作关闭了回响或系统消息的显示, 则**StopMacro**操作会自动将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="23037-114">If the macro has used the **Echo** or **SetWarnings** actions to turn echo or the display of system messages off, the **StopMacro** action automatically turns them back on.</span></span>

<span data-ttu-id="23037-115">此操作在 Visual Basic for Applications (VBA) 模块中不可用。</span><span class="sxs-lookup"><span data-stu-id="23037-115">This action isn't available in a Visual Basic for Applications (VBA) module.</span></span>

## <a name="example"></a><span data-ttu-id="23037-116">示例</span><span class="sxs-lookup"><span data-stu-id="23037-116">Example</span></span>

<span data-ttu-id="23037-117">下面的宏演示如何使用 **OnError** 操作。</span><span class="sxs-lookup"><span data-stu-id="23037-117">The following macro demonstrates the use of the **OnError** action.</span></span> <span data-ttu-id="23037-118">在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。</span><span class="sxs-lookup"><span data-stu-id="23037-118">In this example, the **OnError** action specifies that Access run a custom error handling macro named ErrorHandler when an error occurs.</span></span> <span data-ttu-id="23037-119">发生错误时, 将调用 CatchErrors submacro。</span><span class="sxs-lookup"><span data-stu-id="23037-119">When an error occurs, the CatchErrors submacro is called.</span></span> <span data-ttu-id="23037-120">如果错误号为 2102, 则显示一条特定消息, 并停止宏的执行。</span><span class="sxs-lookup"><span data-stu-id="23037-120">If the error number is 2102, a specific message is displayed and macro execution is halted.</span></span> <span data-ttu-id="23037-121">否则, 将显示描述错误的消息, 并暂停宏, 以便您可以执行其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="23037-121">Otherwise, a message describing the error is displayed and the macro is paused so that you can perform additional troubleshooting.</span></span> <span data-ttu-id="23037-122">ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="23037-122">The ErrorHandler macro displays a message box that refers to the **MacroError** object to display information about the error.</span></span>

<span data-ttu-id="23037-123">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="23037-123">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
