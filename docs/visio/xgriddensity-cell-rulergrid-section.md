---
title: XGridDensity 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1150
localization_priority: Normal
ms.assetid: db7b353f-4379-8865-1c35-36b89cf93257
description: 指定要使用的水平网格的类型。
ms.openlocfilehash: 107cde8e8b0d630a4dc4b43127412de2f6b0115d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781686"
---
# <a name="xgriddensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="75d3c-103">XGridDensity 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="75d3c-103">XGridDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="75d3c-104">指定要使用的水平网格的类型。</span><span class="sxs-lookup"><span data-stu-id="75d3c-104">Specifies the type of horizontal grid to use.</span></span>
  
|<span data-ttu-id="75d3c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="75d3c-105">**Value**</span></span>|<span data-ttu-id="75d3c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="75d3c-106">**Description**</span></span>|<span data-ttu-id="75d3c-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="75d3c-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75d3c-108">0</span><span class="sxs-lookup"><span data-stu-id="75d3c-108">0</span></span>  <br/> |<span data-ttu-id="75d3c-109">固定</span><span class="sxs-lookup"><span data-stu-id="75d3c-109">Fixed</span></span>  <br/> |<span data-ttu-id="75d3c-110">**visGridFixed**</span><span class="sxs-lookup"><span data-stu-id="75d3c-110">**visGridFixed**</span></span> <br/> |
|<span data-ttu-id="75d3c-111">2</span><span class="sxs-lookup"><span data-stu-id="75d3c-111">2</span></span>  <br/> |<span data-ttu-id="75d3c-112">粗糙</span><span class="sxs-lookup"><span data-stu-id="75d3c-112">Coarse</span></span>  <br/> |<span data-ttu-id="75d3c-113">**visGridCoarse**</span><span class="sxs-lookup"><span data-stu-id="75d3c-113">**visGridCoarse**</span></span> <br/> |
|<span data-ttu-id="75d3c-114">4</span><span class="sxs-lookup"><span data-stu-id="75d3c-114">4</span></span>  <br/> |<span data-ttu-id="75d3c-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="75d3c-115">Normal (default)</span></span>  <br/> |<span data-ttu-id="75d3c-116">**visGridNormal**</span><span class="sxs-lookup"><span data-stu-id="75d3c-116">**visGridNormal**</span></span> <br/> |
|<span data-ttu-id="75d3c-117">8</span><span class="sxs-lookup"><span data-stu-id="75d3c-117">8</span></span>  <br/> |<span data-ttu-id="75d3c-118">精细</span><span class="sxs-lookup"><span data-stu-id="75d3c-118">Fine</span></span>  <br/> |<span data-ttu-id="75d3c-119">**visGridFine**</span><span class="sxs-lookup"><span data-stu-id="75d3c-119">**visGridFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="75d3c-120">备注</span><span class="sxs-lookup"><span data-stu-id="75d3c-120">Remarks</span></span>

<span data-ttu-id="75d3c-121">此单元格对应于水平**网格间距**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="75d3c-121">This cell corresponds to the horizontal **Grid spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="75d3c-122">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XGridDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="75d3c-122">To get a reference to the XGridDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="75d3c-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="75d3c-123">Cell name:</span></span>  <br/> |<span data-ttu-id="75d3c-124">XGridDensity</span><span class="sxs-lookup"><span data-stu-id="75d3c-124">XGridDensity</span></span>  <br/> |
   
<span data-ttu-id="75d3c-125">若要从某个程序按索引获取对 XGridDensity 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="75d3c-125">To get a reference to the XGridDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="75d3c-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="75d3c-126">Section index:</span></span>  <br/> |<span data-ttu-id="75d3c-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="75d3c-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="75d3c-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="75d3c-128">Row index:</span></span>  <br/> |<span data-ttu-id="75d3c-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="75d3c-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="75d3c-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="75d3c-130">Cell index:</span></span>  <br/> |<span data-ttu-id="75d3c-131">**visXGridDensity**</span><span class="sxs-lookup"><span data-stu-id="75d3c-131">**visXGridDensity**</span></span> <br/> |
   

