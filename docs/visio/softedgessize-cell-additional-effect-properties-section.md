---
title: SoftEdgesSize 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果，以向 100.00 0.00 从磅为单位的大小。 如果 SoftEdgesSize 单元格的值为 0，则该形状没有柔化边缘。
ms.openlocfilehash: 3b301ae2e8c82867be2a486f2e93c2275fbf3914
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781407"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a><span data-ttu-id="78295-104">SoftEdgesSize 单元格 （其他效果属性内容）</span><span class="sxs-lookup"><span data-stu-id="78295-104">SoftEdgesSize Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="78295-105">确定柔化边缘效果，以向 100.00 0.00 从磅为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="78295-105">Determines the size of a soft edge effect, in points from 0.00 to 100.00.</span></span> <span data-ttu-id="78295-106">如果**SoftEdgesSize**单元格的值为 0，则该形状没有柔化边缘。</span><span class="sxs-lookup"><span data-stu-id="78295-106">If the **SoftEdgesSize** cell has a value of 0, the shape does not have soft edges.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="78295-107">备注</span><span class="sxs-lookup"><span data-stu-id="78295-107">Remarks</span></span>

<span data-ttu-id="78295-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SoftEdgesSize**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="78295-108">To get a reference to the **SoftEdgesSize** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="78295-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="78295-109">Cell name:</span></span>  <br/> | <span data-ttu-id="78295-110">SoftEdgesSize</span><span class="sxs-lookup"><span data-stu-id="78295-110">SoftEdgesSize</span></span>  <br/> |
   
<span data-ttu-id="78295-111">若要从某个程序按索引获取对**SoftEdgesSize**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="78295-111">To get a reference to the **SoftEdgesSize** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="78295-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="78295-112">Section index:</span></span>  <br/> |<span data-ttu-id="78295-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="78295-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="78295-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="78295-114">Row index:</span></span>  <br/> |<span data-ttu-id="78295-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="78295-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="78295-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="78295-116">Cell index:</span></span>  <br/> |<span data-ttu-id="78295-117">**visSoftEdgesSize**</span><span class="sxs-lookup"><span data-stu-id="78295-117">**visSoftEdgesSize**</span></span> <br/> |
   

