---
title: Width 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251194
localization_priority: Normal
ms.assetid: 992ae9d8-ea15-0f5c-ccd6-e4c536099692
description: 包含所选形状的宽度（以绘图单位计）。确定一维形状的宽度的默认公式是：
ms.openlocfilehash: 55e77c5ccfca2425a8a2985564448e0f656aebbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781655"
---
# <a name="width-cell-shape-transform-section"></a><span data-ttu-id="349db-104">Width 单元格（“Shape Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="349db-104">Width Cell (Shape Transform Section)</span></span>

<span data-ttu-id="349db-p102">包含所选形状的宽度（以绘图单位计）。确定一维形状的宽度的默认公式是：</span><span class="sxs-lookup"><span data-stu-id="349db-p102">Contains the width of the selected shape in drawing units. The default formula for determining the width of a 1-D shape is:</span></span>
  
<span data-ttu-id="349db-107">= SQRT((EndX - BeginX) ^ 2 + (EndY - BeginY) ^ 2)</span><span class="sxs-lookup"><span data-stu-id="349db-107">= SQRT((EndX - BeginX) ^ 2 + (EndY - BeginY) ^ 2)</span></span>
  
## <a name="remarks"></a><span data-ttu-id="349db-108">注释</span><span class="sxs-lookup"><span data-stu-id="349db-108">Remarks</span></span>

<span data-ttu-id="349db-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Width 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="349db-109">To get a reference to the Width cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="349db-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="349db-110">Cell name:</span></span>  <br/> | <span data-ttu-id="349db-111">宽度</span><span class="sxs-lookup"><span data-stu-id="349db-111">Width</span></span>  <br/> |
   
<span data-ttu-id="349db-112">要从某个程序按索引获取对 Width 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="349db-112">To get a reference to the Width cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="349db-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="349db-113">Section index:</span></span>  <br/> |<span data-ttu-id="349db-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="349db-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="349db-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="349db-115">Row index:</span></span>  <br/> |<span data-ttu-id="349db-116">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="349db-116">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="349db-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="349db-117">Cell index:</span></span>  <br/> |<span data-ttu-id="349db-118">**visXFormWidth**</span><span class="sxs-lookup"><span data-stu-id="349db-118">**visXFormWidth**</span></span> <br/> |
   

