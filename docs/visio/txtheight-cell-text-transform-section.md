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
description: 确定文本块的高度。默认公式为：
ms.openlocfilehash: e9495eef837a61fa9b7ecb2b242fdabc5df30080
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781572"
---
# <a name="txtheight-cell-text-transform-section"></a><span data-ttu-id="8f824-104">TxtHeight 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="8f824-104">TxtHeight Cell (Text Transform Section)</span></span>

<span data-ttu-id="8f824-p102">确定文本块的高度。默认公式为：</span><span class="sxs-lookup"><span data-stu-id="8f824-p102">Determines the height of the text block. The default formula is:</span></span>
  
<span data-ttu-id="8f824-107">= 高度\*1</span><span class="sxs-lookup"><span data-stu-id="8f824-107">= Height \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8f824-108">备注</span><span class="sxs-lookup"><span data-stu-id="8f824-108">Remarks</span></span>

<span data-ttu-id="8f824-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8f824-109">To get a reference to the TxtHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8f824-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8f824-110">Cell name:</span></span>  <br/> | <span data-ttu-id="8f824-111">TxtHeight</span><span class="sxs-lookup"><span data-stu-id="8f824-111">TxtHeight</span></span>  <br/> |
   
<span data-ttu-id="8f824-112">若要从某个程序按索引获取对 TxtHeight 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="8f824-112">To get a reference to the TxtHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8f824-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8f824-113">Section index:</span></span>  <br/> |<span data-ttu-id="8f824-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8f824-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8f824-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="8f824-115">Row index:</span></span>  <br/> |<span data-ttu-id="8f824-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="8f824-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="8f824-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8f824-117">Cell index:</span></span>  <br/> |<span data-ttu-id="8f824-118">**visXFormHeight**</span><span class="sxs-lookup"><span data-stu-id="8f824-118">**visXFormHeight**</span></span> <br/> |
   

