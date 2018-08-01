---
title: AlignCenter 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm25
localization_priority: Normal
ms.assetid: 7d4416b2-429b-713e-61dc-8b2ead0e6053
description: 确定形状的水平中心依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: 342385dc2d08efd95e8dbad9d96ab59b2133ed7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779630"
---
# <a name="aligncenter-cell-alignment-section"></a><span data-ttu-id="358d5-103">AlignCenter 单元格（“Alignment”部分）</span><span class="sxs-lookup"><span data-stu-id="358d5-103">AlignCenter Cell (Alignment Section)</span></span>

<span data-ttu-id="358d5-104">确定形状的水平中心依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。</span><span class="sxs-lookup"><span data-stu-id="358d5-104">Determines the horizontal position, relative to the origin of its parent, of a vertical guide or guide point to which the shape's horizontal center is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="358d5-105">注释</span><span class="sxs-lookup"><span data-stu-id="358d5-105">Remarks</span></span>

<span data-ttu-id="358d5-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignCenter 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="358d5-106">To get a reference to the AlignCenter cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="358d5-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="358d5-107">Cell name:</span></span>  <br/> | <span data-ttu-id="358d5-108">AlignCenter</span><span class="sxs-lookup"><span data-stu-id="358d5-108">AlignCenter</span></span>  <br/> |
   
<span data-ttu-id="358d5-109">要从某个程序按索引获取对 AlignCenter 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="358d5-109">To get a reference to the AlignCenter cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="358d5-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="358d5-110">Section index:</span></span>  <br/> |<span data-ttu-id="358d5-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="358d5-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="358d5-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="358d5-112">Row index:</span></span>  <br/> |<span data-ttu-id="358d5-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="358d5-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="358d5-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="358d5-114">Cell index:</span></span>  <br/> |<span data-ttu-id="358d5-115">**visAlignCenter**</span><span class="sxs-lookup"><span data-stu-id="358d5-115">**visAlignCenter**</span></span> <br/> |
   

