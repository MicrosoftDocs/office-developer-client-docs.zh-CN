---
title: E 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251761
localization_priority: Normal
ms.assetid: bc0154b1-6930-1fe0-655c-05eab2d60230
description: 包含非均匀有理 B 样条 (NURBS) 公式。
ms.openlocfilehash: 5c9b3cbf96e2a218a8ed790d3a5615843360c95e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423564"
---
# <a name="e-cell-geometry-section"></a><span data-ttu-id="3f142-103">E 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="3f142-103">E Cell (Geometry Section)</span></span>

<span data-ttu-id="3f142-104">包含非均匀有理 B 样条 (NURBS) 公式。</span><span class="sxs-lookup"><span data-stu-id="3f142-104">Contains a nonuniform rational B-spline (NURBS) formula.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3f142-105">备注</span><span class="sxs-lookup"><span data-stu-id="3f142-105">Remarks</span></span>

<span data-ttu-id="3f142-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 E 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3f142-106">To get a reference to the E cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3f142-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3f142-107">Cell name:</span></span>  <br/> | <span data-ttu-id="3f142-108">Geometry  *i*  .E  *j*            其中  *i*  和  *j*  = <1>、2、3...</span><span class="sxs-lookup"><span data-stu-id="3f142-108">Geometry  *i*  .E  *j*            where  *i*  and  *j*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="3f142-109">要从某个程序按索引获取对 E 单元格，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3f142-109">To get a reference to the E cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3f142-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3f142-110">Section index:</span></span>  <br/> |<span data-ttu-id="3f142-111">**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="3f142-111">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="3f142-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="3f142-112">Row index:</span></span>  <br/> |<span data-ttu-id="3f142-113">**visRowVertex**  +  *j* 其中 *j* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="3f142-113">**visRowVertex** +  *j*            where  *j*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="3f142-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3f142-114">Cell index:</span></span>  <br/> |<span data-ttu-id="3f142-115">**visNURBSData**</span><span class="sxs-lookup"><span data-stu-id="3f142-115">**visNURBSData**</span></span> <br/> |
   

