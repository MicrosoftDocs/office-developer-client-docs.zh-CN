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
ms.openlocfilehash: 5b695ccf6fa2364809e2f5124b9f55ea6aab50e0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780805"
---
# <a name="onpage-cell-print-properties-section"></a><span data-ttu-id="cbe37-103">OnPage 单元格（“Print Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="cbe37-103">OnPage Cell (Print Properties Section)</span></span>

<span data-ttu-id="cbe37-104">指示是否将绘图打印到指定数量的打印纸上。</span><span class="sxs-lookup"><span data-stu-id="cbe37-104">Indicates whether the drawing is printed on a specific number of printer pages.</span></span> 
  
|<span data-ttu-id="cbe37-105">**值**</span><span class="sxs-lookup"><span data-stu-id="cbe37-105">**Value**</span></span>|<span data-ttu-id="cbe37-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbe37-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbe37-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="cbe37-107">TRUE</span></span>  <br/> |<span data-ttu-id="cbe37-108">适合绘图页定义数量的打印纸。</span><span class="sxs-lookup"><span data-stu-id="cbe37-108">Fit the drawing page to a defined number of printer pages.</span></span>  <br/> |
|<span data-ttu-id="cbe37-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="cbe37-109">FALSE</span></span>  <br/> |<span data-ttu-id="cbe37-110">不调整绘图页的大小以使其适合指定数量的打印纸（默认值）。</span><span class="sxs-lookup"><span data-stu-id="cbe37-110">Do not fit the drawing page to a defined number of printer pages (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cbe37-111">注解</span><span class="sxs-lookup"><span data-stu-id="cbe37-111">Remarks</span></span>

<span data-ttu-id="cbe37-p101">如果 OnPage 单元格设置为 TRUE，则 Microsoft Visio 将使用 PagesX 单元格和 PagesY 单元格来确定适合于该绘图的打印页的数目。ScaleX 单元格和 ScaleY 单元格中的值将被忽略。可以将此设置视为“自动缩放”设置。</span><span class="sxs-lookup"><span data-stu-id="cbe37-p101">If the OnPage cell is set to TRUE, Microsoft Visio uses the PagesX and PagesY cells to determine the number of printer pages on which to fit the drawing. Values in the ScaleX and ScaleY cells are ignored. This can be considered an "autoscale" setting.</span></span>
  
<span data-ttu-id="cbe37-115">此值对应于**页面设置**对话框中**打印设置**选项卡上的**调整为**选项 （**设计**选项卡中，单击**页面设置**箭头）。</span><span class="sxs-lookup"><span data-stu-id="cbe37-115">This value corresponds to the **Fit to** option on the **Print Setup** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow) .</span></span> 
  
<span data-ttu-id="cbe37-116">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 OnPage 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cbe37-116">To get a reference to the OnPage cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cbe37-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cbe37-117">Cell name:</span></span>  <br/> |<span data-ttu-id="cbe37-118">OnPage</span><span class="sxs-lookup"><span data-stu-id="cbe37-118">OnPage</span></span>  <br/> |
   
<span data-ttu-id="cbe37-119">若要从某个程序按索引获取对 OnPage 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cbe37-119">To get a reference to the OnPage cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cbe37-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cbe37-120">Section index:</span></span>  <br/> |<span data-ttu-id="cbe37-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cbe37-121">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="cbe37-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="cbe37-122">Row index:</span></span>  <br/> |<span data-ttu-id="cbe37-123">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="cbe37-123">**visRowPrintProperties**</span></span> <br/> |
|<span data-ttu-id="cbe37-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cbe37-124">Cell index:</span></span>  <br/> |<span data-ttu-id="cbe37-125">**visPrintPropertiesOnPage**</span><span class="sxs-lookup"><span data-stu-id="cbe37-125">**visPrintPropertiesOnPage**</span></span> <br/> |
   

