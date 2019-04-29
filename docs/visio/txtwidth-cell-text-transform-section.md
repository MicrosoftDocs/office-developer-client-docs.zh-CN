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
description: 确定文本块的宽度。 默认公式为：
ms.openlocfilehash: 806307166035ebc2f8e20e7025d5ecb03c4d6e79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426091"
---
# <a name="txtwidth-cell-text-transform-section"></a><span data-ttu-id="b0bc7-104">TxtWidth 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="b0bc7-104">TxtWidth Cell (Text Transform Section)</span></span>

<span data-ttu-id="b0bc7-105">确定文本块的宽度。</span><span class="sxs-lookup"><span data-stu-id="b0bc7-105">Determines the width of the text block.</span></span> <span data-ttu-id="b0bc7-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-106">The default formula is:</span></span>
  
<span data-ttu-id="b0bc7-107">= Width \* 1</span><span class="sxs-lookup"><span data-stu-id="b0bc7-107">= Width \* 1</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b0bc7-108">说明</span><span class="sxs-lookup"><span data-stu-id="b0bc7-108">Remarks</span></span>

<span data-ttu-id="b0bc7-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-109">To get a reference to the TxtWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b0bc7-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-110">Cell name:</span></span>  <br/> | <span data-ttu-id="b0bc7-111">TxtWidth</span><span class="sxs-lookup"><span data-stu-id="b0bc7-111">TxtWidth</span></span>  <br/> |
   
<span data-ttu-id="b0bc7-112">要从某个程序按索引获取对 TxtWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-112">To get a reference to the TxtWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b0bc7-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-113">Section index:</span></span>  <br/> |<span data-ttu-id="b0bc7-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b0bc7-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b0bc7-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-115">Row index:</span></span>  <br/> |<span data-ttu-id="b0bc7-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="b0bc7-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="b0bc7-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b0bc7-117">Cell index:</span></span>  <br/> |<span data-ttu-id="b0bc7-118">**visXFormWidth**</span><span class="sxs-lookup"><span data-stu-id="b0bc7-118">**visXFormWidth**</span></span> <br/> |
   

