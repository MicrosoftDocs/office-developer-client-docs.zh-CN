---
title: SketchAmount 单元格 （其他效果属性内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7c7353b7-f28e-4004-bf13-6e9714fbed37
description: 确定为 0 到 25 之间的整数素描效果，扭曲的四量。
ms.openlocfilehash: d5ae954f2eab48722c48c9bc4b3f640403dbb3ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781371"
---
# <a name="sketchamount-cell-additional-effect-properties-section"></a><span data-ttu-id="6255a-103">SketchAmount 单元格 （其他效果属性内容）</span><span class="sxs-lookup"><span data-stu-id="6255a-103">SketchAmount Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="6255a-104">确定为 0 到 25 之间的整数素描效果，扭曲的四量。</span><span class="sxs-lookup"><span data-stu-id="6255a-104">Determines the amount of distortion for a sketch effect, as an integer between 0 and 25.</span></span> 
  
|<span data-ttu-id="6255a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6255a-105">**Value**</span></span>|<span data-ttu-id="6255a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="6255a-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6255a-107">0</span><span class="sxs-lookup"><span data-stu-id="6255a-107">0</span></span>  <br/> |<span data-ttu-id="6255a-108">该形状具有应用于它没有素描效果。</span><span class="sxs-lookup"><span data-stu-id="6255a-108">The shape has no sketch effect applied to it.</span></span>  <br/> |
|<span data-ttu-id="6255a-109">1-25</span><span class="sxs-lookup"><span data-stu-id="6255a-109">1-25</span></span>  <br/> |<span data-ttu-id="6255a-110">形状具有草图失真于，其中值为 1 是大多数失真，25 是最少。</span><span class="sxs-lookup"><span data-stu-id="6255a-110">The shape has sketch distortion applied to it, where a value of 1 is the most distortion and 25 is the least.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6255a-111">备注</span><span class="sxs-lookup"><span data-stu-id="6255a-111">Remarks</span></span>

<span data-ttu-id="6255a-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**SketchAmount**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6255a-112">To get a reference to the **SketchAmount** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6255a-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6255a-113">Cell name:</span></span>  <br/> | <span data-ttu-id="6255a-114">SketchAmount</span><span class="sxs-lookup"><span data-stu-id="6255a-114">SketchAmount</span></span>  <br/> |
   
<span data-ttu-id="6255a-115">若要从某个程序按索引获取对**SketchAmount**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="6255a-115">To get a reference to the **SketchAmount** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6255a-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6255a-116">Section index:</span></span>  <br/> |<span data-ttu-id="6255a-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6255a-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6255a-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="6255a-118">Row index:</span></span>  <br/> |<span data-ttu-id="6255a-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="6255a-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="6255a-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6255a-120">Cell index:</span></span>  <br/> |<span data-ttu-id="6255a-121">**visSketchAmount**</span><span class="sxs-lookup"><span data-stu-id="6255a-121">**visSketchAmount**</span></span> <br/> |
   

