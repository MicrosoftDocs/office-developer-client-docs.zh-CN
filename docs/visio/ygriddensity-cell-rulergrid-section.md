---
title: YGridDensity 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251363
localization_priority: Normal
ms.assetid: 3ea2b3c7-0c69-a9f2-379f-8daa0c665810
description: 指定要使用的垂直网格的类型。
ms.openlocfilehash: 4e0d1b1dc6f3da95b9328342e0398313b6c85eb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781716"
---
# <a name="ygriddensity-cell-ruler-amp-grid-section"></a><span data-ttu-id="10c0d-103">YGridDensity 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="10c0d-103">YGridDensity Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="10c0d-104">指定要使用的垂直网格的类型。</span><span class="sxs-lookup"><span data-stu-id="10c0d-104">Specifies the type of vertical grid to use.</span></span>
  
|<span data-ttu-id="10c0d-105">**值**</span><span class="sxs-lookup"><span data-stu-id="10c0d-105">**Value**</span></span>|<span data-ttu-id="10c0d-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="10c0d-106">**Description**</span></span>|<span data-ttu-id="10c0d-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="10c0d-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10c0d-108">0</span><span class="sxs-lookup"><span data-stu-id="10c0d-108">0</span></span>  <br/> |<span data-ttu-id="10c0d-109">固定</span><span class="sxs-lookup"><span data-stu-id="10c0d-109">Fixed</span></span>  <br/> |<span data-ttu-id="10c0d-110">**visGridFixed**</span><span class="sxs-lookup"><span data-stu-id="10c0d-110">**visGridFixed**</span></span> <br/> |
|<span data-ttu-id="10c0d-111">2</span><span class="sxs-lookup"><span data-stu-id="10c0d-111">2</span></span>  <br/> |<span data-ttu-id="10c0d-112">粗糙</span><span class="sxs-lookup"><span data-stu-id="10c0d-112">Coarse</span></span>  <br/> |<span data-ttu-id="10c0d-113">**visGridCoarse**</span><span class="sxs-lookup"><span data-stu-id="10c0d-113">**visGridCoarse**</span></span> <br/> |
|<span data-ttu-id="10c0d-114">4</span><span class="sxs-lookup"><span data-stu-id="10c0d-114">4</span></span>  <br/> |<span data-ttu-id="10c0d-115">标准（默认）</span><span class="sxs-lookup"><span data-stu-id="10c0d-115">Normal (default)</span></span>  <br/> |<span data-ttu-id="10c0d-116">**visGridNormal**</span><span class="sxs-lookup"><span data-stu-id="10c0d-116">**visGridNormal**</span></span> <br/> |
|<span data-ttu-id="10c0d-117">8</span><span class="sxs-lookup"><span data-stu-id="10c0d-117">8</span></span>  <br/> |<span data-ttu-id="10c0d-118">精细</span><span class="sxs-lookup"><span data-stu-id="10c0d-118">Fine</span></span>  <br/> |<span data-ttu-id="10c0d-119">**visGridFine**</span><span class="sxs-lookup"><span data-stu-id="10c0d-119">**visGridFine**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="10c0d-120">备注</span><span class="sxs-lookup"><span data-stu-id="10c0d-120">Remarks</span></span>

<span data-ttu-id="10c0d-121">此单元格对应于垂直**网格间距**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="10c0d-121">This cell corresponds to the vertical **Grid spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="10c0d-122">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 YGridDensity 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="10c0d-122">To get a reference to the YGridDensity cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="10c0d-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="10c0d-123">Cell name:</span></span>  <br/> |<span data-ttu-id="10c0d-124">YGridDensity</span><span class="sxs-lookup"><span data-stu-id="10c0d-124">YGridDensity</span></span>  <br/> |
   
<span data-ttu-id="10c0d-125">若要从某个程序按索引获取对 YGridDensity 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="10c0d-125">To get a reference to the YGridDensity cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="10c0d-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="10c0d-126">Section index:</span></span>  <br/> |<span data-ttu-id="10c0d-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="10c0d-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="10c0d-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="10c0d-128">Row index:</span></span>  <br/> |<span data-ttu-id="10c0d-129">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="10c0d-129">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="10c0d-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="10c0d-130">Cell index:</span></span>  <br/> |<span data-ttu-id="10c0d-131">**visYGridDensity**</span><span class="sxs-lookup"><span data-stu-id="10c0d-131">**visYGridDensity**</span></span> <br/> |
   
