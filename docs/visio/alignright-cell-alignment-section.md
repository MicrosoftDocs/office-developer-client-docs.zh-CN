---
title: AlignRight 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251297
localization_priority: Normal
ms.assetid: c6d298a4-1602-a53c-bb5d-2ef16b43f722
description: 确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: 558808908107a3e42d9d6e4a6fc1cf177150edb9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439770"
---
# <a name="alignright-cell-alignment-section"></a><span data-ttu-id="172f5-103">AlignRight 单元格（“Alignment”内容）</span><span class="sxs-lookup"><span data-stu-id="172f5-103">AlignRight Cell (Alignment Section)</span></span>

<span data-ttu-id="172f5-104">确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。</span><span class="sxs-lookup"><span data-stu-id="172f5-104">Determines the horizontal position, relative to the origin of its parent, of a vertical guide or guide point to which the shape's right border is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="172f5-105">说明</span><span class="sxs-lookup"><span data-stu-id="172f5-105">Remarks</span></span>

<span data-ttu-id="172f5-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignRight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="172f5-106">To get a reference to the AlignRight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="172f5-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="172f5-107">Cell name:</span></span>  <br/> | <span data-ttu-id="172f5-108">AlignRight</span><span class="sxs-lookup"><span data-stu-id="172f5-108">AlignRight</span></span>  <br/> |
   
<span data-ttu-id="172f5-109">要从某个程序按索引获取对 AlignRight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="172f5-109">To get a reference to the AlignRight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="172f5-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="172f5-110">Section index:</span></span>  <br/> |<span data-ttu-id="172f5-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="172f5-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="172f5-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="172f5-112">Row index:</span></span>  <br/> |<span data-ttu-id="172f5-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="172f5-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="172f5-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="172f5-114">Cell index:</span></span>  <br/> |<span data-ttu-id="172f5-115">**visAlignRight**</span><span class="sxs-lookup"><span data-stu-id="172f5-115">**visAlignRight**</span></span> <br/> |
   

