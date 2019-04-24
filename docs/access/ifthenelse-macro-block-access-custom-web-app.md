---
title: If .。。然后 .。。Else 宏块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 18d28dc1-c41f-47c6-b5c7-258d5f877d01
description: 可以使用 If 宏程序块，根据表达式的值有条件地执行一组操作。
ms.openlocfilehash: 6fe82e2c42f8e5d93cdc26798e7572e32d6cdc7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304261"
---
# <a name="ifthenelse-macro-block-access-custom-web-app"></a><span data-ttu-id="abc8b-103">If .。。然后 .。。Else 宏块 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="abc8b-103">If...Then...Else Macro Block (Access custom web app)</span></span>

<span data-ttu-id="abc8b-104">可以使用 **If** 宏程序块，根据表达式的值有条件地执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="abc8b-104">You can use the **If** macro block to conditionally execute a group of actions, depending on the value of an expression.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="abc8b-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="abc8b-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="abc8b-107">语法</span><span class="sxs-lookup"><span data-stu-id="abc8b-107">Syntax</span></span>

```vb
IfexpressionThen 
 Insert macro actions here ... 
Else Ifexpression  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

## <a name="setting"></a><span data-ttu-id="abc8b-108">Setting</span><span class="sxs-lookup"><span data-stu-id="abc8b-108">Setting</span></span>

<span data-ttu-id="abc8b-109">对于 **If** 和 \*\* Else If \*\* ，以下参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="abc8b-109">For both **If** and \*\* Else If \*\*, the following arguments are required.</span></span> 
  
|<span data-ttu-id="abc8b-110">**操作参数**</span><span class="sxs-lookup"><span data-stu-id="abc8b-110">**Action argument**</span></span>|<span data-ttu-id="abc8b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="abc8b-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="abc8b-112">**Expression**</span><span class="sxs-lookup"><span data-stu-id="abc8b-112">**Expression**</span></span> <br/> |<span data-ttu-id="abc8b-113">要测试的条件。</span><span class="sxs-lookup"><span data-stu-id="abc8b-113">The condition that you wish to test.</span></span> <span data-ttu-id="abc8b-114">它必须是一个计算结果为 True 或 False 的表达式。</span><span class="sxs-lookup"><span data-stu-id="abc8b-114">It must be an expression that evaluates to True or False.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="abc8b-115">注解</span><span class="sxs-lookup"><span data-stu-id="abc8b-115">Remarks</span></span>

<span data-ttu-id="abc8b-p103">当您选择 **If** 宏程序块时，会出现一个文本框，可在其中输入代表要测试的条件的表达式。此外，还会出现一个可插入宏操作的组合框，它下面会自动显示文本"End If"。If 和 End If 括起一个区域，可在其中输入操作组或块。仅当您输入的表达式为 True 时，该块才会执行。</span><span class="sxs-lookup"><span data-stu-id="abc8b-p103">When you select the **If** macro block, a textbox appears so that you can enter an expression that represents the condition you wish to test. In addition, a combo box appears where you can insert a macro action, below which the text "End If" automatically displays. The If and the End If bracket an area in which you can enter a group, or block, of actions. The block executes only if the expression that you enter is True.</span></span> 
  
<span data-ttu-id="abc8b-p104">To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block. You must enter an expression that evaluates to True or False. In this case, the block executes only if the expression is True and the first expression is False.</span><span class="sxs-lookup"><span data-stu-id="abc8b-p104">To evaluate a different expression when the first expression is false, you can click **Add Else If** to insert an optional **Else If** block. You must enter an expression that evaluates to True or False. In this case, the block executes only if the expression is True and the first expression is False.</span></span> 
  
<span data-ttu-id="abc8b-123">您可以根据需要向 If 块中添加任意多个 **Else If** 块。</span><span class="sxs-lookup"><span data-stu-id="abc8b-123">You can add as many **Else If** blocks as you like to an If block.</span></span> 
  
<span data-ttu-id="abc8b-p105">You can click **Add Else** to insert an optional **Else** block. In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not. You can add a single **Else** block to an **If** block.</span><span class="sxs-lookup"><span data-stu-id="abc8b-p105">You can click **Add Else** to insert an optional **Else** block. In this case, the actions that you insert below the **Else** form the **Else** block, which executes only when the actions above do not. You can add a single **Else** block to an **If** block.</span></span> 
  
<span data-ttu-id="abc8b-p106">在下面的代码示例中，如果 [Status] 的值大于 0，将执行第一个块中的宏操作。如果 [Status] 的值不大于 0，则计算 **Else If** 之后的表达式。如果 [Status] 的值等于 0，将执行 **Else If** 块中的宏操作。最后，如果第一个块和第二个块都不执行，则执行 **Else** 块中的操作。</span><span class="sxs-lookup"><span data-stu-id="abc8b-p106">In the following code example, the macro actions in the first block execute if the value of [Status] is greater than 0. If the value of [Status] is not greater than 0, the expression that follows the **Else If** is evaluated. The macro actions in the **Else If** block execute if the value of [Status] is equal to 0. Finally, if neither the first block nor the second block execute, the actions in the **Else** block execute.</span></span> 
  
```vb
If[Status] > 0Then 
 Insert macro actions here ... 
Else If[Status] = 0  
 Insert macro actions here ... 
Else 
 Insert macro actions here ... 
End If
```

<span data-ttu-id="abc8b-p107">您可以嵌套 **If** 块。如果要在第一个表达式为 True 时计算另一个表达式，则应考虑在 **If** 块中嵌套一个 **If** 块。在下面的代码示例中，仅当 [Status] 的值既大于 0  **又**  大于 100 时，才会执行内部 *If* 块。</span><span class="sxs-lookup"><span data-stu-id="abc8b-p107">You can nest **If** blocks. You should consider nesting an **If** block within an **If** block if you want to evaluate a second expression when the first expression is True. In the following code example, the inner **If** block only executes when the value of [Status] is both greater than 0  *and*  greater than 100.</span></span> 
  

