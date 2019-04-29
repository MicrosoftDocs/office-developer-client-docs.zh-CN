---
title: OnPage 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033793
localization_priority: Normal
ms.assetid: 4015506a-e24a-0276-c854-7791a7019067
description: 指示是否将绘图打印到指定数量的打印纸上。
ms.openlocfilehash: 61d45a5bffdbb1afd5db9c608f80bc4f797f5191
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439602"
---
# <a name="onpage-cell-print-properties-section"></a><span data-ttu-id="6a52e-103">OnPage 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="6a52e-103">OnPage Cell (Print Properties Section)</span></span>

<span data-ttu-id="6a52e-104">指示是否将绘图打印到指定数量的打印纸上。</span><span class="sxs-lookup"><span data-stu-id="6a52e-104">Indicates whether the drawing is printed on a specific number of printer pages.</span></span> 
  
|<span data-ttu-id="6a52e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6a52e-105">**Value**</span></span>|<span data-ttu-id="6a52e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a52e-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a52e-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="6a52e-107">TRUE</span></span>  <br/> |<span data-ttu-id="6a52e-108">使绘图页与定义的打印机页面的数量相匹配。</span><span class="sxs-lookup"><span data-stu-id="6a52e-108">Fit the drawing page to a defined number of printer pages.</span></span>  <br/> |
|<span data-ttu-id="6a52e-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="6a52e-109">FALSE</span></span>  <br/> |<span data-ttu-id="6a52e-110">不调整绘图页的大小以使其适合指定数量的打印纸（默认值）。</span><span class="sxs-lookup"><span data-stu-id="6a52e-110">Do not fit the drawing page to a defined number of printer pages (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a52e-111">说明</span><span class="sxs-lookup"><span data-stu-id="6a52e-111">Remarks</span></span>

<span data-ttu-id="6a52e-p101">如果 OnPage 单元格设置为 TRUE，则 Microsoft Visio 将使用 PagesX 单元格和 PagesY 单元格来确定适合于该绘图的打印页的数目。ScaleX 单元格和 ScaleY 单元格中的值将被忽略。可以将此设置视为“自动缩放”设置。</span><span class="sxs-lookup"><span data-stu-id="6a52e-p101">If the OnPage cell is set to TRUE, Microsoft Visio uses the PagesX and PagesY cells to determine the number of printer pages on which to fit the drawing. Values in the ScaleX and ScaleY cells are ignored. This can be considered an "autoscale" setting.</span></span>
  
<span data-ttu-id="6a52e-115">此值对应于 "**页面设置**" 对话框 (在 "**设计**" 选项卡上, 单击 "**页面设置**" 箭头) 中 "**打印设置**" 选项卡上的 "**填充到**" 选项。</span><span class="sxs-lookup"><span data-stu-id="6a52e-115">This value corresponds to the **Fit to** option on the **Print Setup** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow) .</span></span> 
  
<span data-ttu-id="6a52e-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 OnPage 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6a52e-116">To get a reference to the OnPage cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a52e-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6a52e-117">Cell name:</span></span>  <br/> |<span data-ttu-id="6a52e-118">OnPage</span><span class="sxs-lookup"><span data-stu-id="6a52e-118">OnPage</span></span>  <br/> |
   
<span data-ttu-id="6a52e-119">若要从某个程序按索引获取对 OnPage 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6a52e-119">To get a reference to the OnPage cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a52e-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6a52e-120">Section index:</span></span>  <br/> |<span data-ttu-id="6a52e-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6a52e-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="6a52e-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="6a52e-122">Row index:</span></span>  <br/> |<span data-ttu-id="6a52e-123">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="6a52e-123">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="6a52e-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6a52e-124">Cell index:</span></span>  <br/> |<span data-ttu-id="6a52e-125">**visPrintPropertiesOnPage**</span><span class="sxs-lookup"><span data-stu-id="6a52e-125">**visPrintPropertiesOnPage**</span></span> <br/> |
   

