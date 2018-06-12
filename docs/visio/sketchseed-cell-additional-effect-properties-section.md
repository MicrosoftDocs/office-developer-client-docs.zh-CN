---
title: SketchSeed 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f62650d-36f8-4c6e-b79f-c9c397a5954d
description: 代表用来确定素描效果，为正整数的几何随机值。 素描效果应用于形状时随机创建 SketchSeed 单元格的值。
ms.openlocfilehash: 7c9d23e19da1a94bb37f1fc916e2f08095976d09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781377"
---
# <a name="sketchseed-cell-additional-effect-properties-section"></a><span data-ttu-id="20c93-104">SketchSeed 单元格 （其他效果属性内容）</span><span class="sxs-lookup"><span data-stu-id="20c93-104">SketchSeed Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="20c93-105">代表用来确定素描效果，为正整数的几何随机值。</span><span class="sxs-lookup"><span data-stu-id="20c93-105">Represents a randomization value used to determine the geometry of a sketch effect, as a positive integer.</span></span> <span data-ttu-id="20c93-106">素描效果应用于形状时随机创建**SketchSeed**单元格的值。</span><span class="sxs-lookup"><span data-stu-id="20c93-106">The value of the **SketchSeed** cell is randomly created when a sketch effect is applied to the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="20c93-107">备注</span><span class="sxs-lookup"><span data-stu-id="20c93-107">Remarks</span></span>

<span data-ttu-id="20c93-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchSeed**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="20c93-108">To get a reference to the **SketchSeed** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="20c93-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="20c93-109">Cell name:</span></span>  <br/> | <span data-ttu-id="20c93-110">SketchSeed</span><span class="sxs-lookup"><span data-stu-id="20c93-110">SketchSeed</span></span>  <br/> |
   
<span data-ttu-id="20c93-111">若要从某个程序按索引获取对**SketchSeed**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="20c93-111">To get a reference to the **SketchSeed** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="20c93-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="20c93-112">Section index:</span></span>  <br/> |<span data-ttu-id="20c93-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="20c93-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="20c93-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="20c93-114">Row index:</span></span>  <br/> |<span data-ttu-id="20c93-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="20c93-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="20c93-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="20c93-116">Cell index:</span></span>  <br/> |<span data-ttu-id="20c93-117">**visSketchSeed**</span><span class="sxs-lookup"><span data-stu-id="20c93-117">**visSketchSeed**</span></span> <br/> |
   

