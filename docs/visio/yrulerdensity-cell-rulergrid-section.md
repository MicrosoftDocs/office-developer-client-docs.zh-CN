---
title: YRulerDensity 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1215
localization_priority: Normal
ms.assetid: aebcd321-9d1c-e04e-7c85-3ec1ed851561
description: 指定页面标尺上的垂直细分线。
ms.openlocfilehash: c92c48f6c86fc794cf6f53a87fdb99e67a73b9f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406799"
---
# <a name="yrulerdensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="9d469-103">YRulerDensity 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="9d469-103">YRulerDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="9d469-104">指定页面标尺上的垂直细分线。</span><span class="sxs-lookup"><span data-stu-id="9d469-104">Specifies the vertical subdivisions on the ruler for the page.</span></span>
  
|<span data-ttu-id="9d469-105">**值**</span><span class="sxs-lookup"><span data-stu-id="9d469-105">**Value**</span></span>|<span data-ttu-id="9d469-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d469-106">**Description**</span></span>|<span data-ttu-id="9d469-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="9d469-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d469-108">0</span><span class="sxs-lookup"><span data-stu-id="9d469-108">0</span></span>  <br/> |<span data-ttu-id="9d469-109">Fixed</span><span class="sxs-lookup"><span data-stu-id="9d469-109">Fixed</span></span>  <br/> |<span data-ttu-id="9d469-110">**visRulerFixed**</span><span class="sxs-lookup"><span data-stu-id="9d469-110">**visRulerFixed**</span></span> <br/> |
|<span data-ttu-id="9d469-111">8 (&amp;H8)</span><span class="sxs-lookup"><span data-stu-id="9d469-111">8 (&amp;H8)</span></span>  <br/> |<span data-ttu-id="9d469-112">粗</span><span class="sxs-lookup"><span data-stu-id="9d469-112">Coarse</span></span>  <br/> |<span data-ttu-id="9d469-113">**visRulerCoarse**</span><span class="sxs-lookup"><span data-stu-id="9d469-113">**visRulerCoarse**</span></span> <br/> |
|<span data-ttu-id="9d469-114">16 (&amp;H10)</span><span class="sxs-lookup"><span data-stu-id="9d469-114">16 (&amp;H10)</span></span>  <br/> |<span data-ttu-id="9d469-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="9d469-115">Normal (Default)</span></span>  <br/> |<span data-ttu-id="9d469-116">**visRulerNormal**</span><span class="sxs-lookup"><span data-stu-id="9d469-116">**visRulerNormal**</span></span> <br/> |
|<span data-ttu-id="9d469-117">32 (&amp;H20)</span><span class="sxs-lookup"><span data-stu-id="9d469-117">32 (&amp;H20)</span></span>  <br/> |<span data-ttu-id="9d469-118">细化</span><span class="sxs-lookup"><span data-stu-id="9d469-118">Fine</span></span>  <br/> |<span data-ttu-id="9d469-119">**visRulerFine**</span><span class="sxs-lookup"><span data-stu-id="9d469-119">**visRulerFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9d469-120">说明</span><span class="sxs-lookup"><span data-stu-id="9d469-120">Remarks</span></span>

<span data-ttu-id="9d469-121">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "垂直**细分**" 选项。</span><span class="sxs-lookup"><span data-stu-id="9d469-121">This cell corresponds to the vertical **Subdivisions** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="9d469-122">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YRulerDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9d469-122">To get a reference to the YRulerDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9d469-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9d469-123">Cell name:</span></span>  <br/> |<span data-ttu-id="9d469-124">YRulerDensity</span><span class="sxs-lookup"><span data-stu-id="9d469-124">YRulerDensity</span></span>  <br/> |
   
<span data-ttu-id="9d469-125">若要从某个程序按索引获取对 YRulerDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9d469-125">To get a reference to the YRulerDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9d469-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9d469-126">Section index:</span></span>  <br/> |<span data-ttu-id="9d469-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9d469-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="9d469-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="9d469-128">Row index:</span></span>  <br/> |<span data-ttu-id="9d469-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="9d469-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="9d469-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9d469-130">Cell index:</span></span>  <br/> |<span data-ttu-id="9d469-131">**visYRulerDensity**</span><span class="sxs-lookup"><span data-stu-id="9d469-131">**visYRulerDensity**</span></span> <br/> |
   

