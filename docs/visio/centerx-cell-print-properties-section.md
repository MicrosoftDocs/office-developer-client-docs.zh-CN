---
title: CenterX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60030
localization_priority: Normal
ms.assetid: 890e2537-66a5-2863-c78d-320b42565ea7
description: 确定该绘图页是否在打印纸上水平居中。
ms.openlocfilehash: 13b05ed71248a3f8fada947fca6b203c6ab19c6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418076"
---
# <a name="centerx-cell-print-properties-section"></a><span data-ttu-id="b8e99-103">CenterX 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="b8e99-103">CenterX Cell (Print Properties Section)</span></span>

<span data-ttu-id="b8e99-104">确定该绘图页是否在打印纸上水平居中。</span><span class="sxs-lookup"><span data-stu-id="b8e99-104">Determines whether the drawing page is centered horizontally on the printer page.</span></span> 
  
|<span data-ttu-id="b8e99-105">**值**</span><span class="sxs-lookup"><span data-stu-id="b8e99-105">**Value**</span></span>|<span data-ttu-id="b8e99-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8e99-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b8e99-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="b8e99-107">TRUE</span></span>  <br/> | <span data-ttu-id="b8e99-108">使绘图页在打印纸上水平居中。</span><span class="sxs-lookup"><span data-stu-id="b8e99-108">Center the drawing page horizontally on the printer page.</span></span>  <br/> |
| <span data-ttu-id="b8e99-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="b8e99-109">FALSE</span></span>  <br/> | <span data-ttu-id="b8e99-110">使绘图页在打印纸上不水平居中（默认值）。</span><span class="sxs-lookup"><span data-stu-id="b8e99-110">Do not center the drawing page horizontally on the printer page (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b8e99-111">备注</span><span class="sxs-lookup"><span data-stu-id="b8e99-111">Remarks</span></span>

<span data-ttu-id="b8e99-p101">默认情况下，绘图页与打印纸的左上角对齐。将 CenterX 单元格和 CenterY 单元格设置为 TRUE，可以将绘图页放置在打印纸的中心（如果需要平铺，则放置在多张打印纸的中心）。</span><span class="sxs-lookup"><span data-stu-id="b8e99-p101">By default, drawing pages are justified to the top and left of the printer page. Setting the CenterX and CenterY cells to TRUE places the drawing page in the center of the printer page (or pages when tiling is necessary).</span></span> 
  
<span data-ttu-id="b8e99-114">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 CenterX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="b8e99-114">To get a reference to the CenterX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b8e99-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b8e99-115">Cell name:</span></span>  <br/> | <span data-ttu-id="b8e99-116">CenterX</span><span class="sxs-lookup"><span data-stu-id="b8e99-116">CenterX</span></span>  <br/> |
   
<span data-ttu-id="b8e99-117">要从某个程序按索引获取对 CenterX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="b8e99-117">To get a reference to the CenterX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b8e99-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b8e99-118">Section index:</span></span>  <br/> |<span data-ttu-id="b8e99-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b8e99-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b8e99-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="b8e99-120">Row index:</span></span>  <br/> |<span data-ttu-id="b8e99-121">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="b8e99-121">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="b8e99-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b8e99-122">Cell index:</span></span>  <br/> |<span data-ttu-id="b8e99-123">**visPrintPropertiesCenterX**</span><span class="sxs-lookup"><span data-stu-id="b8e99-123">**visPrintPropertiesCenterX**</span></span> <br/> |
   

