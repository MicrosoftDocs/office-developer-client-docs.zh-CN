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
# <a name="scratch-section"></a><span data-ttu-id="4999c-103">“Scratch”内容</span><span class="sxs-lookup"><span data-stu-id="4999c-103">Scratch Section</span></span>

<span data-ttu-id="4999c-104">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="4999c-104">A work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4999c-105">备注</span><span class="sxs-lookup"><span data-stu-id="4999c-105">Remarks</span></span>

<span data-ttu-id="4999c-p101">可以使用 **“插入内容”** 对话框添加此内容。方法是：在 ShapeSheet 窗口中单击右键，然后单击 **“插入内容”**。</span><span class="sxs-lookup"><span data-stu-id="4999c-p101">You can add this section by using the **Insert Section** dialog box. Right-click in the ShapeSheet window, and then click **Insert Section**.</span></span>
  
<span data-ttu-id="4999c-108">**Scratch** 部分通常用于隔离重复的复杂计算。</span><span class="sxs-lookup"><span data-stu-id="4999c-108">The **Scratch** section is typically used to isolate repeated complex calculations.</span></span> <span data-ttu-id="4999c-109">如果您的解决方案具有明确的目的，则为了清楚起见，应更明智的使用 **"User-Defined Cells"** 内容中的单元格，因为可以命名 User 单元格。</span><span class="sxs-lookup"><span data-stu-id="4999c-109">If your solution has a well-defined purpose, it's wiser to use a cell in the **User-Defined Cells** section for clarity because User cells can be named.</span></span> 
  
<span data-ttu-id="4999c-110">**"Scratch"内容中的** 单元格以两种不同的方式使用单位。</span><span class="sxs-lookup"><span data-stu-id="4999c-110">Cells in the **Scratch** section use units in two different ways.</span></span> <span data-ttu-id="4999c-111">X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。</span><span class="sxs-lookup"><span data-stu-id="4999c-111">X and Y cells use drawing units; A through D cells don't use units.</span></span> <span data-ttu-id="4999c-112"> (在 C 程序员的行话中，X 和 Y 单元格为"typed"，单元格 A 到 D 为"void"。) Scratch **X** 和 **Scratch Y** 单元格通常用于派生  *x*  坐标和  *y*  坐标（如 **PinX** 和 **PinY）** 或 **Geometry** 部分单元格中的 X 和 Y 单元格。</span><span class="sxs-lookup"><span data-stu-id="4999c-112">(In C programmers' jargon, X and Y cells are "typed," and cells A through D are "void.") The **Scratch X** and **Scratch Y** cells are often used for deriving  *x-*  and  *y-*  coordinates, such as **PinX** and **PinY**, or the X and Y cells found in a **Geometry** section cell.</span></span> <span data-ttu-id="4999c-113">Scratch cells A 到 D 可以显示您指定的任何单位。</span><span class="sxs-lookup"><span data-stu-id="4999c-113">Scratch cells A through D can display whatever units you specify.</span></span> 
  
<span data-ttu-id="4999c-114">这些单元格进一步的区别是，它们存储点值的方式不同。</span><span class="sxs-lookup"><span data-stu-id="4999c-114">A further difference is the way these cells store point values.</span></span> <span data-ttu-id="4999c-115">数据中的点Visio x，y 坐标的单个数据包 *( x，y)* 数据包。</span><span class="sxs-lookup"><span data-stu-id="4999c-115">A point in Visio is a single data package for an ( *x,y*) coordinate.</span></span> <span data-ttu-id="4999c-116">当公式返回点值时，将根据公式所在的 ShapeSheet 单元格，以三种方式之一解释该值。</span><span class="sxs-lookup"><span data-stu-id="4999c-116">When a formula returns a point value, that value is interpreted in one of three ways, depending on the ShapeSheet cell the formula is in.</span></span> <span data-ttu-id="4999c-117">与  *x*  坐标相关的单元格 (例如 **PinX** 或 **Geometry** 内容 X 列中的单元格) 仅提取点值的  *x*  坐标部分。</span><span class="sxs-lookup"><span data-stu-id="4999c-117">Cells that relate to  *x*  -coordinates (for example, **PinX**, or cells in the X column of a **Geometry** section) extract just the  *x*  -coordinate part of a point value.</span></span> <span data-ttu-id="4999c-118">与  *y*  坐标相关的单元格仅提取点值的  *y*  坐标部分。</span><span class="sxs-lookup"><span data-stu-id="4999c-118">Cells that relate to  *y*  -coordinates extract just the  *y*  -coordinate part of a point value.</span></span> 
  
<span data-ttu-id="4999c-119">例如，Visio三种方法 `PNT(3,4)` 提取公式。</span><span class="sxs-lookup"><span data-stu-id="4999c-119">For example, Visio extracts the formula  `PNT(3,4)` in these three ways.</span></span> 
  
|<span data-ttu-id="4999c-120">**Cell**</span><span class="sxs-lookup"><span data-stu-id="4999c-120">**Cell**</span></span>|<span data-ttu-id="4999c-121">**输入值**</span><span class="sxs-lookup"><span data-stu-id="4999c-121">**If you enter**</span></span>|<span data-ttu-id="4999c-122">**Visio 处理方式**</span><span class="sxs-lookup"><span data-stu-id="4999c-122">**Visio treats it as**</span></span>|<span data-ttu-id="4999c-123">**结果**</span><span class="sxs-lookup"><span data-stu-id="4999c-123">**Result**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4999c-124">X</span><span class="sxs-lookup"><span data-stu-id="4999c-124">X</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | <span data-ttu-id="4999c-125">3.0000 in.</span><span class="sxs-lookup"><span data-stu-id="4999c-125">3.0000 in.</span></span>  <br/> |
| <span data-ttu-id="4999c-126">Y</span><span class="sxs-lookup"><span data-stu-id="4999c-126">Y</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | <span data-ttu-id="4999c-127">4.0000 in.</span><span class="sxs-lookup"><span data-stu-id="4999c-127">4.0000 in.</span></span>  <br/> |
| <span data-ttu-id="4999c-128">A-D</span><span class="sxs-lookup"><span data-stu-id="4999c-128">A-D</span></span>  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | <span data-ttu-id="4999c-129">PNT (3.0000 in.， 4.0000 in.) </span><span class="sxs-lookup"><span data-stu-id="4999c-129">PNT(3.0000 in., 4.0000 in.)</span></span>  <br/> |
   

