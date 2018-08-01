---
title: TxtLocPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251275
localization_priority: Normal
ms.assetid: cbfc4e91-10d1-d50e-3e8a-f269f7123276
description: 确定 x-文本块的相对于原点的文本块的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: 6eb48532bb19bce5b0d22ed2cd0997014721df88
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781559"
---
# <a name="txtlocpinx-cell-text-transform-section"></a><span data-ttu-id="ae4d2-104">TxtLocPinX 单元格（“Text Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="ae4d2-104">TxtLocPinX Cell (Text Transform Section)</span></span>

<span data-ttu-id="ae4d2-105">确定*x* -文本块的相对于原点的文本块的旋转中心的坐标。</span><span class="sxs-lookup"><span data-stu-id="ae4d2-105">Determines the  *x*  -coordinate of the text block's center of rotation in relation to the origin of the text block.</span></span> <span data-ttu-id="ae4d2-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-106">The default formula is:</span></span> 
  
<span data-ttu-id="ae4d2-107">= TxtWidth \* 0.5</span><span class="sxs-lookup"><span data-stu-id="ae4d2-107">= TxtWidth \* 0.5</span></span>
  
<span data-ttu-id="ae4d2-108">该公式计算文本块的水平中心。</span><span class="sxs-lookup"><span data-stu-id="ae4d2-108">This formula evaluates to the horizontal center of the text block.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ae4d2-109">注释</span><span class="sxs-lookup"><span data-stu-id="ae4d2-109">Remarks</span></span>

<span data-ttu-id="ae4d2-110">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtLocPinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-110">To get a reference to the TxtLocPinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ae4d2-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-111">Cell name:</span></span>  <br/> | <span data-ttu-id="ae4d2-112">TxtLocPinX</span><span class="sxs-lookup"><span data-stu-id="ae4d2-112">TxtLocPinX</span></span>  <br/> |
   
<span data-ttu-id="ae4d2-113">要从某个程序按索引获取对 TxtLocPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-113">To get a reference to the TxtLocPinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ae4d2-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-114">Section index:</span></span>  <br/> |<span data-ttu-id="ae4d2-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ae4d2-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ae4d2-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-116">Row index:</span></span>  <br/> |<span data-ttu-id="ae4d2-117">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="ae4d2-117">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="ae4d2-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ae4d2-118">Cell index:</span></span>  <br/> |<span data-ttu-id="ae4d2-119">**visXFormLocPinX**</span><span class="sxs-lookup"><span data-stu-id="ae4d2-119">**visXFormLocPinX**</span></span> <br/> |
   

