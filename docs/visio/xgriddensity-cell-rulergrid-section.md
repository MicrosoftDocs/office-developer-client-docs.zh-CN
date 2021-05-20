---
title: 'XGridDensity Cell (Ruler &amp; Grid Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1150
localization_priority: Normal
ms.assetid: db7b353f-4379-8865-1c35-36b89cf93257
description: 指定要使用的水平网格的类型。
ms.openlocfilehash: 5ebd172e56a66bfb39bd9bfa20967bb6b52c5aa2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436039"
---
# <a name="xgriddensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="e1ebb-103">XGridDensity Cell (Ruler &amp; Grid Section) </span><span class="sxs-lookup"><span data-stu-id="e1ebb-103">XGridDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="e1ebb-104">指定要使用的水平网格的类型。</span><span class="sxs-lookup"><span data-stu-id="e1ebb-104">Specifies the type of horizontal grid to use.</span></span>
  
|<span data-ttu-id="e1ebb-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-105">**Value**</span></span>|<span data-ttu-id="e1ebb-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-106">**Description**</span></span>|<span data-ttu-id="e1ebb-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1ebb-108">0</span><span class="sxs-lookup"><span data-stu-id="e1ebb-108">0</span></span>  <br/> |<span data-ttu-id="e1ebb-109">Fixed</span><span class="sxs-lookup"><span data-stu-id="e1ebb-109">Fixed</span></span>  <br/> |<span data-ttu-id="e1ebb-110">**visGridFixed**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-110">**visGridFixed**</span></span> <br/> |
|<span data-ttu-id="e1ebb-111">2</span><span class="sxs-lookup"><span data-stu-id="e1ebb-111">2</span></span>  <br/> |<span data-ttu-id="e1ebb-112">粗细</span><span class="sxs-lookup"><span data-stu-id="e1ebb-112">Coarse</span></span>  <br/> |<span data-ttu-id="e1ebb-113">**visGridCoarse**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-113">**visGridCoarse**</span></span> <br/> |
|<span data-ttu-id="e1ebb-114">4 </span><span class="sxs-lookup"><span data-stu-id="e1ebb-114">4</span></span>  <br/> |<span data-ttu-id="e1ebb-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="e1ebb-115">Normal (default)</span></span>  <br/> |<span data-ttu-id="e1ebb-116">**visGridNormal**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-116">**visGridNormal**</span></span> <br/> |
|<span data-ttu-id="e1ebb-117">8 </span><span class="sxs-lookup"><span data-stu-id="e1ebb-117">8</span></span>  <br/> |<span data-ttu-id="e1ebb-118">精细</span><span class="sxs-lookup"><span data-stu-id="e1ebb-118">Fine</span></span>  <br/> |<span data-ttu-id="e1ebb-119">**visGridFine**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-119">**visGridFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1ebb-120">备注</span><span class="sxs-lookup"><span data-stu-id="e1ebb-120">Remarks</span></span>

<span data-ttu-id="e1ebb-121">此单元格对应于"视图"选项卡上"标尺网格"对话框中 (网格间距"选项，单击"显示") 。  **&amp;**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-121">This cell corresponds to the horizontal **Grid spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="e1ebb-122">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-122">To get a reference to the XGridDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1ebb-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-123">Cell name:</span></span>  <br/> |<span data-ttu-id="e1ebb-124">XGridDensity</span><span class="sxs-lookup"><span data-stu-id="e1ebb-124">XGridDensity</span></span>  <br/> |
   
<span data-ttu-id="e1ebb-125">若要从某个程序按索引获取对 XGridDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-125">To get a reference to the XGridDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1ebb-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-126">Section index:</span></span>  <br/> |<span data-ttu-id="e1ebb-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="e1ebb-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-128">Row index:</span></span>  <br/> |<span data-ttu-id="e1ebb-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="e1ebb-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e1ebb-130">Cell index:</span></span>  <br/> |<span data-ttu-id="e1ebb-131">**visXGridDensity**</span><span class="sxs-lookup"><span data-stu-id="e1ebb-131">**visXGridDensity**</span></span> <br/> |
   

