---
title: TxtWidth 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251270
localization_priority: Normal
ms.assetid: e2215c67-25fa-1d75-9cce-f126bb8760a1
description: 确定文本块的宽度。默认公式为：
ms.openlocfilehash: ecba66aaf1f7eeb6d16c6b0d4c6569aed051910f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781592"
---
# <a name="txtwidth-cell-text-transform-section"></a><span data-ttu-id="da843-104">TxtWidth 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="da843-104">TxtWidth Cell (Text Transform Section)</span></span>

<span data-ttu-id="da843-p102">确定文本块的宽度。默认公式为：</span><span class="sxs-lookup"><span data-stu-id="da843-p102">Determines the width of the text block. The default formula is:</span></span>
  
<span data-ttu-id="da843-107">= 宽度\*1</span><span class="sxs-lookup"><span data-stu-id="da843-107">= Width \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="da843-108">备注</span><span class="sxs-lookup"><span data-stu-id="da843-108">Remarks</span></span>

<span data-ttu-id="da843-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="da843-109">To get a reference to the TxtWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="da843-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="da843-110">Cell name:</span></span>  <br/> | <span data-ttu-id="da843-111">TxtWidth</span><span class="sxs-lookup"><span data-stu-id="da843-111">TxtWidth</span></span>  <br/> |
   
<span data-ttu-id="da843-112">若要从某个程序按索引获取对 TxtWidth 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="da843-112">To get a reference to the TxtWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="da843-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="da843-113">Section index:</span></span>  <br/> |<span data-ttu-id="da843-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="da843-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="da843-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="da843-115">Row index:</span></span>  <br/> |<span data-ttu-id="da843-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="da843-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="da843-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="da843-117">Cell index:</span></span>  <br/> |<span data-ttu-id="da843-118">**visXFormWidth**</span><span class="sxs-lookup"><span data-stu-id="da843-118">**visXFormWidth**</span></span> <br/> |
   

