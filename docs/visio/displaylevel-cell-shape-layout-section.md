---
title: DisplayLevel 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80001
localization_priority: Normal
ms.assetid: 08b730c4-5dd8-106e-ddf3-da2c942e2ef6
description: 确定形状的显示级别分隔条（Z 顺序分组的相对范围）。
ms.openlocfilehash: 4f7e3fcb2d28f8c4c0706502c66444c121ae6ee6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408143"
---
# <a name="displaylevel-cell-shape-layout-section"></a><span data-ttu-id="f67c4-103">DisplayLevel 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="f67c4-103">DisplayLevel Cell (Shape Layout Section)</span></span>

<span data-ttu-id="f67c4-104">确定形状的显示级别分隔条（Z 顺序分组的相对范围）。</span><span class="sxs-lookup"><span data-stu-id="f67c4-104">Determines the display level band (the relative range of Z-order grouping) for the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f67c4-105">备注</span><span class="sxs-lookup"><span data-stu-id="f67c4-105">Remarks</span></span>

<span data-ttu-id="f67c4-p101">Z 顺序是形状在绘图页上的显示顺序。当一个形状与另一个形状重叠时，Z 顺序较高的形状显示在 Z 顺序较低的形状之前。</span><span class="sxs-lookup"><span data-stu-id="f67c4-p101">Z-order is the display order for shapes on the drawing page. A shape that is higher in the Z-order appears in front of a shape that is lower in the Z-order when one of the shapes overlays the other one.</span></span> 
  
<span data-ttu-id="f67c4-p102">显示级别将形状分为不同的组或分隔条。和下层分隔条中的形状相比，给定分隔条中所有形状的 Z 顺序都较高。默认情况下，大多数形状的显示级别为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="f67c4-p102">The display level divides shapes into groupings, or bands. All shapes in a given band have a higher Z-order than the shapes in a lower band. By default, most shapes have a display level of zero (0).</span></span>
  
<span data-ttu-id="f67c4-p103">显示级别的范围从 -32,767 到 +32,767。具有相同显示级别的形状组合为一个分隔条，这些形状在该分隔条内仍根据 Z 顺序彼此分级。</span><span class="sxs-lookup"><span data-stu-id="f67c4-p103">The range of display levels is from -32,767 to +32,767. Shapes that have the same display level are combined into a single band, within which they are also ranked relative to one another by Z-order.</span></span>
  
<span data-ttu-id="f67c4-113">可以使用命令"前移"、"向后发送"、"**前** 移"和"发送到后退"来更改带内形状的 Z **顺序**。</span><span class="sxs-lookup"><span data-stu-id="f67c4-113">You can change the Z-order of shapes within a band by using the commands **Bring Forward**, **Send Backward**, **Bring to Front**, and **Send to Back**.</span></span> <span data-ttu-id="f67c4-114">如果这些命令将形状从给定带区中移开，Microsoft Visio 将在形状的 DisplayLevel 单元格中显示保留值 -32768，除非该单元格受到保护。</span><span class="sxs-lookup"><span data-stu-id="f67c4-114">If those commands move a shape out of its given band, Microsoft Visio displays the reserved value -32768 in the shape's DisplayLevel cell, unless the cell is guarded.</span></span> <span data-ttu-id="f67c4-115">在这种情况下，无法将形状移动到其他带区，并且Visio警告"形状保护和/或图层属性阻止完全执行此命令"。</span><span class="sxs-lookup"><span data-stu-id="f67c4-115">In that case, the shape cannot be moved to a different band, and Visio displays the warning "Shape protection and/or layer properties prevent complete execution of this command."</span></span> 
  
<span data-ttu-id="f67c4-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DisplayLevel 单元格的引用，请使用以下内容。</span><span class="sxs-lookup"><span data-stu-id="f67c4-116">To get a reference to the DisplayLevel cell by name from another formula or from a program by using the **CellsU** property, use the following.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f67c4-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f67c4-117">Cell name:</span></span>  <br/> |<span data-ttu-id="f67c4-118">DisplayLevel</span><span class="sxs-lookup"><span data-stu-id="f67c4-118">DisplayLevel</span></span>  <br/> |
   
<span data-ttu-id="f67c4-119">若要从某个程序按索引获取对 DisplayLevel 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f67c4-119">To get a reference to the DisplayLevel cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f67c4-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f67c4-120">Section index:</span></span>  <br/> |<span data-ttu-id="f67c4-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f67c4-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f67c4-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="f67c4-122">Row index:</span></span>  <br/> |<span data-ttu-id="f67c4-123">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="f67c4-123">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="f67c4-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f67c4-124">Cell index:</span></span>  <br/> |<span data-ttu-id="f67c4-125">**visSLODisplayLevel**</span><span class="sxs-lookup"><span data-stu-id="f67c4-125">**visSLODisplayLevel**</span></span> <br/> |
   

