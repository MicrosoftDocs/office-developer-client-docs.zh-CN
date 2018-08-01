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
ms.openlocfilehash: 8bb3f68a9b7e6fb08cbd95ee0240e35f519d4fb8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779644"
---
# <a name="alignright-cell-alignment-section"></a><span data-ttu-id="1f804-103">AlignRight 单元格（“Alignment”部分）</span><span class="sxs-lookup"><span data-stu-id="1f804-103">AlignRight Cell (Alignment Section)</span></span>

<span data-ttu-id="1f804-104">确定形状的右边框依其对齐的垂直参考线或辅助点的水平位置（该位置是相对于其父级的原点而言的）。</span><span class="sxs-lookup"><span data-stu-id="1f804-104">Determines the horizontal position, relative to the origin of its parent, of a vertical guide or guide point to which the shape's right border is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1f804-105">注释</span><span class="sxs-lookup"><span data-stu-id="1f804-105">Remarks</span></span>

<span data-ttu-id="1f804-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignRight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1f804-106">To get a reference to the AlignRight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1f804-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1f804-107">Cell name:</span></span>  <br/> | <span data-ttu-id="1f804-108">AlignRight</span><span class="sxs-lookup"><span data-stu-id="1f804-108">AlignRight</span></span>  <br/> |
   
<span data-ttu-id="1f804-109">要从某个程序按索引获取对 AlignRight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1f804-109">To get a reference to the AlignRight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1f804-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1f804-110">Section index:</span></span>  <br/> |<span data-ttu-id="1f804-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1f804-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="1f804-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="1f804-112">Row index:</span></span>  <br/> |<span data-ttu-id="1f804-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="1f804-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="1f804-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1f804-114">Cell index:</span></span>  <br/> |<span data-ttu-id="1f804-115">**visAlignRight**</span><span class="sxs-lookup"><span data-stu-id="1f804-115">**visAlignRight**</span></span> <br/> |
   

