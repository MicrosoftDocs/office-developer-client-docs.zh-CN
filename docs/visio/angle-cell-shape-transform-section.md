---
title: Angle 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251196
localization_priority: Normal
ms.assetid: d05a001c-9001-90d9-5028-f38b90acc53e
description: 代表某一形状相对于其父级的当前旋转角度。确定一维形状的旋转角度的默认公式为：=ATAN2(EndY-BeginY,EndX-BeginX)。
ms.openlocfilehash: 85f64c6111b492940d278a5558508a2dea6b1e1a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414548"
---
# <a name="angle-cell-shape-transform-section"></a><span data-ttu-id="1a818-104">Angle 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="1a818-104">Angle Cell (Shape Transform Section)</span></span>

<span data-ttu-id="1a818-p102">代表某一形状相对于其父级的当前旋转角度。确定一维形状的旋转角度的默认公式为：=ATAN2(EndY-BeginY,EndX-BeginX)。</span><span class="sxs-lookup"><span data-stu-id="1a818-p102">Represents the shape's current angle of rotation in relation to its parent. The default formula for determining the rotation angle of a 1-D shape is: =ATAN2(EndY-BeginY,EndX-BeginX).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1a818-107">说明</span><span class="sxs-lookup"><span data-stu-id="1a818-107">Remarks</span></span>

<span data-ttu-id="1a818-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Angle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1a818-108">To get a reference to the Angle cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1a818-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1a818-109">Cell name:</span></span>  <br/> | <span data-ttu-id="1a818-110">角</span><span class="sxs-lookup"><span data-stu-id="1a818-110">Angle</span></span>  <br/> |
   
<span data-ttu-id="1a818-111">要从某个程序按索引获取对 Angle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1a818-111">To get a reference to the Angle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1a818-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1a818-112">Section index:</span></span>  <br/> |<span data-ttu-id="1a818-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1a818-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="1a818-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="1a818-114">Row index:</span></span>  <br/> |<span data-ttu-id="1a818-115">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="1a818-115">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="1a818-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1a818-116">Cell index:</span></span>  <br/> |<span data-ttu-id="1a818-117">**visXFormAngle**</span><span class="sxs-lookup"><span data-stu-id="1a818-117">**visXFormAngle**</span></span> <br/> |
   

