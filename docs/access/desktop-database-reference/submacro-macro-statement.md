---
title: Submacro 宏语句
TOCTitle: Submacro macro statement
ms:assetid: fb580c19-52cd-c0bd-9117-4fa721eead6b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837173(v=office.15)
ms:contentKeyID: 48548867
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: caabfb0f4e90134c10d5ab728f19e1fd2a4437dd
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716192"
---
# <a name="submacro-macro-statement"></a><span data-ttu-id="7b9ed-102">Submacro 宏语句</span><span class="sxs-lookup"><span data-stu-id="7b9ed-102">Submacro macro statement</span></span>

<span data-ttu-id="7b9ed-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b9ed-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7b9ed-104">**Submacro**语句在宏设计器窗口中定义单独的宏。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-104">The **Submacro** statement defines a separate macro in the Macro Designer window.</span></span>

## <a name="setting"></a><span data-ttu-id="7b9ed-105">设置</span><span class="sxs-lookup"><span data-stu-id="7b9ed-105">Setting</span></span>

<span data-ttu-id="7b9ed-106">**Submacro** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-106">The **Submacro** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7b9ed-107">参数</span><span class="sxs-lookup"><span data-stu-id="7b9ed-107">Argument</span></span></p></th>
<th><p><span data-ttu-id="7b9ed-108">是否必需</span><span class="sxs-lookup"><span data-stu-id="7b9ed-108">Required</span></span></p></th>
<th><p><span data-ttu-id="7b9ed-109">说明</span><span class="sxs-lookup"><span data-stu-id="7b9ed-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b9ed-110">名称</span><span class="sxs-lookup"><span data-stu-id="7b9ed-110">Name</span></span></p></td>
<td><p><span data-ttu-id="7b9ed-111">是</span><span class="sxs-lookup"><span data-stu-id="7b9ed-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="7b9ed-112">一个显示为宏名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-112">A string that appears as the name of the macro.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="example"></a><span data-ttu-id="7b9ed-113">示例</span><span class="sxs-lookup"><span data-stu-id="7b9ed-113">Example</span></span>

<span data-ttu-id="7b9ed-114">下面的宏演示如何使用 **OnError** 操作。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-114">The following macro demonstrates the use of the **OnError** action.</span></span> <span data-ttu-id="7b9ed-115">在此示例中， **OnError** 操作指定 Access 在发生错误时运行名为 ErrorHandler 的自定义错误处理宏。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-115">In this example, the **OnError** action specifies that Access run a custom error handling macro named ErrorHandler when an error occurs.</span></span> <span data-ttu-id="7b9ed-116">发生错误时，调用 CatchErrors submacro。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-116">When an error occurs, the CatchErrors submacro is called.</span></span> <span data-ttu-id="7b9ed-117">如果错误号，2102年显示特定的邮件和暂停宏执行。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-117">If the error number is 2102, a specific message is displayed and macro execution is halted.</span></span> <span data-ttu-id="7b9ed-118">否则为显示一条描述错误消息，并将暂停该宏，以便您可以执行其他故障排除。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-118">Otherwise, a message describing the error is displayed and the macro is paused so that you can perform additional troubleshooting.</span></span> <span data-ttu-id="7b9ed-119">ErrorHandler 宏会显示一个引用 **MacroError** 对象的消息框，以显示有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-119">The ErrorHandler macro displays a message box that refers to the **MacroError** object to display information about the error.</span></span>

<span data-ttu-id="7b9ed-120">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="7b9ed-120">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
