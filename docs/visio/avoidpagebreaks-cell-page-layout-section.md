---
title: AvoidPageBreaks 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80000
localization_priority: Normal
ms.assetid: 7d2ec869-7ffa-3b41-8126-3f4889501e0c
description: 确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。
ms.openlocfilehash: 5ff5a31e26cc1ab9415eb69b76fc9f64ccd1ae7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416312"
---
# <a name="avoidpagebreaks-cell-page-layout-section"></a><span data-ttu-id="ac52e-103">AvoidPageBreaks 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="ac52e-103">AvoidPageBreaks Cell (Page Layout Section)</span></span>

<span data-ttu-id="ac52e-104">确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。</span><span class="sxs-lookup"><span data-stu-id="ac52e-104">Determines whether shapes can be placed over page breaks when the shapes are incrementally aligned, incrementally spaced, or both.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ac52e-105">备注</span><span class="sxs-lookup"><span data-stu-id="ac52e-105">Remarks</span></span>

<span data-ttu-id="ac52e-106">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AvoidPageBreaks 单元格的引用，请使用以下内容。</span><span class="sxs-lookup"><span data-stu-id="ac52e-106">To get a reference to the AvoidPageBreaks cell by name from another formula, or from a program by using the **CellsU** property, use the following.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac52e-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ac52e-107">Cell name:</span></span>  <br/> |<span data-ttu-id="ac52e-108">AvoidPageBreaks</span><span class="sxs-lookup"><span data-stu-id="ac52e-108">AvoidPageBreaks</span></span>  <br/> |
   
<span data-ttu-id="ac52e-109">若要从某个程序按索引获取对 AvoidPageBreaks 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ac52e-109">To get a reference to the AvoidPageBreaks cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac52e-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ac52e-110">Section index:</span></span>  <br/> |<span data-ttu-id="ac52e-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ac52e-111">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ac52e-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="ac52e-112">Row index:</span></span>  <br/> |<span data-ttu-id="ac52e-113">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="ac52e-113">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="ac52e-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ac52e-114">Cell index:</span></span>  <br/> |<span data-ttu-id="ac52e-115">**visPLOAvoidPageBreaks**</span><span class="sxs-lookup"><span data-stu-id="ac52e-115">**visPLOAvoidPageBreaks**</span></span> <br/> |
   

