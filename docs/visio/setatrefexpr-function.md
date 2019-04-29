---
title: SETATREFEXPR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027317
localization_priority: Normal
ms.assetid: c1bd7819-b53b-bff1-69c1-6d78e8fb278b
description: 存储通过用户界面 (UI) 或自动化中的操作设置的值。
ms.openlocfilehash: 5ca7b59d0ced9c3da346c416826ac89e6b4001da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439049"
---
# <a name="setatrefexpr-function"></a><span data-ttu-id="73597-103">SETATREFEXPR 函数</span><span class="sxs-lookup"><span data-stu-id="73597-103">SETATREFEXPR Function</span></span>

<span data-ttu-id="73597-104">存储通过用户界面 (UI) 或自动化中的操作设置的值。</span><span class="sxs-lookup"><span data-stu-id="73597-104">Stores a value that is set through an action in the user interface (UI) or Automation.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="73597-105">语法</span><span class="sxs-lookup"><span data-stu-id="73597-105">Syntax</span></span>

<span data-ttu-id="73597-106">SETATREFEXPR ([\* \* *expr_opt* \* \*])</span><span class="sxs-lookup"><span data-stu-id="73597-106">SETATREFEXPR ([ \*\* *expr_opt* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="73597-107">参数</span><span class="sxs-lookup"><span data-stu-id="73597-107">Parameters</span></span>

|<span data-ttu-id="73597-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="73597-108">**Name**</span></span>|<span data-ttu-id="73597-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="73597-109">**Required/Optional**</span></span>|<span data-ttu-id="73597-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="73597-110">**Data Type**</span></span>|<span data-ttu-id="73597-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="73597-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="73597-112">_expr_opt_</span><span class="sxs-lookup"><span data-stu-id="73597-112">_expr_opt_</span></span> <br/> |<span data-ttu-id="73597-113">可选</span><span class="sxs-lookup"><span data-stu-id="73597-113">Optional</span></span>  <br/> |<span data-ttu-id="73597-114">**相同**</span><span class="sxs-lookup"><span data-stu-id="73597-114">**Varies**</span></span> <br/> |<span data-ttu-id="73597-115">由赋给 SETATREF 函数中引用单元格的值或表达式所替换的表达式。</span><span class="sxs-lookup"><span data-stu-id="73597-115">An expression that is replaced by the value or expression being assigned to the referenced cell in the SETATREF function.</span></span> <span data-ttu-id="73597-116">如果未指明, 其初始值为 0 (零)。</span><span class="sxs-lookup"><span data-stu-id="73597-116">If not indicated, its initial value is 0 (zero).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="73597-117">说明</span><span class="sxs-lookup"><span data-stu-id="73597-117">Remarks</span></span>

<span data-ttu-id="73597-118">还可以通过其他单元格（该单元格引用包含 SETATREFEXPR 表达式的单元格）中的 SETATREF 函数设置 SETATREFEXPR 表达式的值。</span><span class="sxs-lookup"><span data-stu-id="73597-118">The value of a SETATREFEXPR expression can also be set from a SETATREF function in another cell that references the cell containing the SETATREFEXPR expression.</span></span> 
  
<span data-ttu-id="73597-119">您并不局限于将 SETATREFEXPR 函数用作 SETATREF 函数的参数。</span><span class="sxs-lookup"><span data-stu-id="73597-119">You are not limited to using the SETATREFEXPR function as a parameter to the SETATREF function.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="73597-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="73597-120">Example 1</span></span>

<span data-ttu-id="73597-121">下面的示例使用 SETATREFEXPR 函数来确保形状的宽度与其文本的宽度相同。</span><span class="sxs-lookup"><span data-stu-id="73597-121">The following example uses the SETATREFEXPR function to ensure that a shape is as wide as its text.</span></span>
  
<span data-ttu-id="73597-122">Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())</span><span class="sxs-lookup"><span data-stu-id="73597-122">Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())</span></span>
  
## <a name="example-2"></a><span data-ttu-id="73597-123">示例 2</span><span class="sxs-lookup"><span data-stu-id="73597-123">Example 2</span></span>

<span data-ttu-id="73597-p102">下面的示例说明如何使用 SETATREFEXPR 函数使形状与自定义网格对齐。SETATREFEXPR 公式放置于 PinX 和 PinY 单元格中，使形状的旋转中心点与 User.GridX 和 User.GridY 中定义的网格对齐。</span><span class="sxs-lookup"><span data-stu-id="73597-p102">The following example shows how you can use the SETATREFEXPR function to cause your shapes to snap to a custom grid. The SETATREFEXPR formulas are placed in the PinX and PinY cells, causing the shape's pin to snap to the grid defined in User.GridX and User.GridY.</span></span> 
  
<span data-ttu-id="73597-126">User.GridX =2 in</span><span class="sxs-lookup"><span data-stu-id="73597-126">User.GridX =2 in</span></span>
  
<span data-ttu-id="73597-127">User.GridY =2 in</span><span class="sxs-lookup"><span data-stu-id="73597-127">User.GridY =2 in</span></span>
  
<span data-ttu-id="73597-128">PinX = INT (SETATREFEXPR ()/User.GridX + .5)\*用户 GridX</span><span class="sxs-lookup"><span data-stu-id="73597-128">PinX =INT(SETATREFEXPR()/User.GridX + .5)\*User.GridX</span></span>
  
<span data-ttu-id="73597-129">PinY = INT (SETATREFEXPR ()/User.GridY + .5)\*User. GridY</span><span class="sxs-lookup"><span data-stu-id="73597-129">PinY =INT(SETATREFEXPR()/User.GridY + .5)\*User.GridY</span></span>
  
## <a name="example-3"></a><span data-ttu-id="73597-130">示例 3</span><span class="sxs-lookup"><span data-stu-id="73597-130">Example 3</span></span>

<span data-ttu-id="73597-131">有关 SETATREFEXPR 函数与 SETATREF 函数结合使用的示例，请参阅 [SETATREF](setatref-function.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="73597-131">For an example using the SETATREFEXPR function with the SETATREF function, see the [SETATREF](setatref-function.md) function.</span></span> 
  

