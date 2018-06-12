---
title: NoSnap 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm740
localization_priority: Normal
ms.assetid: 0e6c8621-868c-9eac-926b-3049f18023b0
description: 确定其他形状是否与路径对齐。
ms.openlocfilehash: 111f3773cb1df9033ed5a7b0b146d40ce6b26df0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780802"
---
# <a name="nosnap-cell-geometry-section"></a><span data-ttu-id="3a422-103">NoSnap 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="3a422-103">NoSnap Cell (Geometry Section)</span></span>

<span data-ttu-id="3a422-104">确定其他形状是否与路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3a422-104">Determines whether other shapes snap to a path.</span></span>
  
|<span data-ttu-id="3a422-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3a422-105">**Value**</span></span>|<span data-ttu-id="3a422-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a422-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="3a422-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="3a422-107">TRUE</span></span>  <br/> | <span data-ttu-id="3a422-108">不允许其他形状与该路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3a422-108">Do not allow other shapes to snap to this path.</span></span>  <br/> |
| <span data-ttu-id="3a422-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="3a422-109">FALSE</span></span>  <br/> | <span data-ttu-id="3a422-110">允许其他形状与该路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3a422-110">Allow other shapes to snap to this path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a422-111">注释</span><span class="sxs-lookup"><span data-stu-id="3a422-111">Remarks</span></span>

<span data-ttu-id="3a422-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 NoSnap 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3a422-112">To get a reference to the NoSnap cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3a422-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3a422-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3a422-114">Geometry *i* 。NoSnap 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="3a422-114">Geometry  *i*  .NoSnap            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="3a422-115">若要从某个程序按索引获取对 NoSnap 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="3a422-115">To get a reference to the NoSnap cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3a422-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3a422-116">Section index:</span></span>  <br/> |<span data-ttu-id="3a422-117">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="3a422-117">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="3a422-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3a422-118">Row index:</span></span>  <br/> |<span data-ttu-id="3a422-119">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="3a422-119">**visRowComponent**</span></span> <br/> |
| <span data-ttu-id="3a422-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3a422-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3a422-121">**visCompNoSnap**</span><span class="sxs-lookup"><span data-stu-id="3a422-121">**visCompNoSnap**</span></span> <br/> |
   

