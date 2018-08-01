---
title: Position 单元格（“Tabs”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251755
localization_priority: Normal
ms.assetid: 40d7e38e-b3b0-8616-ed27-1f963a841e03
description: 指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。
ms.openlocfilehash: 06f3a9fd5cfdf78f5383e70f32f8514b0adab114
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780973"
---
# <a name="position-cell-tabs-section"></a><span data-ttu-id="35a25-105">Position 单元格（“Tabs”部分）</span><span class="sxs-lookup"><span data-stu-id="35a25-105">Position Cell (Tabs Section)</span></span>

<span data-ttu-id="35a25-p102">指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。</span><span class="sxs-lookup"><span data-stu-id="35a25-p102">Specifies the position of a tab stop. The tab position is independent of the scale of the drawing. If the drawing is scaled, the tab position remains the same.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="35a25-109">注释</span><span class="sxs-lookup"><span data-stu-id="35a25-109">Remarks</span></span>

<span data-ttu-id="35a25-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Position 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="35a25-110">To get a reference to the Position cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="35a25-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="35a25-111">Cell name:</span></span>  <br/> | <span data-ttu-id="35a25-112">选项卡。</span><span class="sxs-lookup"><span data-stu-id="35a25-112">Tabs.</span></span>  <span data-ttu-id="35a25-113">*ij*其中*i*和*j* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="35a25-113">*ij*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="35a25-114">要从某个程序按索引获取对 Position 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="35a25-114">To get a reference to the Position cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="35a25-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="35a25-115">Section index:</span></span>  <br/> |<span data-ttu-id="35a25-116">**visSectionTab**</span><span class="sxs-lookup"><span data-stu-id="35a25-116">**visSectionTab**</span></span> <br/> |
| <span data-ttu-id="35a25-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="35a25-117">Row index:</span></span>  <br/> |<span data-ttu-id="35a25-118">**visRowTab** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="35a25-118">**visRowTab** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="35a25-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="35a25-119">Cell index:</span></span>  <br/> | <span data-ttu-id="35a25-120">(*j* \* 3) + **visTabPos**</span><span class="sxs-lookup"><span data-stu-id="35a25-120">(*j*  \*3) + **visTabPos**</span></span> <br/> |
   

