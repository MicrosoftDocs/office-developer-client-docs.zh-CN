---
title: Rounding 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm860
localization_priority: Normal
ms.assetid: c44457ca-997a-5315-44dd-4218e4203550
description: 指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。
ms.openlocfilehash: 0624ec42978292e84965c978d25e4052fc41613f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781132"
---
# <a name="rounding-cell-line-format-section"></a><span data-ttu-id="5af71-105">Rounding 单元格（“Line Format”部分）</span><span class="sxs-lookup"><span data-stu-id="5af71-105">Rounding Cell (Line Format Section)</span></span>

<span data-ttu-id="5af71-p102">指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。</span><span class="sxs-lookup"><span data-stu-id="5af71-p102">Indicates the radius of the rounding arc applied where two contiguous segments of a path meet. For example, rounding can be used to give a rectangle rounded corners. To set rounding, enter a value with units of measure (a number-unit pair).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5af71-109">注解</span><span class="sxs-lookup"><span data-stu-id="5af71-109">Remarks</span></span>

<span data-ttu-id="5af71-110">您还可以设置此值在**线条**对话框 （在**主页**选项卡，**形状**组中，单击**线条**，指向**权重**，，然后单击**多行**）。</span><span class="sxs-lookup"><span data-stu-id="5af71-110">You can also set this value in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="5af71-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Rounding 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5af71-111">To get a reference to the Rounding cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5af71-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5af71-112">Cell name:</span></span>  <br/> |<span data-ttu-id="5af71-113">Rounding</span><span class="sxs-lookup"><span data-stu-id="5af71-113">Rounding</span></span>  <br/> |
   
<span data-ttu-id="5af71-114">若要从某个程序按索引获取对 Rounding 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5af71-114">To get a reference to the Rounding cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5af71-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5af71-115">Section index:</span></span>  <br/> |<span data-ttu-id="5af71-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5af71-116">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="5af71-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="5af71-117">Row index:</span></span>  <br/> |<span data-ttu-id="5af71-118">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="5af71-118">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="5af71-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5af71-119">Cell index:</span></span>  <br/> |<span data-ttu-id="5af71-120">**visLineRounding**</span><span class="sxs-lookup"><span data-stu-id="5af71-120">**visLineRounding**</span></span> <br/> |
   

