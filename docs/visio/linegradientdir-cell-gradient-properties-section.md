---
title: LineGradientDir 单元格 ("渐变属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c603f9a5-f887-47ce-90bb-d41ec2d1a6a1
description: 确定线条渐变的方向。 渐变可以是线形、放射状、矩形或跟随路径。
ms.openlocfilehash: 05dcc6904a4e67d97c632dba44635936b1c14049
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350958"
---
# <a name="linegradientdir-cell-gradient-properties-section"></a><span data-ttu-id="1b6b4-104">LineGradientDir 单元格 ("渐变属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="1b6b4-104">LineGradientDir Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="1b6b4-105">确定线条渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-105">Determines the direction of the line gradient.</span></span> <span data-ttu-id="1b6b4-106">渐变可以是线形、放射状、矩形或跟随路径。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-106">A gradient can be linear, radial, rectangular, or follow a path.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1b6b4-107">线性渐变是唯一采用其他角度值 (由**LineGradientDir**单元格确定) 的渐变。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-107">A linear gradient is the only gradient that takes an additional angle value (as determined by **LineGradientDir** cell).</span></span> <span data-ttu-id="1b6b4-108">其他所有渐变方向都具有预设枚举。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-108">All other gradient directions have preset enumerations.</span></span> 
  
|<span data-ttu-id="1b6b4-109">**Value**</span><span class="sxs-lookup"><span data-stu-id="1b6b4-109">**Value**</span></span>|<span data-ttu-id="1b6b4-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="1b6b4-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b6b4-111">0</span><span class="sxs-lookup"><span data-stu-id="1b6b4-111">0</span></span>  <br/> |<span data-ttu-id="1b6b4-112">线性渐变。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-112">Linear gradient.</span></span> <span data-ttu-id="1b6b4-113">**LineGradientAngle**单元格决定渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-113">The **LineGradientAngle** cell determines the direction of the gradient.</span></span>  <br/> |
|<span data-ttu-id="1b6b4-114">1-7</span><span class="sxs-lookup"><span data-stu-id="1b6b4-114">1-7</span></span>  <br/> |<span data-ttu-id="1b6b4-115">放射状渐变。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-115">Radial gradients.</span></span> <span data-ttu-id="1b6b4-116">渐变从一个中心点向外扩展到一个圆。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-116">The gradient extends outwards in a circle from a central point.</span></span>  <br/> |
|<span data-ttu-id="1b6b4-117">8-12</span><span class="sxs-lookup"><span data-stu-id="1b6b4-117">8-12</span></span>  <br/> |<span data-ttu-id="1b6b4-118">矩形渐变。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-118">Rectangular gradients.</span></span> <span data-ttu-id="1b6b4-119">渐变将作为方向线从具有矩形形状淡入淡出的原点扩展。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-119">The gradient extends as a directional line from an origin with a rectangular-shaped fade.</span></span>  <br/> |
|<span data-ttu-id="1b6b4-120">13</span><span class="sxs-lookup"><span data-stu-id="1b6b4-120">13</span></span>  <br/> |<span data-ttu-id="1b6b4-121">路径渐变。</span><span class="sxs-lookup"><span data-stu-id="1b6b4-121">Path gradient.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1b6b4-122">注解</span><span class="sxs-lookup"><span data-stu-id="1b6b4-122">Remarks</span></span>

<span data-ttu-id="1b6b4-123">若要从另一个公式按名称获取对**LineGradientDir**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="1b6b4-123">To get a reference to the **LineGradientDir** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1b6b4-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1b6b4-124">Cell name:</span></span>  <br/> | <span data-ttu-id="1b6b4-125">LineGradientDir</span><span class="sxs-lookup"><span data-stu-id="1b6b4-125">LineGradientDir</span></span>  <br/> |
   
<span data-ttu-id="1b6b4-126">若要从某个程序按索引获取对**LineGradientDir**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="1b6b4-126">To get a reference to the **LineGradientDir** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1b6b4-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1b6b4-127">Section index:</span></span>  <br/> |<span data-ttu-id="1b6b4-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1b6b4-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="1b6b4-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="1b6b4-129">Row index:</span></span>  <br/> |<span data-ttu-id="1b6b4-130">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="1b6b4-130">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="1b6b4-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1b6b4-131">Cell index:</span></span>  <br/> |<span data-ttu-id="1b6b4-132">**visLineGradientDir**</span><span class="sxs-lookup"><span data-stu-id="1b6b4-132">**visLineGradientDir**</span></span> <br/> |
   

