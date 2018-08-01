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
ms.openlocfilehash: ff052c5b254f9b49a97f5d362a4643e16a27b85d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779637"
---
# <a name="angle-cell-shape-transform-section"></a><span data-ttu-id="d8691-104">Angle 单元格（“Shape Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="d8691-104">Angle Cell (Shape Transform Section)</span></span>

<span data-ttu-id="d8691-p102">代表某一形状相对于其父级的当前旋转角度。确定一维形状的旋转角度的默认公式为：=ATAN2(EndY-BeginY,EndX-BeginX)。</span><span class="sxs-lookup"><span data-stu-id="d8691-p102">Represents the shape's current angle of rotation in relation to its parent. The default formula for determining the rotation angle of a 1-D shape is: =ATAN2(EndY-BeginY,EndX-BeginX).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d8691-107">注释</span><span class="sxs-lookup"><span data-stu-id="d8691-107">Remarks</span></span>

<span data-ttu-id="d8691-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Angle 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d8691-108">To get a reference to the Angle cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d8691-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d8691-109">Cell name:</span></span>  <br/> | <span data-ttu-id="d8691-110">Angle</span><span class="sxs-lookup"><span data-stu-id="d8691-110">Angle</span></span>  <br/> |
   
<span data-ttu-id="d8691-111">要从某个程序按索引获取对 Angle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d8691-111">To get a reference to the Angle cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d8691-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d8691-112">Section index:</span></span>  <br/> |<span data-ttu-id="d8691-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d8691-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d8691-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="d8691-114">Row index:</span></span>  <br/> |<span data-ttu-id="d8691-115">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="d8691-115">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="d8691-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d8691-116">Cell index:</span></span>  <br/> |<span data-ttu-id="d8691-117">**visXFormAngle**</span><span class="sxs-lookup"><span data-stu-id="d8691-117">**visXFormAngle**</span></span> <br/> |
   

