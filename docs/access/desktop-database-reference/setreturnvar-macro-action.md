---
title: SetReturnVar Macro Action
TOCTitle: SetReturnVar Macro Action
ms:assetid: 53719857-00bb-4f33-b5d2-93aff92d736e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193989(v=office.15)
ms:contentKeyID: 48544870
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fa4380904888194bf1d954ebf5619cab7d155047
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466692"
---
# <a name="setreturnvar-macro-action"></a><span data-ttu-id="788a1-102">SetReturnVar Macro Action</span><span class="sxs-lookup"><span data-stu-id="788a1-102">SetReturnVar Macro Action</span></span>

<span data-ttu-id="788a1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="788a1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="788a1-104">**SetReturnVar**操作创建返回变量，并将其设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="788a1-104">The **SetReturnVar** action creates a return variable and sets it to a specific value.</span></span>

> [!NOTE]
> <span data-ttu-id="788a1-105">**SetReturnVar**操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="788a1-105">The **SetReturnVar** action is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="788a1-106">设置</span><span class="sxs-lookup"><span data-stu-id="788a1-106">Setting</span></span>

<span data-ttu-id="788a1-107">**SetReturnVar**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="788a1-107">The **SetReturnVar** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="788a1-108">参数</span><span class="sxs-lookup"><span data-stu-id="788a1-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="788a1-109">是否必需</span><span class="sxs-lookup"><span data-stu-id="788a1-109">Required</span></span></p></th>
<th><p><span data-ttu-id="788a1-110">说明</span><span class="sxs-lookup"><span data-stu-id="788a1-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="788a1-111">名称</span><span class="sxs-lookup"><span data-stu-id="788a1-111">Name</span></span></p></td>
<td><p><span data-ttu-id="788a1-112">是</span><span class="sxs-lookup"><span data-stu-id="788a1-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="788a1-113">一个用于指定变量名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="788a1-113">A string that specifies the name of the variable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="788a1-114">表达式</span><span class="sxs-lookup"><span data-stu-id="788a1-114">Expression</span></span></p></td>
<td><p><span data-ttu-id="788a1-115">是</span><span class="sxs-lookup"><span data-stu-id="788a1-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="788a1-116">一个表达式，用于设置为临时变量的值。</span><span class="sxs-lookup"><span data-stu-id="788a1-116">An expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="788a1-117">不在表达式前面放等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="788a1-117">Do not precede the expression with the equal sign (=).</span></span> <span data-ttu-id="788a1-118">您可以单击<strong>生成</strong>按钮以使用<strong>表达式生成器</strong>设置此参数。</span><span class="sxs-lookup"><span data-stu-id="788a1-118">You can click the <strong>Build</strong> button to use the <strong>Expression Builder</strong> to set this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="788a1-119">说明</span><span class="sxs-lookup"><span data-stu-id="788a1-119">Remarks</span></span>

<span data-ttu-id="788a1-120">**SetReturnVar**操作用于创建**ReturnVar**，这是可供使用**RunDataMacro**操作调用的数据宏的宏的变量。</span><span class="sxs-lookup"><span data-stu-id="788a1-120">The **SetReturnVar** action is used to create a **ReturnVar**, which is variable that can be used by macros that call a data macro by using the **RunDataMacro** action.</span></span>

<span data-ttu-id="788a1-121">**SetReturnVar**操作创建**ReturnVar**后，调用宏可以使用它在表达式中。</span><span class="sxs-lookup"><span data-stu-id="788a1-121">Once a **ReturnVar** is created by the **SetReturnVar** action, the calling macro can use it in an expression.</span></span> <span data-ttu-id="788a1-122">例如，如果您创建名为**UpdateSuccess** **ReturnVar** ，您可以使用该变量使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="788a1-122">For example, if you created a **ReturnVar** named **UpdateSuccess**, you could use the variable by using the following syntax:</span></span>

```vb
    =[ReturnVars]![UpdateSuccess]
```

<span data-ttu-id="788a1-123">**SetReturnVar**操作可仅在命名的数据宏。</span><span class="sxs-lookup"><span data-stu-id="788a1-123">The **SetReturnVar** action can be used only in named data macros.</span></span> <span data-ttu-id="788a1-124">不适用于数据宏附加到的数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="788a1-124">It is not available in data macros that are attached to a data macro event.</span></span>

## <a name="example"></a><span data-ttu-id="788a1-125">示例</span><span class="sxs-lookup"><span data-stu-id="788a1-125">Example</span></span>

<span data-ttu-id="788a1-126">下面的示例演示如何使用 SetReturnVar 操作从已命名的数据宏返回值。</span><span class="sxs-lookup"><span data-stu-id="788a1-126">The following example shows how to use the SetReturnVar action to return a value from a named data macro.</span></span> <span data-ttu-id="788a1-127">名为**CurrentServiceRequest** ReturnVar 调用已命名的数据宏的 Applications (VBA) 子例程返回到宏或 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="788a1-127">A ReturnVar named **CurrentServiceRequest** is returned to the macro or Visual Basic for Applications (VBA) subroutine that called the named data macro.</span></span>

<span data-ttu-id="788a1-128">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="788a1-128">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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