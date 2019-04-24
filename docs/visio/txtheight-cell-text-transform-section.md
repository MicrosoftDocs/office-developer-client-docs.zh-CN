---
title: TxtHeight 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1025
localization_priority: Normal
ms.assetid: cfa3ecc6-61a8-506c-ba1d-b5e1f757d44f
description: 确定文本块的高度。 默认公式为：
ms.openlocfilehash: 8ad17cdf1deca6c4aa81f3388d7c112b4e179e2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334389"
---
# <a name="txtheight-cell-text-transform-section"></a><span data-ttu-id="e921e-104">TxtHeight 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="e921e-104">TxtHeight Cell (Text Transform Section)</span></span>

<span data-ttu-id="e921e-105">确定文本块的高度。</span><span class="sxs-lookup"><span data-stu-id="e921e-105">Determines the height of the text block.</span></span> <span data-ttu-id="e921e-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="e921e-106">The default formula is:</span></span>
  
<span data-ttu-id="e921e-107">= Height \* 1</span><span class="sxs-lookup"><span data-stu-id="e921e-107">= Height \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e921e-108">注解</span><span class="sxs-lookup"><span data-stu-id="e921e-108">Remarks</span></span>

<span data-ttu-id="e921e-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e921e-109">To get a reference to the TxtHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e921e-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e921e-110">Cell name:</span></span>  <br/> | <span data-ttu-id="e921e-111">TxtHeight</span><span class="sxs-lookup"><span data-stu-id="e921e-111">TxtHeight</span></span>  <br/> |
   
<span data-ttu-id="e921e-112">要从某个程序按索引获取对 TxtHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e921e-112">To get a reference to the TxtHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e921e-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e921e-113">Section index:</span></span>  <br/> |<span data-ttu-id="e921e-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e921e-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e921e-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="e921e-115">Row index:</span></span>  <br/> |<span data-ttu-id="e921e-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="e921e-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="e921e-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e921e-117">Cell index:</span></span>  <br/> |<span data-ttu-id="e921e-118">**visXFormHeight**</span><span class="sxs-lookup"><span data-stu-id="e921e-118">**visXFormHeight**</span></span> <br/> |
   

