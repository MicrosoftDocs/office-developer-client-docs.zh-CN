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
description: 表示形状的旋转中心点 (旋转中心) 相对于其父级原点的 x 坐标。
ms.openlocfilehash: de12b379d5f345209a468298174634ff4f9cd639
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346751"
---
# <a name="pinx-cell-shape-transform-section"></a><span data-ttu-id="02737-103">PinX 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="02737-103">PinX Cell (Shape Transform Section)</span></span>

<span data-ttu-id="02737-104">表示形状的旋转中心点 (旋转中心) 相对于其父级原点的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="02737-104">Represents the  *x*  -coordinate of the shape's pin (center of rotation) in relation to the origin of its parent.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="02737-105">注解</span><span class="sxs-lookup"><span data-stu-id="02737-105">Remarks</span></span>

<span data-ttu-id="02737-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="02737-106">To get a reference to the PinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="02737-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="02737-107">Cell name:</span></span>  <br/> | <span data-ttu-id="02737-108">PinX</span><span class="sxs-lookup"><span data-stu-id="02737-108">PinX</span></span>  <br/> |
   
<span data-ttu-id="02737-109">要从某个程序按索引获取对 PinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="02737-109">To get a reference to the PinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="02737-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="02737-110">Section index:</span></span>  <br/> |<span data-ttu-id="02737-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="02737-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="02737-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="02737-112">Row index:</span></span>  <br/> |<span data-ttu-id="02737-113">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="02737-113">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="02737-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="02737-114">Cell index:</span></span>  <br/> |<span data-ttu-id="02737-115">**visXFormPinX**</span><span class="sxs-lookup"><span data-stu-id="02737-115">**visXFormPinX**</span></span> <br/> |
   

