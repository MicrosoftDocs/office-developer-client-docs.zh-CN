---
title: EnableGrid 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251642
localization_priority: Normal
ms.assetid: bfea4ef4-1b30-eb22-215d-3b9b73098da9
description: 确定在“配置布局”对话框中配置布局时应用程序是否根据内部不可见的页面网格排放形状。（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”。）
ms.openlocfilehash: 3371767343132219ebc38134b93afd1da46c7a45
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780174"
---
# <a name="enablegrid-cell-page-layout-section"></a><span data-ttu-id="49cb1-104">EnableGrid 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="49cb1-104">EnableGrid Cell (Page Layout Section)</span></span>

<span data-ttu-id="49cb1-p102">确定在 **“配置布局”** 对话框中配置布局时应用程序是否根据内部不可见的页面网格排放形状。（在 **“设计”** 选项卡上的 **“布局”** 组中，单击 **“重新布局页面”**，然后单击 **“其他布局选项”**。）</span><span class="sxs-lookup"><span data-stu-id="49cb1-p102">Determines whether the application lays out shapes based on an internal, invisible page grid when you configure the layout in the **Configure Layout** dialog box. (On the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**.)</span></span>
  
|<span data-ttu-id="49cb1-107">**值**</span><span class="sxs-lookup"><span data-stu-id="49cb1-107">**Value**</span></span>|<span data-ttu-id="49cb1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="49cb1-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="49cb1-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="49cb1-109">TRUE</span></span>  <br/> |<span data-ttu-id="49cb1-110">使用内部页网格。</span><span class="sxs-lookup"><span data-stu-id="49cb1-110">Use the internal page grid.</span></span>  <br/> |
|<span data-ttu-id="49cb1-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="49cb1-111">FALSE</span></span>  <br/> |<span data-ttu-id="49cb1-112">不使用内部页网格。</span><span class="sxs-lookup"><span data-stu-id="49cb1-112">Do not use the internal page grid.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="49cb1-113">注解</span><span class="sxs-lookup"><span data-stu-id="49cb1-113">Remarks</span></span>

<span data-ttu-id="49cb1-p103">可以使用 **“布局与排列间距”** 对话框中的 **“形状间的距离”** 和 **“平均形状大小”** 值创建此页面网格。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，单击 **“布局与排列”**，然后单击 **“间距”**。）</span><span class="sxs-lookup"><span data-stu-id="49cb1-p103">You create this page grid by using the **Space between shapes** and the **Average shape size** values in the **Layout and Routing Spacing** dialog box. (On the **Design** tab, click the **Page Setup** arrow, click **Layout and Routing**, and then click **Spacing**.)</span></span> 
  
<span data-ttu-id="49cb1-116">启用此功能后，应用程序会将每个可放置形状的中心点与内部页网格上的块的中心对齐。</span><span class="sxs-lookup"><span data-stu-id="49cb1-116">When you enable this feature, the application aligns each placeable shape's center point with the center of a block on the internal page grid.</span></span> 
  
<span data-ttu-id="49cb1-117">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 EnableGrid 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="49cb1-117">To get a reference to the EnableGrid cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="49cb1-118">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="49cb1-118">Cell name:</span></span>  <br/> |<span data-ttu-id="49cb1-119">EnableGrid</span><span class="sxs-lookup"><span data-stu-id="49cb1-119">EnableGrid</span></span>  <br/> |
   
<span data-ttu-id="49cb1-120">若要从某个程序按索引获取对 EnableGrid 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="49cb1-120">To get a reference to the EnableGrid cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="49cb1-121">内容索引：</span><span class="sxs-lookup"><span data-stu-id="49cb1-121">Section index:</span></span>  <br/> |<span data-ttu-id="49cb1-122">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="49cb1-122">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="49cb1-123">行索引：</span><span class="sxs-lookup"><span data-stu-id="49cb1-123">Row index:</span></span>  <br/> |<span data-ttu-id="49cb1-124">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="49cb1-124">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="49cb1-125">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="49cb1-125">Cell index:</span></span>  <br/> |<span data-ttu-id="49cb1-126">**visPLOEnableGrid**</span><span class="sxs-lookup"><span data-stu-id="49cb1-126">**visPLOEnableGrid**</span></span> <br/> |
   

