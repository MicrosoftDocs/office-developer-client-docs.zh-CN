---
title: SketchSeed 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f62650d-36f8-4c6e-b79f-c9c397a5954d
description: 表示用于确定草图效果几何图形的随机值, 以正整数表示。 将草图效果应用于形状时, 会随机创建 SketchSeed 单元格的值。
ms.openlocfilehash: 3ec58fbfa183d1a6d7bb6960672658f9a6cca073
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315146"
---
# <a name="sketchseed-cell-additional-effect-properties-section"></a><span data-ttu-id="45e42-104">SketchSeed 单元格 ("其他效果属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="45e42-104">SketchSeed Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="45e42-105">表示用于确定草图效果几何图形的随机值, 以正整数表示。</span><span class="sxs-lookup"><span data-stu-id="45e42-105">Represents a randomization value used to determine the geometry of a sketch effect, as a positive integer.</span></span> <span data-ttu-id="45e42-106">将草图效果应用于形状时, 会随机创建**SketchSeed**单元格的值。</span><span class="sxs-lookup"><span data-stu-id="45e42-106">The value of the **SketchSeed** cell is randomly created when a sketch effect is applied to the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="45e42-107">注解</span><span class="sxs-lookup"><span data-stu-id="45e42-107">Remarks</span></span>

<span data-ttu-id="45e42-108">若要从另一个公式按名称获取对**SketchSeed**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="45e42-108">To get a reference to the **SketchSeed** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="45e42-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="45e42-109">Cell name:</span></span>  <br/> | <span data-ttu-id="45e42-110">SketchSeed</span><span class="sxs-lookup"><span data-stu-id="45e42-110">SketchSeed</span></span>  <br/> |
   
<span data-ttu-id="45e42-111">若要从某个程序按索引获取对**SketchSeed**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="45e42-111">To get a reference to the **SketchSeed** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="45e42-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="45e42-112">Section index:</span></span>  <br/> |<span data-ttu-id="45e42-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="45e42-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="45e42-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="45e42-114">Row index:</span></span>  <br/> |<span data-ttu-id="45e42-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="45e42-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="45e42-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="45e42-116">Cell index:</span></span>  <br/> |<span data-ttu-id="45e42-117">**visSketchSeed**</span><span class="sxs-lookup"><span data-stu-id="45e42-117">**visSketchSeed**</span></span> <br/> |
   

