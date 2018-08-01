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
description: 存储在用户界面 (UI) 或自动化中通过某项操作设置一个值。
ms.openlocfilehash: c664717afcc2b81e55495fd1957a86ef1b021d0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781257"
---
# <a name="setatrefexpr-function"></a><span data-ttu-id="a9398-103">SETATREFEXPR 函数</span><span class="sxs-lookup"><span data-stu-id="a9398-103">SETATREFEXPR Function</span></span>

<span data-ttu-id="a9398-104">存储在用户界面 (UI) 或自动化中通过某项操作设置一个值。</span><span class="sxs-lookup"><span data-stu-id="a9398-104">Stores a value that is set through an action in the user interface (UI) or Automation.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a9398-105">语法</span><span class="sxs-lookup"><span data-stu-id="a9398-105">Syntax</span></span>

<span data-ttu-id="a9398-106">SETATREFEXPR ([* * *expr_opt* * *])</span><span class="sxs-lookup"><span data-stu-id="a9398-106">SETATREFEXPR ([ ** *expr_opt* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a9398-107">参数</span><span class="sxs-lookup"><span data-stu-id="a9398-107">Parameters</span></span>

|<span data-ttu-id="a9398-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a9398-108">**Name**</span></span>|<span data-ttu-id="a9398-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a9398-109">**Required/Optional**</span></span>|<span data-ttu-id="a9398-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a9398-110">**Data Type**</span></span>|<span data-ttu-id="a9398-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9398-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a9398-112">_expr_opt_</span><span class="sxs-lookup"><span data-stu-id="a9398-112">_expr_opt_</span></span> <br/> |<span data-ttu-id="a9398-113">可选</span><span class="sxs-lookup"><span data-stu-id="a9398-113">Optional</span></span>  <br/> |<span data-ttu-id="a9398-114">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="a9398-114">**Varies**</span></span> <br/> |<span data-ttu-id="a9398-115">表达式，用于替换为其分配到 SETATREF 函数中引用的单元格的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="a9398-115">An expression that is replaced by the value or expression being assigned to the referenced cell in the SETATREF function.</span></span> <span data-ttu-id="a9398-116">如果未指示，其初始值为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="a9398-116">If not indicated, its initial value is 0 (zero).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a9398-117">注解</span><span class="sxs-lookup"><span data-stu-id="a9398-117">Remarks</span></span>

<span data-ttu-id="a9398-118">还可以通过其他单元格（该单元格引用包含 SETATREFEXPR 表达式的单元格）中的 SETATREF 函数设置 SETATREFEXPR 表达式的值。</span><span class="sxs-lookup"><span data-stu-id="a9398-118">The value of a SETATREFEXPR expression can also be set from a SETATREF function in another cell that references the cell containing the SETATREFEXPR expression.</span></span> 
  
<span data-ttu-id="a9398-119">您不限于使用 SETATREFEXPR 函数作为 SETATREF 函数的参数。</span><span class="sxs-lookup"><span data-stu-id="a9398-119">You are not limited to using the SETATREFEXPR function as a parameter to the SETATREF function.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="a9398-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="a9398-120">Example 1</span></span>

<span data-ttu-id="a9398-121">下面的示例使用 SETATREFEXPR 函数来确保形状的宽度与其文本的宽度相同。</span><span class="sxs-lookup"><span data-stu-id="a9398-121">The following example uses the SETATREFEXPR function to ensure that a shape is as wide as its text.</span></span>
  
<span data-ttu-id="a9398-122">Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())</span><span class="sxs-lookup"><span data-stu-id="a9398-122">Width =MAX(TEXTWIDTH(TheText),SETATREFEXPR())</span></span>
  
## <a name="example-2"></a><span data-ttu-id="a9398-123">示例 2</span><span class="sxs-lookup"><span data-stu-id="a9398-123">Example 2</span></span>

<span data-ttu-id="a9398-p102">下面的示例说明如何使用 SETATREFEXPR 函数使形状与自定义网格对齐。SETATREFEXPR 公式放置于 PinX 和 PinY 单元格中，使形状的旋转中心点与 User.GridX 和 User.GridY 中定义的网格对齐。</span><span class="sxs-lookup"><span data-stu-id="a9398-p102">The following example shows how you can use the SETATREFEXPR function to cause your shapes to snap to a custom grid. The SETATREFEXPR formulas are placed in the PinX and PinY cells, causing the shape's pin to snap to the grid defined in User.GridX and User.GridY.</span></span> 
  
<span data-ttu-id="a9398-126">User.GridX =2 in</span><span class="sxs-lookup"><span data-stu-id="a9398-126">User.GridX =2 in</span></span>
  
<span data-ttu-id="a9398-127">User.GridY =2 in</span><span class="sxs-lookup"><span data-stu-id="a9398-127">User.GridY =2 in</span></span>
  
<span data-ttu-id="a9398-128">PinX = INT (SETATREFEXPR （) /User.GridX +.5)\*User.GridX</span><span class="sxs-lookup"><span data-stu-id="a9398-128">PinX =INT(SETATREFEXPR()/User.GridX + .5)\*User.GridX</span></span>
  
<span data-ttu-id="a9398-129">PinY = INT (SETATREFEXPR （) /User.GridY +.5)\*User.GridY</span><span class="sxs-lookup"><span data-stu-id="a9398-129">PinY =INT(SETATREFEXPR()/User.GridY + .5)\*User.GridY</span></span>
  
## <a name="example-3"></a><span data-ttu-id="a9398-130">示例 3</span><span class="sxs-lookup"><span data-stu-id="a9398-130">Example 3</span></span>

<span data-ttu-id="a9398-131">有关 SETATREFEXPR 函数与 SETATREF 函数结合使用的示例，请参阅 [SETATREF](setatref-function.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="a9398-131">For an example using the SETATREFEXPR function with the SETATREF function, see the [SETATREF](setatref-function.md) function.</span></span> 
  

