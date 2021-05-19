---
title: 'SketchSeed Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6f62650d-36f8-4c6e-b79f-c9c397a5954d
description: 表示用于确定草图效果的几何图形的随机化值，为正整数。 当将草图效果应用于形状时，将随机创建 SketchSeed 单元格的值。
ms.openlocfilehash: 3ec58fbfa183d1a6d7bb6960672658f9a6cca073
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434394"
---
# <a name="sketchseed-cell-additional-effect-properties-section"></a><span data-ttu-id="38a9a-104">SketchSeed Cell (Additional Effect Properties Section) </span><span class="sxs-lookup"><span data-stu-id="38a9a-104">SketchSeed Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="38a9a-105">表示用于确定草图效果的几何图形的随机化值，为正整数。</span><span class="sxs-lookup"><span data-stu-id="38a9a-105">Represents a randomization value used to determine the geometry of a sketch effect, as a positive integer.</span></span> <span data-ttu-id="38a9a-106">当将草图效果应用于形状时，将随机创建 **SketchSeed** 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="38a9a-106">The value of the **SketchSeed** cell is randomly created when a sketch effect is applied to the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="38a9a-107">备注</span><span class="sxs-lookup"><span data-stu-id="38a9a-107">Remarks</span></span>

<span data-ttu-id="38a9a-108">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchSeed** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="38a9a-108">To get a reference to the **SketchSeed** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="38a9a-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="38a9a-109">Cell name:</span></span>  <br/> | <span data-ttu-id="38a9a-110">SketchSeed</span><span class="sxs-lookup"><span data-stu-id="38a9a-110">SketchSeed</span></span>  <br/> |
   
<span data-ttu-id="38a9a-111">若要从程序按索引获取对 **SketchSeed** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="38a9a-111">To get a reference to the **SketchSeed** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="38a9a-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="38a9a-112">Section index:</span></span>  <br/> |<span data-ttu-id="38a9a-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="38a9a-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="38a9a-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="38a9a-114">Row index:</span></span>  <br/> |<span data-ttu-id="38a9a-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="38a9a-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="38a9a-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="38a9a-116">Cell index:</span></span>  <br/> |<span data-ttu-id="38a9a-117">**visSketchSeed**</span><span class="sxs-lookup"><span data-stu-id="38a9a-117">**visSketchSeed**</span></span> <br/> |
   

