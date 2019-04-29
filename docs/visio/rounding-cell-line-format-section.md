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
ms.openlocfilehash: d64d3266e3dd2b0a3998955efe271aab04905fbf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427008"
---
# <a name="rounding-cell-line-format-section"></a><span data-ttu-id="cca24-105">Rounding 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="cca24-105">Rounding Cell (Line Format Section)</span></span>

<span data-ttu-id="cca24-p102">指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。</span><span class="sxs-lookup"><span data-stu-id="cca24-p102">Indicates the radius of the rounding arc applied where two contiguous segments of a path meet. For example, rounding can be used to give a rectangle rounded corners. To set rounding, enter a value with units of measure (a number-unit pair).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cca24-109">说明</span><span class="sxs-lookup"><span data-stu-id="cca24-109">Remarks</span></span>

<span data-ttu-id="cca24-110">您还可以在 "**线条**" 对话框 (在 "**开始**" 选项卡上的 "**形状**" 组中, 单击 "**线条**", 指向 "**粗细**", 然后单击 "**其他线条**") 中设置此值。</span><span class="sxs-lookup"><span data-stu-id="cca24-110">You can also set this value in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**).</span></span>
  
<span data-ttu-id="cca24-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Rounding 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cca24-111">To get a reference to the Rounding cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cca24-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cca24-112">Cell name:</span></span>  <br/> |<span data-ttu-id="cca24-113">Rounding</span><span class="sxs-lookup"><span data-stu-id="cca24-113">Rounding</span></span>  <br/> |
   
<span data-ttu-id="cca24-114">若要从某个程序按索引获取对 Rounding 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cca24-114">To get a reference to the Rounding cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cca24-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cca24-115">Section index:</span></span>  <br/> |<span data-ttu-id="cca24-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cca24-116">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="cca24-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="cca24-117">Row index:</span></span>  <br/> |<span data-ttu-id="cca24-118">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="cca24-118">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="cca24-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cca24-119">Cell index:</span></span>  <br/> |<span data-ttu-id="cca24-120">**visLineRounding**</span><span class="sxs-lookup"><span data-stu-id="cca24-120">**visLineRounding**</span></span> <br/> |
   

