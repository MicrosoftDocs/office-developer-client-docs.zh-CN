---
title: AlignLeft 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm30
localization_priority: Normal
ms.assetid: d094411e-ed65-1d0d-5c35-68b003da2696
description: 确定形状的左边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: f2fc7ef62723812f7dde3f94272a90927272936e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779634"
---
# <a name="alignleft-cell-alignment-section"></a><span data-ttu-id="2c11c-103">AlignLeft 单元格（“Alignment”部分）</span><span class="sxs-lookup"><span data-stu-id="2c11c-103">AlignLeft Cell (Alignment Section)</span></span>

<span data-ttu-id="2c11c-104">确定形状的左边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。</span><span class="sxs-lookup"><span data-stu-id="2c11c-104">Determines the horizontal position, relative to the origin of its parent, of a vertical guide or guide point to which the shape's left border is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2c11c-105">注释</span><span class="sxs-lookup"><span data-stu-id="2c11c-105">Remarks</span></span>

<span data-ttu-id="2c11c-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignLeft 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2c11c-106">To get a reference to the AlignLeft cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2c11c-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2c11c-107">Cell name:</span></span>  <br/> | <span data-ttu-id="2c11c-108">AlignLeft</span><span class="sxs-lookup"><span data-stu-id="2c11c-108">AlignLeft</span></span>  <br/> |
   
<span data-ttu-id="2c11c-109">要从某个程序按索引获取对 AlignLeft 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2c11c-109">To get a reference to the AlignLeft cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2c11c-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2c11c-110">Section index:</span></span>  <br/> |<span data-ttu-id="2c11c-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2c11c-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2c11c-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="2c11c-112">Row index:</span></span>  <br/> |<span data-ttu-id="2c11c-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="2c11c-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="2c11c-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2c11c-114">Cell index:</span></span>  <br/> |<span data-ttu-id="2c11c-115">**visAlignLeft**</span><span class="sxs-lookup"><span data-stu-id="2c11c-115">**visAlignLeft**</span></span> <br/> |
   

