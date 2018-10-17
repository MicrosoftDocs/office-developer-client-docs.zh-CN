---
title: EndTrigger 单元格（“Glue Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251331
localization_priority: Normal
ms.assetid: 8dc6515b-66ab-f1ac-18fd-820209f90991
description: 包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的终点以便保持其与另一个形状的连接。
ms.openlocfilehash: 3a2fadd3d00bc23e689bbf22bb3b5db3efcd71f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780187"
---
# <a name="endtrigger-cell-glue-info-section"></a><span data-ttu-id="8f962-103">EndTrigger 单元格（“Glue Info”部分）</span><span class="sxs-lookup"><span data-stu-id="8f962-103">EndTrigger Cell (Glue Info Section)</span></span>

<span data-ttu-id="8f962-104">包含由应用程序生成的触发器公式，该公式确定是否移动一维形状的终点以便保持其与另一个形状的连接。</span><span class="sxs-lookup"><span data-stu-id="8f962-104">Contains a trigger formula generated by the application that determines whether to move the endpoint of a 1-D shape to maintain its connection to another shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8f962-105">注释</span><span class="sxs-lookup"><span data-stu-id="8f962-105">Remarks</span></span>

<span data-ttu-id="8f962-p101">当使用动态粘附将一维形状粘附到另一个形状时，Visio 会生成一个公式，公式中引用其他形状的 EventXFMod 单元格。当更改该形状时，Visio 会重新计算引用其 EventXFMod 单元格的任何公式，包括 EndTrigger 单元格中的公式。该一维形状的其他公式引用 EndTrigger 单元格并根据需要移动一维形状的端点或变更形状。</span><span class="sxs-lookup"><span data-stu-id="8f962-p101">When you glue a 1-D shape to another shape using dynamic glue, Visio generates a formula that refers to the EventXFMod cell of the other shape. When that shape is changed, Visio recalculates any formula that refers to its EventXFMod cell, including the formula in the EndTrigger cell. Other formulas of the 1-D shape refer to the EndTrigger cell and move the endpoint of the 1-D shape or alter the shape as needed.</span></span>
  
<span data-ttu-id="8f962-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EndTrigger 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8f962-109">To get a reference to the EndTrigger cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8f962-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8f962-110">Cell name:</span></span>  <br/> | <span data-ttu-id="8f962-111">EndTrigger</span><span class="sxs-lookup"><span data-stu-id="8f962-111">EndTrigger</span></span>  <br/> |
   
<span data-ttu-id="8f962-112">要从某个程序按索引获取对 EndTrigger 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8f962-112">To get a reference to the EndTrigger cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8f962-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8f962-113">Section index:</span></span>  <br/> |<span data-ttu-id="8f962-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8f962-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8f962-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="8f962-115">Row index:</span></span>  <br/> |<span data-ttu-id="8f962-116">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="8f962-116">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="8f962-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8f962-117">Cell index:</span></span>  <br/> |<span data-ttu-id="8f962-118">**visEndTrigger**</span><span class="sxs-lookup"><span data-stu-id="8f962-118">**visEndTrigger**</span></span> <br/> |
   
