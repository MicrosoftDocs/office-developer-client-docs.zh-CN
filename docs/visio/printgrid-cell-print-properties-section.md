---
title: PrintGrid 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033794
localization_priority: Normal
ms.assetid: 0504ff7f-2274-7ae3-1f4b-a3d890dbd79a
description: 指定在打印文档页面时是否打印网格。
ms.openlocfilehash: 9b98999cd02fa6a47ec8564bbd7337ecf8637306
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433204"
---
# <a name="printgrid-cell-print-properties-section"></a><span data-ttu-id="42e29-103">PrintGrid 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="42e29-103">PrintGrid Cell (Print Properties Section)</span></span>

<span data-ttu-id="42e29-104">指定在打印文档页面时是否打印网格。</span><span class="sxs-lookup"><span data-stu-id="42e29-104">Specifies whether to print the grid when printing a document page.</span></span>
  
|<span data-ttu-id="42e29-105">**值**</span><span class="sxs-lookup"><span data-stu-id="42e29-105">**Value**</span></span>|<span data-ttu-id="42e29-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="42e29-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="42e29-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="42e29-107">TRUE</span></span>  <br/> |<span data-ttu-id="42e29-108">在打印此页时显示网格。</span><span class="sxs-lookup"><span data-stu-id="42e29-108">Show the grid when printing this page.</span></span>  <br/> |
|<span data-ttu-id="42e29-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="42e29-109">FALSE</span></span>  <br/> |<span data-ttu-id="42e29-110">在打印此页时不显示网格（默认值）。</span><span class="sxs-lookup"><span data-stu-id="42e29-110">Do not show the grid when printing this page (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42e29-111">备注</span><span class="sxs-lookup"><span data-stu-id="42e29-111">Remarks</span></span>

<span data-ttu-id="42e29-p101">此值对应于 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中 **“打印设置”** 选项卡上的 **“网格线”** 复选框。与颜色（打印出来的效果为灰色）不同的是，打印出来的网格与您在 Microsoft Visio 绘图窗口中看到的网格相同。</span><span class="sxs-lookup"><span data-stu-id="42e29-p101">This value corresponds to the **Gridlines** check box on the **Print Setup** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow). Other than color (the printed version is gray), the printed grid is identical to the grid you see in the Microsoft Visio drawing window.</span></span> 
  
<span data-ttu-id="42e29-114">您可以选择是否逐页打印网格。</span><span class="sxs-lookup"><span data-stu-id="42e29-114">You can choose whether to print the grid on a page-by-page basis.</span></span> <span data-ttu-id="42e29-115">还可以在"视图"选项卡上的"标尺网格"对话框 (中，单击"在页面处于活动状态时显示网格) 按页定义网格的样式。 **&amp;**</span><span class="sxs-lookup"><span data-stu-id="42e29-115">The style of grid can also be defined on a page-by-page basis in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow) when a page is active.</span></span> 
  
<span data-ttu-id="42e29-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PrintGrid 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="42e29-116">To get a reference to the PrintGrid cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42e29-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="42e29-117">Cell name:</span></span>  <br/> |<span data-ttu-id="42e29-118">PrintGrid</span><span class="sxs-lookup"><span data-stu-id="42e29-118">PrintGrid</span></span>  <br/> |
   
<span data-ttu-id="42e29-119">若要从某个程序按索引获取对 PrintGrid 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="42e29-119">To get a reference to the PrintGrid cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="42e29-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="42e29-120">Section index:</span></span>  <br/> |<span data-ttu-id="42e29-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="42e29-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="42e29-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="42e29-122">Row index:</span></span>  <br/> |<span data-ttu-id="42e29-123">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="42e29-123">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="42e29-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="42e29-124">Cell index:</span></span>  <br/> |<span data-ttu-id="42e29-125">**visPrintPropertiesPrintGrid**</span><span class="sxs-lookup"><span data-stu-id="42e29-125">**visPrintPropertiesPrintGrid**</span></span> <br/> |
   

