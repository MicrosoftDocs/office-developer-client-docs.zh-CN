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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409305"
---
# <a name="txtheight-cell-text-transform-section"></a><span data-ttu-id="cfaab-104">TxtHeight 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="cfaab-104">TxtHeight Cell (Text Transform Section)</span></span>

<span data-ttu-id="cfaab-105">确定文本块的高度。</span><span class="sxs-lookup"><span data-stu-id="cfaab-105">Determines the height of the text block.</span></span> <span data-ttu-id="cfaab-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="cfaab-106">The default formula is:</span></span>
  
<span data-ttu-id="cfaab-107">= Height \* 1</span><span class="sxs-lookup"><span data-stu-id="cfaab-107">= Height \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cfaab-108">说明</span><span class="sxs-lookup"><span data-stu-id="cfaab-108">Remarks</span></span>

<span data-ttu-id="cfaab-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cfaab-109">To get a reference to the TxtHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cfaab-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cfaab-110">Cell name:</span></span>  <br/> | <span data-ttu-id="cfaab-111">TxtHeight</span><span class="sxs-lookup"><span data-stu-id="cfaab-111">TxtHeight</span></span>  <br/> |
   
<span data-ttu-id="cfaab-112">要从某个程序按索引获取对 TxtHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cfaab-112">To get a reference to the TxtHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cfaab-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cfaab-113">Section index:</span></span>  <br/> |<span data-ttu-id="cfaab-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cfaab-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="cfaab-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="cfaab-115">Row index:</span></span>  <br/> |<span data-ttu-id="cfaab-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="cfaab-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="cfaab-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cfaab-117">Cell index:</span></span>  <br/> |<span data-ttu-id="cfaab-118">**visXFormHeight**</span><span class="sxs-lookup"><span data-stu-id="cfaab-118">**visXFormHeight**</span></span> <br/> |
   

