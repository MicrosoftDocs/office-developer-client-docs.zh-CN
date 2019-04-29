---
title: AlignBottom 单元格（“Alignment”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm20
localization_priority: Normal
ms.assetid: 234e7ffa-04e3-0204-c5be-7ff7a4d0d54c
description: 确定垂直位置，该位置是相对于其父级的原点、形状的下边框依其对齐的水平参考线或辅助点的原点而言的。
ms.openlocfilehash: 66fea9949f2f31eb5c3aaf43804ac0ec9f7e20fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411797"
---
# <a name="alignbottom-cell-alignment-section"></a><span data-ttu-id="8fa54-103">AlignBottom 单元格（“Alignment”内容）</span><span class="sxs-lookup"><span data-stu-id="8fa54-103">AlignBottom Cell (Alignment Section)</span></span>

<span data-ttu-id="8fa54-104">确定垂直位置，该位置是相对于其父级的原点、形状的下边框依其对齐的水平参考线或辅助点的原点而言的。</span><span class="sxs-lookup"><span data-stu-id="8fa54-104">Determines the vertical position, relative to the origin of its parent, of a horizontal guide or guide point to which the shape's bottom border is aligned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8fa54-105">说明</span><span class="sxs-lookup"><span data-stu-id="8fa54-105">Remarks</span></span>

<span data-ttu-id="8fa54-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 AlignBottom 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8fa54-106">To get a reference to the AlignBottom cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8fa54-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8fa54-107">Cell name:</span></span>  <br/> | <span data-ttu-id="8fa54-108">AlignBottom</span><span class="sxs-lookup"><span data-stu-id="8fa54-108">AlignBottom</span></span>  <br/> |
   
<span data-ttu-id="8fa54-109">要从某个程序按索引获取对 AlignBottom 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8fa54-109">To get a reference to the AlignBottom cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8fa54-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8fa54-110">Section index:</span></span>  <br/> |<span data-ttu-id="8fa54-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8fa54-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8fa54-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="8fa54-112">Row index:</span></span>  <br/> |<span data-ttu-id="8fa54-113">**visRowAlign**</span><span class="sxs-lookup"><span data-stu-id="8fa54-113">**visRowAlign**</span></span> <br/> |
| <span data-ttu-id="8fa54-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8fa54-114">Cell index:</span></span>  <br/> |<span data-ttu-id="8fa54-115">**visAlignBottom**</span><span class="sxs-lookup"><span data-stu-id="8fa54-115">**visAlignBottom**</span></span> <br/> |
   

