---
title: LineGradientDir 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c603f9a5-f887-47ce-90bb-d41ec2d1a6a1
description: 确定线条渐变的方向。 渐变可以是线性、 径向、 矩形，或按路径。
ms.openlocfilehash: 6243d7a6b470db0915ba6fc462f05b72a9814f66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780581"
---
# <a name="linegradientdir-cell-gradient-properties-section"></a><span data-ttu-id="eb02c-104">LineGradientDir 单元格（“Gradient Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="eb02c-104">LineGradientDir Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="eb02c-105">确定线条渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="eb02c-105">Determines the direction of the line gradient.</span></span> <span data-ttu-id="eb02c-106">渐变可以是线性、 径向、 矩形，或按路径。</span><span class="sxs-lookup"><span data-stu-id="eb02c-106">A gradient can be linear, radial, rectangular, or follow a path.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eb02c-107">线性渐变是采用其他角度值 （如由**LineGradientDir**单元格） 的唯一渐变。</span><span class="sxs-lookup"><span data-stu-id="eb02c-107">A linear gradient is the only gradient that takes an additional angle value (as determined by **LineGradientDir** cell).</span></span> <span data-ttu-id="eb02c-108">所有其他渐变方向具有预设枚举。</span><span class="sxs-lookup"><span data-stu-id="eb02c-108">All other gradient directions have preset enumerations.</span></span> 
  
|<span data-ttu-id="eb02c-109">**值**</span><span class="sxs-lookup"><span data-stu-id="eb02c-109">**Value**</span></span>|<span data-ttu-id="eb02c-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb02c-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb02c-111">0</span><span class="sxs-lookup"><span data-stu-id="eb02c-111">0</span></span>  <br/> |<span data-ttu-id="eb02c-112">线性渐变。</span><span class="sxs-lookup"><span data-stu-id="eb02c-112">Linear gradient.</span></span> <span data-ttu-id="eb02c-113">**LineGradientAngle**单元格确定渐变的方向。</span><span class="sxs-lookup"><span data-stu-id="eb02c-113">The **LineGradientAngle** cell determines the direction of the gradient.</span></span>  <br/> |
|<span data-ttu-id="eb02c-114">1-7</span><span class="sxs-lookup"><span data-stu-id="eb02c-114">1-7</span></span>  <br/> |<span data-ttu-id="eb02c-115">径向渐变。</span><span class="sxs-lookup"><span data-stu-id="eb02c-115">Radial gradients.</span></span> <span data-ttu-id="eb02c-116">渐变扩展向外圆圈从一个中心点。</span><span class="sxs-lookup"><span data-stu-id="eb02c-116">The gradient extends outwards in a circle from a central point.</span></span>  <br/> |
|<span data-ttu-id="eb02c-117">8-12</span><span class="sxs-lookup"><span data-stu-id="eb02c-117">8-12</span></span>  <br/> |<span data-ttu-id="eb02c-118">矩形渐变。</span><span class="sxs-lookup"><span data-stu-id="eb02c-118">Rectangular gradients.</span></span> <span data-ttu-id="eb02c-119">渐变扩展为方向一行与矩形形状淡来源。</span><span class="sxs-lookup"><span data-stu-id="eb02c-119">The gradient extends as a directional line from an origin with a rectangular-shaped fade.</span></span>  <br/> |
|<span data-ttu-id="eb02c-120">13</span><span class="sxs-lookup"><span data-stu-id="eb02c-120">13</span></span>  <br/> |<span data-ttu-id="eb02c-121">路径渐变。</span><span class="sxs-lookup"><span data-stu-id="eb02c-121">Path gradient.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eb02c-122">说明</span><span class="sxs-lookup"><span data-stu-id="eb02c-122">Remarks</span></span>

<span data-ttu-id="eb02c-123">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LineGradientDir**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="eb02c-123">To get a reference to the **LineGradientDir** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eb02c-124">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="eb02c-124">Cell name:</span></span>  <br/> | <span data-ttu-id="eb02c-125">LineGradientDir</span><span class="sxs-lookup"><span data-stu-id="eb02c-125">LineGradientDir</span></span>  <br/> |
   
<span data-ttu-id="eb02c-126">若要从某个程序按索引获取对**LineGradientDir**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="eb02c-126">To get a reference to the **LineGradientDir** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eb02c-127">内容索引：</span><span class="sxs-lookup"><span data-stu-id="eb02c-127">Section index:</span></span>  <br/> |<span data-ttu-id="eb02c-128">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="eb02c-128">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="eb02c-129">行索引：</span><span class="sxs-lookup"><span data-stu-id="eb02c-129">Row index:</span></span>  <br/> |<span data-ttu-id="eb02c-130">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="eb02c-130">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="eb02c-131">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="eb02c-131">Cell index:</span></span>  <br/> |<span data-ttu-id="eb02c-132">**visLineGradientDir**</span><span class="sxs-lookup"><span data-stu-id="eb02c-132">**visLineGradientDir**</span></span> <br/> |
   

