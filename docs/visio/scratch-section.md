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
ms.openlocfilehash: 16f0bac8f139c0b03d7826ac377a964d15296dd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781222"
---
# <a name="scratch-section"></a><span data-ttu-id="45ef1-103">“Scratch”内容</span><span class="sxs-lookup"><span data-stu-id="45ef1-103">Scratch Section</span></span>

<span data-ttu-id="45ef1-104">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="45ef1-104">A work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="45ef1-105">注解</span><span class="sxs-lookup"><span data-stu-id="45ef1-105">Remarks</span></span>

<span data-ttu-id="45ef1-106">使用**插入节**对话框，您可以添加此内容。</span><span class="sxs-lookup"><span data-stu-id="45ef1-106">You can add this section by using the **Insert Section** dialog box.</span></span> <span data-ttu-id="45ef1-107">在 ShapeSheet 窗口中，右键单击，然后单击**插入节**。</span><span class="sxs-lookup"><span data-stu-id="45ef1-107">Right-click in the ShapeSheet window, and then click **Insert Section**.</span></span>
  
<span data-ttu-id="45ef1-108">**草稿**部分通常用于将隔离重复复杂的计算。</span><span class="sxs-lookup"><span data-stu-id="45ef1-108">The **Scratch** section is typically used to isolate repeated complex calculations.</span></span> <span data-ttu-id="45ef1-109">如果您的解决方案必须定义完善的目的，则丝毫因为用户的单元格可以名为**用户定义单元格**部分中为清楚起见使用单元格。</span><span class="sxs-lookup"><span data-stu-id="45ef1-109">If your solution has a well-defined purpose, it's wiser to use a cell in the **User-Defined Cells** section for clarity because User cells can be named.</span></span> 
  
<span data-ttu-id="45ef1-110">**草稿**部分中的单元格使用两种不同方式的单位。</span><span class="sxs-lookup"><span data-stu-id="45ef1-110">Cells in the **Scratch** section use units in two different ways.</span></span> <span data-ttu-id="45ef1-111">X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。</span><span class="sxs-lookup"><span data-stu-id="45ef1-111">X and Y cells use drawing units; A through D cells don't use units.</span></span> <span data-ttu-id="45ef1-112">（C 程序员术语 X 和 Y 单元格"类型"，并以单元格 A 到 D 是"void。"）**草稿 X**和**Y 草稿**单元格通常用于派生*x*和*y*坐标，如**PinX**和**PinY**或位于**geometry**内容单元格中的 X 和 Y 单元格。</span><span class="sxs-lookup"><span data-stu-id="45ef1-112">(In C programmers' jargon, X and Y cells are "typed," and cells A through D are "void.") The **Scratch X** and **Scratch Y** cells are often used for deriving  *x-*  and  *y-*  coordinates, such as **PinX** and **PinY**, or the X and Y cells found in a **Geometry** section cell.</span></span> <span data-ttu-id="45ef1-113">草稿单元格 A 到 D 可以显示任何您指定的单位。</span><span class="sxs-lookup"><span data-stu-id="45ef1-113">Scratch cells A through D can display whatever units you specify.</span></span> 
  
<span data-ttu-id="45ef1-114">进一步的区别是这些单元格存储点值的方式。</span><span class="sxs-lookup"><span data-stu-id="45ef1-114">A further difference is the way these cells store point values.</span></span> <span data-ttu-id="45ef1-115">Visio 中的一个点 （ *x，y*） 坐标的单个数据包。</span><span class="sxs-lookup"><span data-stu-id="45ef1-115">A point in Visio is a single data package for an ( *x,y*) coordinate.</span></span> <span data-ttu-id="45ef1-116">当公式返回点值时，该值被解释中有三种方法，具体取决于公式是在的 ShapeSheet 单元格。</span><span class="sxs-lookup"><span data-stu-id="45ef1-116">When a formula returns a point value, that value is interpreted in one of three ways, depending on the ShapeSheet cell the formula is in.</span></span> <span data-ttu-id="45ef1-117">与*x*单元格的坐标 （例如， **PinX**或 X 列中的**geometry**内容中的单元格） 中提取刚刚*x* -协调点值的一部分。</span><span class="sxs-lookup"><span data-stu-id="45ef1-117">Cells that relate to  *x*  -coordinates (for example, **PinX**, or cells in the X column of a **Geometry** section) extract just the  *x*  -coordinate part of a point value.</span></span> <span data-ttu-id="45ef1-118">与*y*单元格的坐标提取刚刚*y* -协调点值的一部分。</span><span class="sxs-lookup"><span data-stu-id="45ef1-118">Cells that relate to  *y*  -coordinates extract just the  *y*  -coordinate part of a point value.</span></span> 
  
<span data-ttu-id="45ef1-119">例如，Visio 提取公式`PNT(3,4)`中以下三种方式。</span><span class="sxs-lookup"><span data-stu-id="45ef1-119">For example, Visio extracts the formula  `PNT(3,4)` in these three ways.</span></span> 
  
|<span data-ttu-id="45ef1-120">**Cell**</span><span class="sxs-lookup"><span data-stu-id="45ef1-120">**Cell**</span></span>|<span data-ttu-id="45ef1-121">**如果您输入**</span><span class="sxs-lookup"><span data-stu-id="45ef1-121">**If you enter**</span></span>|<span data-ttu-id="45ef1-122">**Visio 处理方式**</span><span class="sxs-lookup"><span data-stu-id="45ef1-122">**Visio treats it as**</span></span>|<span data-ttu-id="45ef1-123">**结果**</span><span class="sxs-lookup"><span data-stu-id="45ef1-123">**Result**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="45ef1-124">X</span><span class="sxs-lookup"><span data-stu-id="45ef1-124">X</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | <span data-ttu-id="45ef1-125">3.0000 in.</span><span class="sxs-lookup"><span data-stu-id="45ef1-125">3.0000 in.</span></span>  <br/> |
| <span data-ttu-id="45ef1-126">Y</span><span class="sxs-lookup"><span data-stu-id="45ef1-126">Y</span></span>  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | <span data-ttu-id="45ef1-127">4.0000 in.</span><span class="sxs-lookup"><span data-stu-id="45ef1-127">4.0000 in.</span></span>  <br/> |
| <span data-ttu-id="45ef1-128">A-D</span><span class="sxs-lookup"><span data-stu-id="45ef1-128">A-D</span></span>  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | <span data-ttu-id="45ef1-129">PNT (3.0000 英寸，4.0000 中。)</span><span class="sxs-lookup"><span data-stu-id="45ef1-129">PNT(3.0000 in., 4.0000 in.)</span></span>  <br/> |
   

