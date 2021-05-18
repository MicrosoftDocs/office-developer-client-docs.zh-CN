---
title: 'SketchAmount Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7c7353b7-f28e-4004-bf13-6e9714fbed37
description: 确定草图效果的失真量，以 0 到 25 之间的整数表示。
ms.openlocfilehash: fd9ee3390d05f24d81d9c6677160155b0f0f0d35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404419"
---
# <a name="sketchamount-cell-additional-effect-properties-section"></a><span data-ttu-id="08d2d-103">SketchAmount Cell (Additional Effect Properties Section) </span><span class="sxs-lookup"><span data-stu-id="08d2d-103">SketchAmount Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="08d2d-104">确定草图效果的失真量，以 0 到 25 之间的整数表示。</span><span class="sxs-lookup"><span data-stu-id="08d2d-104">Determines the amount of distortion for a sketch effect, as an integer between 0 and 25.</span></span> 
  
|<span data-ttu-id="08d2d-105">**值**</span><span class="sxs-lookup"><span data-stu-id="08d2d-105">**Value**</span></span>|<span data-ttu-id="08d2d-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="08d2d-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08d2d-107">0</span><span class="sxs-lookup"><span data-stu-id="08d2d-107">0</span></span>  <br/> |<span data-ttu-id="08d2d-108">形状没有应用草图效果。</span><span class="sxs-lookup"><span data-stu-id="08d2d-108">The shape has no sketch effect applied to it.</span></span>  <br/> |
|<span data-ttu-id="08d2d-109">1-25</span><span class="sxs-lookup"><span data-stu-id="08d2d-109">1-25</span></span>  <br/> |<span data-ttu-id="08d2d-110">形状应用了草图失真，其中值 1 表示最失真，25 表示最小。</span><span class="sxs-lookup"><span data-stu-id="08d2d-110">The shape has sketch distortion applied to it, where a value of 1 is the most distortion and 25 is the least.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08d2d-111">备注</span><span class="sxs-lookup"><span data-stu-id="08d2d-111">Remarks</span></span>

<span data-ttu-id="08d2d-112">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SketchAmount** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="08d2d-112">To get a reference to the **SketchAmount** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08d2d-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="08d2d-113">Cell name:</span></span>  <br/> | <span data-ttu-id="08d2d-114">SketchAmount</span><span class="sxs-lookup"><span data-stu-id="08d2d-114">SketchAmount</span></span>  <br/> |
   
<span data-ttu-id="08d2d-115">若要从程序按索引获取对 **SketchAmount** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="08d2d-115">To get a reference to the **SketchAmount** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08d2d-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="08d2d-116">Section index:</span></span>  <br/> |<span data-ttu-id="08d2d-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="08d2d-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="08d2d-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="08d2d-118">Row index:</span></span>  <br/> |<span data-ttu-id="08d2d-119">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="08d2d-119">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="08d2d-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="08d2d-120">Cell index:</span></span>  <br/> |<span data-ttu-id="08d2d-121">**visSketchAmount**</span><span class="sxs-lookup"><span data-stu-id="08d2d-121">**visSketchAmount**</span></span> <br/> |
   

