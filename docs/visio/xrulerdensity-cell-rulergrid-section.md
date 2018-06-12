---
title: XRulerDensity 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1165
localization_priority: Normal
ms.assetid: c11717c5-eb0e-e4fa-5a91-c62ecc048635
description: 指定页面标尺上的水平细分线。
ms.openlocfilehash: 633b2e54ca77216fd20ead00f047283c54f8164d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781682"
---
# <a name="xrulerdensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="9006e-103">XRulerDensity 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="9006e-103">XRulerDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="9006e-104">指定页面标尺上的水平细分线。</span><span class="sxs-lookup"><span data-stu-id="9006e-104">Specifies the horizontal subdivisions on the ruler for the page.</span></span>
  
|<span data-ttu-id="9006e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="9006e-105">**Value**</span></span>|<span data-ttu-id="9006e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="9006e-106">**Description**</span></span>|<span data-ttu-id="9006e-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="9006e-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9006e-108">0</span><span class="sxs-lookup"><span data-stu-id="9006e-108">0</span></span>  <br/> |<span data-ttu-id="9006e-109">固定</span><span class="sxs-lookup"><span data-stu-id="9006e-109">Fixed</span></span>  <br/> |<span data-ttu-id="9006e-110">**visRulerFixed**</span><span class="sxs-lookup"><span data-stu-id="9006e-110">**visRulerFixed**</span></span> <br/> |
|<span data-ttu-id="9006e-111">8 (&amp;H8)</span><span class="sxs-lookup"><span data-stu-id="9006e-111">8 (&amp;H8)</span></span>  <br/> |<span data-ttu-id="9006e-112">粗糙</span><span class="sxs-lookup"><span data-stu-id="9006e-112">Coarse</span></span>  <br/> |<span data-ttu-id="9006e-113">**visRulerCoarse**</span><span class="sxs-lookup"><span data-stu-id="9006e-113">**visRulerCoarse**</span></span> <br/> |
|<span data-ttu-id="9006e-114">16 (&amp;H10)</span><span class="sxs-lookup"><span data-stu-id="9006e-114">16 (&amp;H10)</span></span>  <br/> |<span data-ttu-id="9006e-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="9006e-115">Normal (Default)</span></span>  <br/> |<span data-ttu-id="9006e-116">**visRulerNormal**</span><span class="sxs-lookup"><span data-stu-id="9006e-116">**visRulerNormal**</span></span> <br/> |
|<span data-ttu-id="9006e-117">32 (&amp;H20)</span><span class="sxs-lookup"><span data-stu-id="9006e-117">32 (&amp;H20)</span></span>  <br/> |<span data-ttu-id="9006e-118">精细</span><span class="sxs-lookup"><span data-stu-id="9006e-118">Fine</span></span>  <br/> |<span data-ttu-id="9006e-119">**visRulerFine**</span><span class="sxs-lookup"><span data-stu-id="9006e-119">**visRulerFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9006e-120">备注</span><span class="sxs-lookup"><span data-stu-id="9006e-120">Remarks</span></span>

<span data-ttu-id="9006e-121">此单元格对应于中的水平**细分线**选项**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="9006e-121">This cell corresponds to the horizontal **Subdivisions** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="9006e-122">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XRulerDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9006e-122">To get a reference to the XRulerDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9006e-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9006e-123">Cell name:</span></span>  <br/> |<span data-ttu-id="9006e-124">XRulerDensity</span><span class="sxs-lookup"><span data-stu-id="9006e-124">XRulerDensity</span></span>  <br/> |
   
<span data-ttu-id="9006e-125">若要从某个程序按索引获取对 XRulerDensity 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="9006e-125">To get a reference to the XRulerDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9006e-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9006e-126">Section index:</span></span>  <br/> |<span data-ttu-id="9006e-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9006e-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="9006e-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="9006e-128">Row index:</span></span>  <br/> |<span data-ttu-id="9006e-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="9006e-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="9006e-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9006e-130">Cell index:</span></span>  <br/> |<span data-ttu-id="9006e-131">**visXRulerDensity**</span><span class="sxs-lookup"><span data-stu-id="9006e-131">**visXRulerDensity**</span></span> <br/> |
   

