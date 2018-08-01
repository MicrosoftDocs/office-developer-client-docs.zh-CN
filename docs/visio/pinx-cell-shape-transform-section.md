---
title: PinX 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm790
localization_priority: Normal
ms.assetid: dd88fb8d-3ec3-476a-870d-6642b191496f
description: 代表 x 的形状的旋转中心点 （旋转中心） 相对于其父级的原点坐标。
ms.openlocfilehash: 74e98732f1e0c44fa20c159070198ed4f98cee92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780852"
---
# <a name="pinx-cell-shape-transform-section"></a><span data-ttu-id="ad688-103">PinX 单元格（“Shape Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="ad688-103">PinX Cell (Shape Transform Section)</span></span>

<span data-ttu-id="ad688-104">代表*x*的形状的旋转中心点 （旋转中心） 相对于其父级的原点坐标。</span><span class="sxs-lookup"><span data-stu-id="ad688-104">Represents the  *x*  -coordinate of the shape's pin (center of rotation) in relation to the origin of its parent.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ad688-105">说明</span><span class="sxs-lookup"><span data-stu-id="ad688-105">Remarks</span></span>

<span data-ttu-id="ad688-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ad688-106">To get a reference to the PinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ad688-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ad688-107">Cell name:</span></span>  <br/> | <span data-ttu-id="ad688-108">PinX</span><span class="sxs-lookup"><span data-stu-id="ad688-108">PinX</span></span>  <br/> |
   
<span data-ttu-id="ad688-109">要从某个程序按索引获取对 PinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ad688-109">To get a reference to the PinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ad688-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ad688-110">Section index:</span></span>  <br/> |<span data-ttu-id="ad688-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ad688-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ad688-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="ad688-112">Row index:</span></span>  <br/> |<span data-ttu-id="ad688-113">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="ad688-113">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="ad688-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ad688-114">Cell index:</span></span>  <br/> |<span data-ttu-id="ad688-115">**visXFormPinX**</span><span class="sxs-lookup"><span data-stu-id="ad688-115">**visXFormPinX**</span></span> <br/> |
   

