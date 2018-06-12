---
title: YRulerDensity 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1215
localization_priority: Normal
ms.assetid: aebcd321-9d1c-e04e-7c85-3ec1ed851561
description: 指定页面标尺上的垂直细分线。
ms.openlocfilehash: 4b5dcba7a5cb1a588f742b1c2ea6b430cb2af12c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781714"
---
# <a name="yrulerdensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="b8df7-103">YRulerDensity 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="b8df7-103">YRulerDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="b8df7-104">指定页面标尺上的垂直细分线。</span><span class="sxs-lookup"><span data-stu-id="b8df7-104">Specifies the vertical subdivisions on the ruler for the page.</span></span>
  
|<span data-ttu-id="b8df7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b8df7-105">**Value**</span></span>|<span data-ttu-id="b8df7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8df7-106">**Description**</span></span>|<span data-ttu-id="b8df7-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="b8df7-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8df7-108">0</span><span class="sxs-lookup"><span data-stu-id="b8df7-108">0</span></span>  <br/> |<span data-ttu-id="b8df7-109">固定</span><span class="sxs-lookup"><span data-stu-id="b8df7-109">Fixed</span></span>  <br/> |<span data-ttu-id="b8df7-110">**visRulerFixed**</span><span class="sxs-lookup"><span data-stu-id="b8df7-110">**visRulerFixed**</span></span> <br/> |
|<span data-ttu-id="b8df7-111">8 (&amp;H8)</span><span class="sxs-lookup"><span data-stu-id="b8df7-111">8 (&amp;H8)</span></span>  <br/> |<span data-ttu-id="b8df7-112">粗糙</span><span class="sxs-lookup"><span data-stu-id="b8df7-112">Coarse</span></span>  <br/> |<span data-ttu-id="b8df7-113">**visRulerCoarse**</span><span class="sxs-lookup"><span data-stu-id="b8df7-113">**visRulerCoarse**</span></span> <br/> |
|<span data-ttu-id="b8df7-114">16 (&amp;H10)</span><span class="sxs-lookup"><span data-stu-id="b8df7-114">16 (&amp;H10)</span></span>  <br/> |<span data-ttu-id="b8df7-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="b8df7-115">Normal (Default)</span></span>  <br/> |<span data-ttu-id="b8df7-116">**visRulerNormal**</span><span class="sxs-lookup"><span data-stu-id="b8df7-116">**visRulerNormal**</span></span> <br/> |
|<span data-ttu-id="b8df7-117">32 (&amp;H20)</span><span class="sxs-lookup"><span data-stu-id="b8df7-117">32 (&amp;H20)</span></span>  <br/> |<span data-ttu-id="b8df7-118">精细</span><span class="sxs-lookup"><span data-stu-id="b8df7-118">Fine</span></span>  <br/> |<span data-ttu-id="b8df7-119">**visRulerFine**</span><span class="sxs-lookup"><span data-stu-id="b8df7-119">**visRulerFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b8df7-120">备注</span><span class="sxs-lookup"><span data-stu-id="b8df7-120">Remarks</span></span>

<span data-ttu-id="b8df7-121">此单元格对应于在垂直**细分线**选项**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="b8df7-121">This cell corresponds to the vertical **Subdivisions** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="b8df7-122">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 YRulerDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b8df7-122">To get a reference to the YRulerDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b8df7-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b8df7-123">Cell name:</span></span>  <br/> |<span data-ttu-id="b8df7-124">YRulerDensity</span><span class="sxs-lookup"><span data-stu-id="b8df7-124">YRulerDensity</span></span>  <br/> |
   
<span data-ttu-id="b8df7-125">若要从某个程序按索引获取对 YRulerDensity 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="b8df7-125">To get a reference to the YRulerDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b8df7-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b8df7-126">Section index:</span></span>  <br/> |<span data-ttu-id="b8df7-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b8df7-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="b8df7-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="b8df7-128">Row index:</span></span>  <br/> |<span data-ttu-id="b8df7-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="b8df7-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="b8df7-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b8df7-130">Cell index:</span></span>  <br/> |<span data-ttu-id="b8df7-131">**visYRulerDensity**</span><span class="sxs-lookup"><span data-stu-id="b8df7-131">**visYRulerDensity**</span></span> <br/> |
   

