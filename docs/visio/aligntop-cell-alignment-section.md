---
title: AlignTop 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50
localization_priority: Normal
ms.assetid: 56e0b544-8504-0fbb-5810-7cf94d775f7c
description: 确定形状的上边框依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。
ms.openlocfilehash: 399514aa95897348238008715ee92694d57bad96
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779660"
---
# <a name="aligntop-cell-alignment-section"></a><span data-ttu-id="f9a3e-103">AlignTop 单元格（“Alignment”部分）</span><span class="sxs-lookup"><span data-stu-id="f9a3e-103">AlignTop Cell (Alignment Section)</span></span>

<span data-ttu-id="f9a3e-104">确定形状的上边框依其对齐的水平参考线或辅助点的垂直位置（该位置是相对于其父级的原点而言的）。</span><span class="sxs-lookup"><span data-stu-id="f9a3e-104">Determines the vertical position, relative to the origin of its parent, of a horizontal guide or guide point to which the shape's top border is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f9a3e-105">注释</span><span class="sxs-lookup"><span data-stu-id="f9a3e-105">Remarks</span></span>

<span data-ttu-id="f9a3e-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignTop 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-106">To get a reference to the AlignTop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f9a3e-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-107">Cell name:</span></span>  <br/> | <span data-ttu-id="f9a3e-108">AlignTop</span><span class="sxs-lookup"><span data-stu-id="f9a3e-108">AlignTop</span></span>  <br/> |
   
<span data-ttu-id="f9a3e-109">要从某个程序按索引获取对 AlignTop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-109">To get a reference to the AlignTop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f9a3e-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-110">Section index:</span></span>  <br/> |<span data-ttu-id="f9a3e-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f9a3e-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f9a3e-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-112">Row index:</span></span>  <br/> |<span data-ttu-id="f9a3e-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="f9a3e-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="f9a3e-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f9a3e-114">Cell index:</span></span>  <br/> |<span data-ttu-id="f9a3e-115">**visAlignTop**</span><span class="sxs-lookup"><span data-stu-id="f9a3e-115">**visAlignTop**</span></span> <br/> |
   

