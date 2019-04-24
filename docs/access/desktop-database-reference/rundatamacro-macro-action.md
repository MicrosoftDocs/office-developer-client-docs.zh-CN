---
title: RunDataMacro 宏操作
TOCTitle: RunDataMacro macro action
ms:assetid: fe4ac2f4-7851-7797-ce91-5f2dd3ba4d22
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837269(v=office.15)
ms:contentKeyID: 48548933
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm168493
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 32945f0822682a9432d75ed1ac59117dde3cc0e9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306809"
---
# <a name="rundatamacro-macro-action"></a><span data-ttu-id="f7ea0-102">RunDataMacro 宏操作</span><span class="sxs-lookup"><span data-stu-id="f7ea0-102">RunDataMacro macro action</span></span>

<span data-ttu-id="f7ea0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f7ea0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f7ea0-104">您可以使用 **RunDataMacro** 操作来运行指定的数据宏。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-104">You can use the **RunDataMacro** action to run a named data macro.</span></span>

## <a name="setting"></a><span data-ttu-id="f7ea0-105">Setting</span><span class="sxs-lookup"><span data-stu-id="f7ea0-105">Setting</span></span>

<span data-ttu-id="f7ea0-106">**RunDataMacro** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-106">The **RunDataMacro** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f7ea0-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="f7ea0-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="f7ea0-108">说明</span><span class="sxs-lookup"><span data-stu-id="f7ea0-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7ea0-109">Name</span><span class="sxs-lookup"><span data-stu-id="f7ea0-109">Name</span></span></p></td>
<td><p><span data-ttu-id="f7ea0-110">要运行的数据宏的名称。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-110">The name of the data macro to run.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="f7ea0-111">注解</span><span class="sxs-lookup"><span data-stu-id="f7ea0-111">Remarks</span></span>

<span data-ttu-id="f7ea0-112">您可以在宏、名为 data 宏和以下宏事件中使用**RunDataMacro**操作: **[Delete 宏定义](after-delete-macro-event.md)** after 宏事件后**[](after-insert-macro-event.md)** 和**[更新宏事件](after-update-macro-event.md)** 之后。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-112">You can use the **RunDataMacro** action in macros, named data macros, and the following macro events: **[After Delete macro event](after-delete-macro-event.md)**, **[After Insert macro event](after-insert-macro-event.md)** and **[After Update macro event](after-update-macro-event.md)**.</span></span>

<span data-ttu-id="f7ea0-113">数据宏的名称必须包含它所附加到的表 (例如**AddComment**, 而不仅仅是**AddComment**)。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-113">The name of the data macro must include the table to which it is attached (for example, **Comments.AddComment**, not just **AddComment**).</span></span>

<span data-ttu-id="f7ea0-114">当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-114">When you select the data macro that you want to run in the macro designer, Access determines if the data macro requires parameters.</span></span> <span data-ttu-id="f7ea0-115">如果数据宏需要参数, 则将显示文本框, 您可以在其中键入参数。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-115">If the data macro requires parameters, text boxes appear where you can type in the arguments.</span></span>

<span data-ttu-id="f7ea0-p102">当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-p102">When you run a macro that contains the **RunDataMacro** action and it reaches the **RunDataMacro** action, Access runs the called data macro. When the called data macro has finished, Access returns to the original macro and runs the next action.</span></span>

## <a name="example"></a><span data-ttu-id="f7ea0-118">示例</span><span class="sxs-lookup"><span data-stu-id="f7ea0-118">Example</span></span>

<span data-ttu-id="f7ea0-119">下面的示例演示如何将参数传递给已命名的数据宏。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-119">The following example shows how to pass a parameter to a named data macro.</span></span> <span data-ttu-id="f7ea0-120">tblServiceRequests 表的 dmGetCurrentServiceRequest 数据宏是通过使用 RunDataMacro 操作调用的。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-120">The dmGetCurrentServiceRequest data macro of the tblServiceRequests table is called by using the RunDataMacro action.</span></span> <span data-ttu-id="f7ea0-121">dmGetCurrentServiceRequest 完成后, 返回的 CurrentServiceRequest 变量的数据宏将写入到 txtCurrentSR 文本框。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-121">When the dmGetCurrentServiceRequest is finished, the CurrentServiceRequest variable returned form the data macro is written to the txtCurrentSR text box.</span></span>

<span data-ttu-id="f7ea0-122">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="f7ea0-122">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    RunDataMacro
        Macro Name tblServiceRequests.dmGetCurrentServiceRequest
    
    Parameters
        prmAssignedTo =[ID]
    
    SetProperty
        Control Name txtCurrentSR
        Property Value
        Value =[ReturnVars]![CurrentServiceRequest]
```
