---
title: XGridDensity 单元格 ( &amp; "标尺网格" 部分)
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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328980"
---
# <a name="xgriddensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="bb2c2-103">XGridDensity 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="bb2c2-103">XGridDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="bb2c2-104">指定要使用的水平网格的类型。</span><span class="sxs-lookup"><span data-stu-id="bb2c2-104">Specifies the type of horizontal grid to use.</span></span>
  
|<span data-ttu-id="bb2c2-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-105">**Value**</span></span>|<span data-ttu-id="bb2c2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-106">**Description**</span></span>|<span data-ttu-id="bb2c2-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb2c2-108">0</span><span class="sxs-lookup"><span data-stu-id="bb2c2-108">0</span></span>  <br/> |<span data-ttu-id="bb2c2-109">Fixed</span><span class="sxs-lookup"><span data-stu-id="bb2c2-109">Fixed</span></span>  <br/> |<span data-ttu-id="bb2c2-110">**visGridFixed**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-110">**visGridFixed**</span></span> <br/> |
|<span data-ttu-id="bb2c2-111">双面</span><span class="sxs-lookup"><span data-stu-id="bb2c2-111">2</span></span>  <br/> |<span data-ttu-id="bb2c2-112">粗</span><span class="sxs-lookup"><span data-stu-id="bb2c2-112">Coarse</span></span>  <br/> |<span data-ttu-id="bb2c2-113">**visGridCoarse**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-113">**visGridCoarse**</span></span> <br/> |
|<span data-ttu-id="bb2c2-114">4</span><span class="sxs-lookup"><span data-stu-id="bb2c2-114">4</span></span>  <br/> |<span data-ttu-id="bb2c2-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="bb2c2-115">Normal (default)</span></span>  <br/> |<span data-ttu-id="bb2c2-116">**visGridNormal**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-116">**visGridNormal**</span></span> <br/> |
|<span data-ttu-id="bb2c2-117">utf-8</span><span class="sxs-lookup"><span data-stu-id="bb2c2-117">8</span></span>  <br/> |<span data-ttu-id="bb2c2-118">细化</span><span class="sxs-lookup"><span data-stu-id="bb2c2-118">Fine</span></span>  <br/> |<span data-ttu-id="bb2c2-119">**visGridFine**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-119">**visGridFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb2c2-120">注解</span><span class="sxs-lookup"><span data-stu-id="bb2c2-120">Remarks</span></span>

<span data-ttu-id="bb2c2-121">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**网格间距**" 选项。</span><span class="sxs-lookup"><span data-stu-id="bb2c2-121">This cell corresponds to the horizontal **Grid spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="bb2c2-122">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-122">To get a reference to the XGridDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb2c2-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-123">Cell name:</span></span>  <br/> |<span data-ttu-id="bb2c2-124">XGridDensity</span><span class="sxs-lookup"><span data-stu-id="bb2c2-124">XGridDensity</span></span>  <br/> |
   
<span data-ttu-id="bb2c2-125">若要从某个程序按索引获取对 XGridDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-125">To get a reference to the XGridDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb2c2-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-126">Section index:</span></span>  <br/> |<span data-ttu-id="bb2c2-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="bb2c2-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-128">Row index:</span></span>  <br/> |<span data-ttu-id="bb2c2-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="bb2c2-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bb2c2-130">Cell index:</span></span>  <br/> |<span data-ttu-id="bb2c2-131">**visXGridDensity**</span><span class="sxs-lookup"><span data-stu-id="bb2c2-131">**visXGridDensity**</span></span> <br/> |
   

