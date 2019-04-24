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
ms.openlocfilehash: 60a6532aee0f391eb38609f6ed87577e5558d5c2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341126"
---
# <a name="nosnap-cell-geometry-section"></a><span data-ttu-id="3d478-103">NoSnap 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="3d478-103">NoSnap Cell (Geometry Section)</span></span>

<span data-ttu-id="3d478-104">确定其他形状是否与路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3d478-104">Determines whether other shapes snap to a path.</span></span>
  
|<span data-ttu-id="3d478-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="3d478-105">**Value**</span></span>|<span data-ttu-id="3d478-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="3d478-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="3d478-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="3d478-107">TRUE</span></span>  <br/> | <span data-ttu-id="3d478-108">不允许其他形状与该路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3d478-108">Do not allow other shapes to snap to this path.</span></span>  <br/> |
| <span data-ttu-id="3d478-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="3d478-109">FALSE</span></span>  <br/> | <span data-ttu-id="3d478-110">允许其他形状与该路径对齐。</span><span class="sxs-lookup"><span data-stu-id="3d478-110">Allow other shapes to snap to this path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d478-111">注解</span><span class="sxs-lookup"><span data-stu-id="3d478-111">Remarks</span></span>

<span data-ttu-id="3d478-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoSnap 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3d478-112">To get a reference to the NoSnap cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3d478-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3d478-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3d478-114">几何图形*i* 。NoSnap 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="3d478-114">Geometry  *i*  .NoSnap            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="3d478-115">要从某个程序按索引获取对 NoSnap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3d478-115">To get a reference to the NoSnap cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3d478-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3d478-116">Section index:</span></span>  <br/> |<span data-ttu-id="3d478-117">**visSectionFirstComponent** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="3d478-117">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="3d478-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3d478-118">Row index:</span></span>  <br/> |<span data-ttu-id="3d478-119">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="3d478-119">**visRowComponent**</span></span> <br/> |
| <span data-ttu-id="3d478-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3d478-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3d478-121">**visCompNoSnap**</span><span class="sxs-lookup"><span data-stu-id="3d478-121">**visCompNoSnap**</span></span> <br/> |
   

