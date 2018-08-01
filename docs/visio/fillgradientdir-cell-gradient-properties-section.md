---
title: FillGradientDir 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e8156ff1-c540-44b8-8b69-ba4d54883260
description: 确定填充渐变的方向。 渐变可以是线性、 径向、 矩形，或按路径。
ms.openlocfilehash: 9b4226892e70fcffe7a78d109bd852e6d4f93838
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780245"
---
# <a name="fillgradientdir-cell-gradient-properties-section"></a><span data-ttu-id="9400a-104">FillGradientDir 单元格（“Gradient Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="9400a-104">FillGradientDir Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="9400a-105">确定填充渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="9400a-105">Determines the direction of the fill gradient.</span></span> <span data-ttu-id="9400a-106">渐变可以是线性、 径向、 矩形，或按路径。</span><span class="sxs-lookup"><span data-stu-id="9400a-106">A gradient can be linear, radial, rectangular, or follow a path.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9400a-107">线性渐变是采用其他角度值 （如由**FillGradientDir**单元格） 的唯一渐变。</span><span class="sxs-lookup"><span data-stu-id="9400a-107">A linear gradient is the only gradient that takes an additional angle value (as determined by **FillGradientDir** cell).</span></span> <span data-ttu-id="9400a-108">所有其他渐变方向具有预设枚举。</span><span class="sxs-lookup"><span data-stu-id="9400a-108">All other gradient directions have preset enumerations.</span></span> 
  
****

|<span data-ttu-id="9400a-109">**值**</span><span class="sxs-lookup"><span data-stu-id="9400a-109">**Value**</span></span>|<span data-ttu-id="9400a-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="9400a-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9400a-111">0</span><span class="sxs-lookup"><span data-stu-id="9400a-111">0</span></span>  <br/> |<span data-ttu-id="9400a-112">线性渐变。</span><span class="sxs-lookup"><span data-stu-id="9400a-112">Linear gradient.</span></span> <span data-ttu-id="9400a-113">**FillGradientAngle**单元格确定渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="9400a-113">The **FillGradientAngle** cell determines the direction of the gradient.</span></span>  <br/> |
|<span data-ttu-id="9400a-114">1-7</span><span class="sxs-lookup"><span data-stu-id="9400a-114">1-7</span></span>  <br/> |<span data-ttu-id="9400a-115">径向渐变。</span><span class="sxs-lookup"><span data-stu-id="9400a-115">Radial gradients.</span></span> <span data-ttu-id="9400a-116">渐变扩展向外圆圈从一个中心点。</span><span class="sxs-lookup"><span data-stu-id="9400a-116">The gradient extends outwards in a circle from a central point.</span></span>  <br/> |
|<span data-ttu-id="9400a-117">8-12</span><span class="sxs-lookup"><span data-stu-id="9400a-117">8-12</span></span>  <br/> |<span data-ttu-id="9400a-118">矩形渐变。</span><span class="sxs-lookup"><span data-stu-id="9400a-118">Rectangular gradients.</span></span> <span data-ttu-id="9400a-119">渐变扩展为方向一行与矩形形状淡来源。</span><span class="sxs-lookup"><span data-stu-id="9400a-119">The gradient extends as a directional line from an origin with a rectangular-shaped fade.</span></span>  <br/> |
|<span data-ttu-id="9400a-120">13</span><span class="sxs-lookup"><span data-stu-id="9400a-120">13</span></span>  <br/> |<span data-ttu-id="9400a-121">路径渐变。</span><span class="sxs-lookup"><span data-stu-id="9400a-121">Path gradient.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9400a-122">说明</span><span class="sxs-lookup"><span data-stu-id="9400a-122">Remarks</span></span>

<span data-ttu-id="9400a-123">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**FillGradientDir**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9400a-123">To get a reference to the **FillGradientDir** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9400a-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9400a-124">Cell name:</span></span>  <br/> | <span data-ttu-id="9400a-125">FillGradientDir</span><span class="sxs-lookup"><span data-stu-id="9400a-125">FillGradientDir</span></span>  <br/> |
   
<span data-ttu-id="9400a-126">若要从某个程序按索引获取对**FillGradientDir**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="9400a-126">To get a reference to the **FillGradientDir** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9400a-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9400a-127">Section index:</span></span>  <br/> |<span data-ttu-id="9400a-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9400a-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9400a-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="9400a-129">Row index:</span></span>  <br/> |<span data-ttu-id="9400a-130">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="9400a-130">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="9400a-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9400a-131">Cell index:</span></span>  <br/> |<span data-ttu-id="9400a-132">**visFillGradientDir**</span><span class="sxs-lookup"><span data-stu-id="9400a-132">**visFillGradientDir**</span></span> <br/> |
   

