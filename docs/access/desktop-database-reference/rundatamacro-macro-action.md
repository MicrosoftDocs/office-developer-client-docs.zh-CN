---
title: RunDataMacro 宏操作
TOCTitle: RunDataMacro Macro Action
ms:assetid: fe4ac2f4-7851-7797-ce91-5f2dd3ba4d22
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837269(v=office.15)
ms:contentKeyID: 48548933
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm168493
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6777ae05d2ab7455016df834d17abb3406a2d710
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25889922"
---
# <a name="rundatamacro-macro-action"></a><span data-ttu-id="a75a2-102">RunDataMacro 宏操作</span><span class="sxs-lookup"><span data-stu-id="a75a2-102">RunDataMacro Macro Action</span></span>

<span data-ttu-id="a75a2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a75a2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a75a2-104">您可以使用 **RunDataMacro** 操作来运行指定的数据宏。</span><span class="sxs-lookup"><span data-stu-id="a75a2-104">You can use the **RunDataMacro** action to run a named data macro.</span></span>

## <a name="setting"></a><span data-ttu-id="a75a2-105">设置</span><span class="sxs-lookup"><span data-stu-id="a75a2-105">Setting</span></span>

<span data-ttu-id="a75a2-106">**RunDataMacro** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="a75a2-106">The **RunDataMacro** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a75a2-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="a75a2-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="a75a2-108">说明</span><span class="sxs-lookup"><span data-stu-id="a75a2-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a75a2-109">名称</span><span class="sxs-lookup"><span data-stu-id="a75a2-109">Name</span></span></p></td>
<td><p><span data-ttu-id="a75a2-110">要运行的数据宏的名称。</span><span class="sxs-lookup"><span data-stu-id="a75a2-110">The name of the data macro to run.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="a75a2-111">注释</span><span class="sxs-lookup"><span data-stu-id="a75a2-111">Remarks</span></span>

<span data-ttu-id="a75a2-112">您可以在宏、指定的数据宏和以下宏事件中使用 **RunDataMacro** 操作： **["删除后"宏事件](after-delete-macro-event.md)** 、 **["插入后"宏事件](after-insert-macro-event.md)** 和 **["更新后"宏事件](after-update-macro-event.md)** 。</span><span class="sxs-lookup"><span data-stu-id="a75a2-112">You can use the **RunDataMacro** action in macros, named data macros, and the following macro events: **[After Delete Macro Event](after-delete-macro-event.md)**, **[After Insert Macro Event](after-insert-macro-event.md)** and **[After Update Macro Event](after-update-macro-event.md)**.</span></span>

<span data-ttu-id="a75a2-113">数据宏的名称必须包括所附加 （例如， **Comments.AddComment**，而不仅仅是**AddComment**） 到的表。</span><span class="sxs-lookup"><span data-stu-id="a75a2-113">The name of the data macro must include the table to which it is attached (for example, **Comments.AddComment**, not just **AddComment**).</span></span>

<span data-ttu-id="a75a2-114">当您选择要在宏设计器中运行的数据宏时，Access 将确定该数据宏是否需要参数。</span><span class="sxs-lookup"><span data-stu-id="a75a2-114">When you select the data macro that you want to run in the macro designer, Access determines if the data macro requires parameters.</span></span> <span data-ttu-id="a75a2-115">如果数据宏需要参数，文本框将显示您可在其中键入参数。</span><span class="sxs-lookup"><span data-stu-id="a75a2-115">If the data macro requires parameters, text boxes appear where you can type in the arguments.</span></span>

<span data-ttu-id="a75a2-p102">当您运行包含 **RunDataMacro** 操作的宏并且该宏到达 **RunDataMacro** 操作时，Access 将运行调用的数据宏。当调用的数据宏完成时，Access 将返回到原始宏并运行下一操作。</span><span class="sxs-lookup"><span data-stu-id="a75a2-p102">When you run a macro that contains the **RunDataMacro** action and it reaches the **RunDataMacro** action, Access runs the called data macro. When the called data macro has finished, Access returns to the original macro and runs the next action.</span></span>

## <a name="example"></a><span data-ttu-id="a75a2-118">示例</span><span class="sxs-lookup"><span data-stu-id="a75a2-118">Example</span></span>

<span data-ttu-id="a75a2-119">下面的示例演示如何将参数传递到已命名的数据宏。</span><span class="sxs-lookup"><span data-stu-id="a75a2-119">The following example shows how to pass a parameter to a named data macro.</span></span> <span data-ttu-id="a75a2-120">使用 RunDataMacro 操作调用 dmGetCurrentServiceRequest tblServiceRequests 表的数据宏。</span><span class="sxs-lookup"><span data-stu-id="a75a2-120">The dmGetCurrentServiceRequest data macro of the tblServiceRequests table is called by using the RunDataMacro action.</span></span> <span data-ttu-id="a75a2-121">完成 dmGetCurrentServiceRequest 后，CurrentServiceRequest 变量返回数据宏将被写至 txtCurrentSR 文本框的窗体。</span><span class="sxs-lookup"><span data-stu-id="a75a2-121">When the dmGetCurrentServiceRequest is finished, the CurrentServiceRequest variable returned form the data macro is written to the txtCurrentSR text box.</span></span>

<span data-ttu-id="a75a2-122">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="a75a2-122">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
