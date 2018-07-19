---
title: 如果...然后...其他宏程序块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 18d28dc1-c41f-47c6-b5c7-258d5f877d01
description: 可以使用 If 宏程序块，根据表达式的值有条件地执行一组操作。
ms.openlocfilehash: 8ac78ff0eaf22c1d821e306654ebfa8fac4ed34a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773457"
---
# <a name="ifthenelse-macro-block-access-custom-web-app"></a><span data-ttu-id="aa7a4-103">如果...然后...其他宏程序块 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="aa7a4-103">If...Then...Else Macro Block (Access custom web app)</span></span>

<span data-ttu-id="aa7a4-104">可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-104">You can use the **If** macro block to conditionally execute a group of actions, depending on the value of an expression.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="aa7a4-p101"> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="aa7a4-107">语法</span><span class="sxs-lookup"><span data-stu-id="aa7a4-107">Syntax</span></span>

```vb
IfexpressionThen 
 Insert macro actions here ... 
Else Ifexpression  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

## <a name="setting"></a><span data-ttu-id="aa7a4-108">设置</span><span class="sxs-lookup"><span data-stu-id="aa7a4-108">Setting</span></span>

<span data-ttu-id="aa7a4-109">对于 **If** 和 ** Else If ** ，以下参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-109">For both **If** and ** Else If **, the following arguments are required.</span></span> 
  
|<span data-ttu-id="aa7a4-110">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="aa7a4-110">**Action argument**</span></span>|<span data-ttu-id="aa7a4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa7a4-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa7a4-112">**Expression**</span><span class="sxs-lookup"><span data-stu-id="aa7a4-112">**Expression**</span></span> <br/> |<span data-ttu-id="aa7a4-113">您要测试的条件。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-113">The condition that you wish to test.</span></span> <span data-ttu-id="aa7a4-114">它必须是表达式的计算结果为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-114">It must be an expression that evaluates to True or False.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aa7a4-115">注释</span><span class="sxs-lookup"><span data-stu-id="aa7a4-115">Remarks</span></span>

<span data-ttu-id="aa7a4-p103">当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-p103">When you select the **If** macro block, a textbox appears so that you can enter an expression that represents the condition you wish to test. In addition, a combo box appears where you can insert a macro action, below which the text "End If" automatically displays. The If and the End If bracket an area in which you can enter a group, or block, of actions. The block executes only if the expression that you enter is True.</span></span> 
  
<span data-ttu-id="aa7a4-120">表达式进行求值不同的第一个表达式为 false 时，您可以单击**添加 Else If**插入一个可选的**Else If**块。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-120">To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block.</span></span> <span data-ttu-id="aa7a4-121">您必须输入表达式，其计算结果 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-121">You must enter an expression that evaluates to True or False.</span></span> <span data-ttu-id="aa7a4-122">在这种情况下，阻止执行仅当表达式为 True 且的第一个表达式为 False。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-122">In this case, the block executes only if the expression is True and the first expression is False.</span></span> 
  
<span data-ttu-id="aa7a4-123">您可以根据需要向 If 块中添加任意多个 **Else If** 块。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-123">You can add as many **Else If** blocks as you like to an If block.</span></span> 
  
<span data-ttu-id="aa7a4-124">您可以单击**添加其他人**要插入可选的**Else**块。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-124">You can click **Add Else** to insert an optional **Else** block.</span></span> <span data-ttu-id="aa7a4-125">在这种情况下， **Else**下方插入操作窗体的**Else**块中，仅当上述操作不会执行。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-125">In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not.</span></span> <span data-ttu-id="aa7a4-126">您可以向**If**块添加单个**Else**块。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-126">You can add a single **Else** block to an **If** block.</span></span> 
  
<span data-ttu-id="aa7a4-p106">在下面的代码示例中，如果 [Status] 的值大于 0，将执行第一个块中的宏操作。如果 [Status] 的值不大于 0，则计算 **Else If** 之后的表达式。如果 [Status] 的值等于 0，将执行 **Else If** 块中的宏操作。最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-p106">In the following code example, the macro actions in the first block execute if the value of [Status] is greater than 0. If the value of [Status] is not greater than 0, the expression that follows the **Else If** is evaluated. The macro actions in the **Else If** block execute if the value of [Status] is equal to 0. Finally, if neither the first block nor the second block execute, the actions in the **Else** block execute.</span></span> 
  
```vb
If[Status] > 0Then 
 Insert macro actions here ... 
Else If[Status] = 0  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

<span data-ttu-id="aa7a4-p107">您可以嵌套 **If** 块。如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。在下面的代码示例中，仅当 [Status] 的值既大于 0  **又**  大于 100 时，才会执行内部 *If* 块。</span><span class="sxs-lookup"><span data-stu-id="aa7a4-p107">You can nest **If** blocks. You should consider nesting an **If** block within an **If** block if you want to evaluate a second expression when the first expression is True. In the following code example, the inner **If** block only executes when the value of [Status] is both greater than 0  *and*  greater than 100.</span></span> 
  

