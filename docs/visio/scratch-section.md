---
title: “Scratch”内容
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm2125
localization_priority: Normal
ms.assetid: 144dd06f-7225-57db-fd19-a58d6bccf0e1
description: 用于输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: a7d2c6762e96fc19986521c2ba164666b925c928
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411601"
---
# <a name="scratch-section"></a><span data-ttu-id="96f22-103">“Scratch”内容</span><span class="sxs-lookup"><span data-stu-id="96f22-103">Scratch Section</span></span>

<span data-ttu-id="96f22-104">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="96f22-104">A work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="96f22-105">说明</span><span class="sxs-lookup"><span data-stu-id="96f22-105">Remarks</span></span>

<span data-ttu-id="96f22-p101">可以使用 **“插入内容”** 对话框添加此内容。方法是：在 ShapeSheet 窗口中单击右键，然后单击 **“插入内容”**。</span><span class="sxs-lookup"><span data-stu-id="96f22-p101">You can add this section by using the **Insert Section** dialog box. Right-click in the ShapeSheet window, and then click **Insert Section**.</span></span>
  
<span data-ttu-id="96f22-108">"**草稿**" 部分通常用于隔离重复的复杂计算。</span><span class="sxs-lookup"><span data-stu-id="96f22-108">The **Scratch** section is typically used to isolate repeated complex calculations.</span></span> <span data-ttu-id="96f22-109">如果您的解决方案具有明确定义的用途, 则在使用 "**用户定义的单元**格" 部分中的单元格以进行清晰度是 wiser 的, 因为用户单元格可以命名。</span><span class="sxs-lookup"><span data-stu-id="96f22-109">If your solution has a well-defined purpose, it's wiser to use a cell in the **User-Defined Cells** section for clarity because User cells can be named.</span></span> 
  
<span data-ttu-id="96f22-110">"**草稿**" 部分中的单元格以两种不同的方式使用单位。</span><span class="sxs-lookup"><span data-stu-id="96f22-110">Cells in the **Scratch** section use units in two different ways.</span></span> <span data-ttu-id="96f22-111">X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。</span><span class="sxs-lookup"><span data-stu-id="96f22-111">X and Y cells use drawing units; A through D cells don't use units.</span></span> <span data-ttu-id="96f22-112">(在 C 程序员的术语中, X 和 Y 单元格是 "类型化的", 单元格 A 到 D 是 "void"。)^ **x**和**擦掉 y**单元格通常用于派生*X*和*y*坐标, 如**PinX**和**PinY**, 或在 " **Geometry** " 内容单元格中找到的 x 和 y 单元格。</span><span class="sxs-lookup"><span data-stu-id="96f22-112">(In C programmers' jargon, X and Y cells are "typed," and cells A through D are "void.") The **Scratch X** and **Scratch Y** cells are often used for deriving  *x-*  and  *y-*  coordinates, such as **PinX** and **PinY**, or the X and Y cells found in a **Geometry** section cell.</span></span> <span data-ttu-id="96f22-113">暂存单元格 A 到 D 可以显示任何指定的单位。</span><span class="sxs-lookup"><span data-stu-id="96f22-113">Scratch cells A through D can display whatever units you specify.</span></span> 
  
<span data-ttu-id="96f22-114">这些单元格进一步的区别是，它们存储点值的方式不同。</span><span class="sxs-lookup"><span data-stu-id="96f22-114">A further difference is the way these cells store point values.</span></span> <span data-ttu-id="96f22-115">Visio 中的一个点是 ( *x, y*) 坐标的单个数据包。</span><span class="sxs-lookup"><span data-stu-id="96f22-115">A point in Visio is a single data package for an ( *x,y*) coordinate.</span></span> <span data-ttu-id="96f22-116">当公式返回点值时，将根据公式所在的 ShapeSheet 单元格，以三种方式之一解释该值。</span><span class="sxs-lookup"><span data-stu-id="96f22-116">When a formula returns a point value, that value is interpreted in one of three ways, depending on the ShapeSheet cell the formula is in.</span></span> <span data-ttu-id="96f22-117">与*x*坐标相关的单元格 (例如, " **PinX**" 或 " **Geometry** " 内容的 x 列中的单元格) 只提取点值的*x*坐标部分。</span><span class="sxs-lookup"><span data-stu-id="96f22-117">Cells that relate to  *x*  -coordinates (for example, **PinX**, or cells in the X column of a **Geometry** section) extract just the  *x*  -coordinate part of a point value.</span></span> <span data-ttu-id="96f22-118">与*y*坐标相关的单元格只提取点值的*y*坐标部分。</span><span class="sxs-lookup"><span data-stu-id="96f22-118">Cells that relate to  *y*  -coordinates extract just the  *y*  -coordinate part of a point value.</span></span> 
  
<span data-ttu-id="96f22-119">例如, Visio 以这三种`PNT(3,4)`方式提取公式。</span><span class="sxs-lookup"><span data-stu-id="96f22-119">For example, Visio extracts the formula  `PNT(3,4)` in these three ways.</span></span> 
  
|<span data-ttu-id="96f22-120">**单元格**</span><span class="sxs-lookup"><span data-stu-id="96f22-120">**Cell**</span></span>|<span data-ttu-id="96f22-121">**输入值**</span><span class="sxs-lookup"><span data-stu-id="96f22-121">**If you enter**</span></span>|<span data-ttu-id="96f22-122">**Visio 处理方式**</span><span class="sxs-lookup"><span data-stu-id="96f22-122">**Visio treats it as**</span></span>|<span data-ttu-id="96f22-123">**结果**</span><span class="sxs-lookup"><span data-stu-id="96f22-123">**Result**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="96f22-124">X</span><span class="sxs-lookup"><span data-stu-id="96f22-124">X</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | <span data-ttu-id="96f22-125">3.0000 in.</span><span class="sxs-lookup"><span data-stu-id="96f22-125">3.0000 in.</span></span>  <br/> |
| <span data-ttu-id="96f22-126">Y</span><span class="sxs-lookup"><span data-stu-id="96f22-126">Y</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | <span data-ttu-id="96f22-127">4.0000 in.</span><span class="sxs-lookup"><span data-stu-id="96f22-127">4.0000 in.</span></span>  <br/> |
| <span data-ttu-id="96f22-128">-D</span><span class="sxs-lookup"><span data-stu-id="96f22-128">A-D</span></span>  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | <span data-ttu-id="96f22-129">PNT (3.0000, 4.0000)</span><span class="sxs-lookup"><span data-stu-id="96f22-129">PNT(3.0000 in., 4.0000 in.)</span></span>  <br/> |
   

