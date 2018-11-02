---
title: If...Then...Else 宏程序块
TOCTitle: If...Then...Else macro block
ms:assetid: 0c4a4b7a-4fdb-9dbc-a94e-939a2ff1c0e5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845158(v=office.15)
ms:contentKeyID: 48543188
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c671ced7d3de2ce461af3bcf0a5d832e092bbf17
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922935"
---
# <a name="ifthenelse-macro-block"></a><span data-ttu-id="7eb22-102">If...Then...Else 宏程序块</span><span class="sxs-lookup"><span data-stu-id="7eb22-102">If...Then...Else macro block</span></span>


<span data-ttu-id="7eb22-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7eb22-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7eb22-104">可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="7eb22-104">You can use the **If** macro block to conditionally execute a group of actions, depending on the value of an expression.</span></span>

```vb
    If expression Then 
     Insert macro actions here ... 
    Else If expression 
     Insert macro actions here ... 
    Else 
     Insert macro actions here ... 
    End If
```

## <a name="setting"></a><span data-ttu-id="7eb22-105">设置</span><span class="sxs-lookup"><span data-stu-id="7eb22-105">Setting</span></span>

<span data-ttu-id="7eb22-106">**如果**和**Else If**，以下参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="7eb22-106">For both **If** and **Else If**, the following arguments are required.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7eb22-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="7eb22-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7eb22-108">说明</span><span class="sxs-lookup"><span data-stu-id="7eb22-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb22-109"><strong>Expression</strong></span><span class="sxs-lookup"><span data-stu-id="7eb22-109"><strong>Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb22-110">您要测试的条件。</span><span class="sxs-lookup"><span data-stu-id="7eb22-110">The condition that you wish to test.</span></span> <span data-ttu-id="7eb22-111">它必须是表达式的计算结果为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="7eb22-111">It must be an expression that evaluates to True or False.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="7eb22-112">注释</span><span class="sxs-lookup"><span data-stu-id="7eb22-112">Remarks</span></span>

<span data-ttu-id="7eb22-p102">当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。</span><span class="sxs-lookup"><span data-stu-id="7eb22-p102">When you select the **If** macro block, a textbox appears so that you can enter an expression that represents the condition you wish to test. In addition, a combo box appears where you can insert a macro action, below which the text "End If" automatically displays. The If and the End If bracket an area in which you can enter a group, or block, of actions. The block executes only if the expression that you enter is True.</span></span>

<span data-ttu-id="7eb22-117">表达式进行求值不同的第一个表达式为 false 时，您可以单击**添加 Else If**插入一个可选的**Else If**块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-117">To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block.</span></span> <span data-ttu-id="7eb22-118">您必须输入表达式，其计算结果 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="7eb22-118">You must enter an expression that evaluates to True or False.</span></span> <span data-ttu-id="7eb22-119">在这种情况下，阻止执行仅当表达式为 True 且的第一个表达式为 False。</span><span class="sxs-lookup"><span data-stu-id="7eb22-119">In this case, the block executes only if the expression is True and the first expression is False.</span></span>

<span data-ttu-id="7eb22-120">您可以根据需要向 If 块中添加任意多个 **Else If** 块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-120">You can add as many **Else If** blocks as you like to an If block.</span></span>

<span data-ttu-id="7eb22-121">您可以单击**添加其他人**要插入可选的**Else**块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-121">You can click **Add Else** to insert an optional **Else** block.</span></span> <span data-ttu-id="7eb22-122">在这种情况下， **Else**下方插入操作窗体的**Else**块中，仅当上述操作不会执行。</span><span class="sxs-lookup"><span data-stu-id="7eb22-122">In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not.</span></span> <span data-ttu-id="7eb22-123">您可以向**If**块添加单个**Else**块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-123">You can add a single **Else** block to an **If** block.</span></span>

<span data-ttu-id="7eb22-124">下面的代码示例中的第一个块中的宏操作执行如果的值\[状态\]大于 0。</span><span class="sxs-lookup"><span data-stu-id="7eb22-124">In the following code example, the macro actions in the first block execute if the value of \[Status\] is greater than 0.</span></span> <span data-ttu-id="7eb22-125">如果值\[状态\]不大于 0，计算**Else If**遵循的表达式。</span><span class="sxs-lookup"><span data-stu-id="7eb22-125">If the value of \[Status\] is not greater than 0, the expression that follows the **Else If** is evaluated.</span></span> <span data-ttu-id="7eb22-126">如果执行**Else If**块中的宏操作的值\[状态\]等于 0。</span><span class="sxs-lookup"><span data-stu-id="7eb22-126">The macro actions in the **Else If** block execute if the value of \[Status\] is equal to 0.</span></span> <span data-ttu-id="7eb22-127">最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。</span><span class="sxs-lookup"><span data-stu-id="7eb22-127">Finally, if neither the first block nor the second block execute, the actions in the **Else** block execute.</span></span>

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
    Else If [Status] = 0 
     Insert macro actions here ... 
    Else 
     Insert macro actions here ... 
    End If
```

<span data-ttu-id="7eb22-128">您可以嵌套 **If** 块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-128">You can nest **If** blocks.</span></span> <span data-ttu-id="7eb22-129">如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。</span><span class="sxs-lookup"><span data-stu-id="7eb22-129">You should consider nesting an **If** block within an **If** block if you want to evaluate a second expression when the first expression is True.</span></span> <span data-ttu-id="7eb22-130">在下面的代码示例中，内部**If**块仅时，会执行的值\[状态\]同时大于 0*和*大于 100。</span><span class="sxs-lookup"><span data-stu-id="7eb22-130">In the following code example, the inner **If** block only executes when the value of \[Status\] is both greater than 0 *and* greater than 100.</span></span>

```vb
    If [Status] > 0 Then 
     Insert macro actions here ... 
     If [Status] > 100 
     Insert macro actions here ... 
     EndifEnd If
```
