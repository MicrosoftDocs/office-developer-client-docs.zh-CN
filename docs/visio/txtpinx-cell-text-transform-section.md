---
title: TxtPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1040
localization_priority: Normal
ms.assetid: d0c0fe52-6a9e-e40e-394e-83a851db55a4
description: 确定 x-文本块的相对于原点形状的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: df103557d103dbde7e4a1c8d67cabe37a0af9311
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781570"
---
# <a name="txtpinx-cell-text-transform-section"></a><span data-ttu-id="765af-104">TxtPinX 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="765af-104">TxtPinX Cell (Text Transform Section)</span></span>

<span data-ttu-id="765af-105">确定*x* -文本块的相对于原点形状的旋转中心的坐标。</span><span class="sxs-lookup"><span data-stu-id="765af-105">Determines the  *x*  -coordinate of the text block's center of rotation in relation to the origin of the shape.</span></span> <span data-ttu-id="765af-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="765af-106">The default formula is:</span></span> 
  
<span data-ttu-id="765af-107">= 宽度\*0.5</span><span class="sxs-lookup"><span data-stu-id="765af-107">= Width \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="765af-108">备注</span><span class="sxs-lookup"><span data-stu-id="765af-108">Remarks</span></span>

<span data-ttu-id="765af-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtPinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="765af-109">To get a reference to the TxtPinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="765af-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="765af-110">Cell name:</span></span>  <br/> | <span data-ttu-id="765af-111">TxtPinX</span><span class="sxs-lookup"><span data-stu-id="765af-111">TxtPinX</span></span>  <br/> |
   
<span data-ttu-id="765af-112">若要从某个程序按索引获取对 TxtPinX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="765af-112">To get a reference to the TxtPinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="765af-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="765af-113">Section index:</span></span>  <br/> |<span data-ttu-id="765af-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="765af-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="765af-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="765af-115">Row index:</span></span>  <br/> |<span data-ttu-id="765af-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="765af-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="765af-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="765af-117">Cell index:</span></span>  <br/> |<span data-ttu-id="765af-118">**visXFormPinX**</span><span class="sxs-lookup"><span data-stu-id="765af-118">**visXFormPinX**</span></span> <br/> |
   

