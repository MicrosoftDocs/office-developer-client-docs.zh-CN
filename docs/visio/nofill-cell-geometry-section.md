---
title: NoFill 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm710
localization_priority: Normal
ms.assetid: 0ba7f6da-681b-b749-fe72-afbca23d7e16
description: 指示是否可以填充路径。
ms.openlocfilehash: 301f30b644e338ff9e597a7a7d8226b9c8a4462f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415017"
---
# <a name="nofill-cell-geometry-section"></a><span data-ttu-id="e5e90-103">NoFill 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="e5e90-103">NoFill Cell (Geometry Section)</span></span>

<span data-ttu-id="e5e90-104">指示是否可以填充路径。</span><span class="sxs-lookup"><span data-stu-id="e5e90-104">Indicates whether a path can be filled.</span></span>
  
|<span data-ttu-id="e5e90-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e5e90-105">**Value**</span></span>|<span data-ttu-id="e5e90-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5e90-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e5e90-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="e5e90-107">TRUE</span></span>  <br/> | <span data-ttu-id="e5e90-108">不填充该路径，即使可填充形状中的其他路径。</span><span class="sxs-lookup"><span data-stu-id="e5e90-108">The path is not filled even if other paths in the shape are filled.</span></span>  <br/> |
| <span data-ttu-id="e5e90-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="e5e90-109">FALSE</span></span>  <br/> | <span data-ttu-id="e5e90-110">形状的填充适用于该路径，即使它不是封闭的路径。</span><span class="sxs-lookup"><span data-stu-id="e5e90-110">The shape's fill applies to the path, even if it isn't closed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e5e90-111">备注</span><span class="sxs-lookup"><span data-stu-id="e5e90-111">Remarks</span></span>

<span data-ttu-id="e5e90-p101">如果将形状的填充图案设置为非 (0)，则不填充该形状的任何路径。此单元格用于选择性地禁用形状中路径的填充方式。</span><span class="sxs-lookup"><span data-stu-id="e5e90-p101">If you set a shape's fill pattern to none (0), none of its paths are filled. This cell is used to turn the fill off selectively for a path within a shape.</span></span>
  
<span data-ttu-id="e5e90-114">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoFill 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e5e90-114">To get a reference to the NoFill cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e5e90-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e5e90-115">Cell name:</span></span>  <br/> | <span data-ttu-id="e5e90-116">Geometry  *i*  .NoFill 其中  *i*  = <1>、2、3...</span><span class="sxs-lookup"><span data-stu-id="e5e90-116">Geometry  *i*  .NoFill            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e5e90-117">要从某个程序按索引获取对 NoFill 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e5e90-117">To get a reference to the NoFill cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e5e90-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e5e90-118">Section index:</span></span>  <br/> |<span data-ttu-id="e5e90-119">**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="e5e90-119">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="e5e90-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="e5e90-120">Row index:</span></span>  <br/> |<span data-ttu-id="e5e90-121">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="e5e90-121">**visRowComponent**</span></span> <br/> |
| <span data-ttu-id="e5e90-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e5e90-122">Cell index:</span></span>  <br/> |<span data-ttu-id="e5e90-123">**visCompNoFill**</span><span class="sxs-lookup"><span data-stu-id="e5e90-123">**visCompNoFill**</span></span> <br/> |
   

