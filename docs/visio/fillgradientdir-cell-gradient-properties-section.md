---
title: 'FillGradientDir Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e8156ff1-c540-44b8-8b69-ba4d54883260
description: 确定填充渐变的方向。 渐变可以是线性、径向、矩形或遵循路径。
ms.openlocfilehash: 53aad056c7fc1674e00e142fd72a10134103b390
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406715"
---
# <a name="fillgradientdir-cell-gradient-properties-section"></a><span data-ttu-id="9312e-104">FillGradientDir Cell (Gradient Properties Section) </span><span class="sxs-lookup"><span data-stu-id="9312e-104">FillGradientDir Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="9312e-105">确定填充渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="9312e-105">Determines the direction of the fill gradient.</span></span> <span data-ttu-id="9312e-106">渐变可以是线性、径向、矩形或遵循路径。</span><span class="sxs-lookup"><span data-stu-id="9312e-106">A gradient can be linear, radial, rectangular, or follow a path.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9312e-107">线性渐变是唯一一个采用其他角度值的渐变 (**FillGradientDir** 单元格值) 。</span><span class="sxs-lookup"><span data-stu-id="9312e-107">A linear gradient is the only gradient that takes an additional angle value (as determined by **FillGradientDir** cell).</span></span> <span data-ttu-id="9312e-108">所有其他渐变方向都有预设枚举。</span><span class="sxs-lookup"><span data-stu-id="9312e-108">All other gradient directions have preset enumerations.</span></span> 
  
****

|<span data-ttu-id="9312e-109">**值**</span><span class="sxs-lookup"><span data-stu-id="9312e-109">**Value**</span></span>|<span data-ttu-id="9312e-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="9312e-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9312e-111">0</span><span class="sxs-lookup"><span data-stu-id="9312e-111">0</span></span>  <br/> |<span data-ttu-id="9312e-112">线性渐变。</span><span class="sxs-lookup"><span data-stu-id="9312e-112">Linear gradient.</span></span> <span data-ttu-id="9312e-113">**FillGradientAngle** 单元格确定渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="9312e-113">The **FillGradientAngle** cell determines the direction of the gradient.</span></span>  <br/> |
|<span data-ttu-id="9312e-114">1-7</span><span class="sxs-lookup"><span data-stu-id="9312e-114">1-7</span></span>  <br/> |<span data-ttu-id="9312e-115">径向渐变。</span><span class="sxs-lookup"><span data-stu-id="9312e-115">Radial gradients.</span></span> <span data-ttu-id="9312e-116">渐变从中心点向外延伸，在圆中向外延伸。</span><span class="sxs-lookup"><span data-stu-id="9312e-116">The gradient extends outwards in a circle from a central point.</span></span>  <br/> |
|<span data-ttu-id="9312e-117">8-12</span><span class="sxs-lookup"><span data-stu-id="9312e-117">8-12</span></span>  <br/> |<span data-ttu-id="9312e-118">矩形渐变。</span><span class="sxs-lookup"><span data-stu-id="9312e-118">Rectangular gradients.</span></span> <span data-ttu-id="9312e-119">渐变从具有矩形淡化的原点延伸为方向线。</span><span class="sxs-lookup"><span data-stu-id="9312e-119">The gradient extends as a directional line from an origin with a rectangular-shaped fade.</span></span>  <br/> |
|<span data-ttu-id="9312e-120">13</span><span class="sxs-lookup"><span data-stu-id="9312e-120">13</span></span>  <br/> |<span data-ttu-id="9312e-121">路径渐变。</span><span class="sxs-lookup"><span data-stu-id="9312e-121">Path gradient.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9312e-122">备注</span><span class="sxs-lookup"><span data-stu-id="9312e-122">Remarks</span></span>

<span data-ttu-id="9312e-123">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **FillGradientDir** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9312e-123">To get a reference to the **FillGradientDir** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9312e-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9312e-124">Cell name:</span></span>  <br/> | <span data-ttu-id="9312e-125">FillGradientDir</span><span class="sxs-lookup"><span data-stu-id="9312e-125">FillGradientDir</span></span>  <br/> |
   
<span data-ttu-id="9312e-126">若要从程序按索引获取对 **FillGradientDir** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9312e-126">To get a reference to the **FillGradientDir** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9312e-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9312e-127">Section index:</span></span>  <br/> |<span data-ttu-id="9312e-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9312e-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9312e-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="9312e-129">Row index:</span></span>  <br/> |<span data-ttu-id="9312e-130">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="9312e-130">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="9312e-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9312e-131">Cell index:</span></span>  <br/> |<span data-ttu-id="9312e-132">**visFillGradientDir**</span><span class="sxs-lookup"><span data-stu-id="9312e-132">**visFillGradientDir**</span></span> <br/> |
   

