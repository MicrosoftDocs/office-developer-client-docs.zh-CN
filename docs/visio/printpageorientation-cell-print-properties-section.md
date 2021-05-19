---
title: PrintPageOrientation 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033795
localization_priority: Normal
ms.assetid: f8354d0d-0ce2-fb33-ddf7-611a2c24a8be
description: 确定是纵向打印页面还是横向打印页面。
ms.openlocfilehash: f7e73bea5120d878a1b2dbf553a66b349d247fce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434863"
---
# <a name="printpageorientation-cell-print-properties-section"></a><span data-ttu-id="cc965-103">PrintPageOrientation 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="cc965-103">PrintPageOrientation Cell (Print Properties Section)</span></span>

<span data-ttu-id="cc965-104">确定是纵向打印页面还是横向打印页面。</span><span class="sxs-lookup"><span data-stu-id="cc965-104">Determines whether the page prints using portrait or landscape orientation.</span></span>
  
|<span data-ttu-id="cc965-105">**值**</span><span class="sxs-lookup"><span data-stu-id="cc965-105">**Value**</span></span>|<span data-ttu-id="cc965-106">**Orientation**</span><span class="sxs-lookup"><span data-stu-id="cc965-106">**Orientation**</span></span>|<span data-ttu-id="cc965-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="cc965-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="cc965-108">0</span><span class="sxs-lookup"><span data-stu-id="cc965-108">0</span></span>  <br/> | <span data-ttu-id="cc965-109">同于打印机</span><span class="sxs-lookup"><span data-stu-id="cc965-109">Same as printer</span></span>  <br/> |<span data-ttu-id="cc965-110">**visPPOSameAsPrinter**</span><span class="sxs-lookup"><span data-stu-id="cc965-110">**visPPOSameAsPrinter**</span></span> <br/> |
| <span data-ttu-id="cc965-111">1</span><span class="sxs-lookup"><span data-stu-id="cc965-111">1</span></span>  <br/> | <span data-ttu-id="cc965-112">Portrait</span><span class="sxs-lookup"><span data-stu-id="cc965-112">Portrait</span></span>  <br/> |<span data-ttu-id="cc965-113">**visPPOPortrait**</span><span class="sxs-lookup"><span data-stu-id="cc965-113">**visPPOPortrait**</span></span> <br/> |
|<span data-ttu-id="cc965-114">2</span><span class="sxs-lookup"><span data-stu-id="cc965-114">2</span></span>  <br/> |<span data-ttu-id="cc965-115">横向</span><span class="sxs-lookup"><span data-stu-id="cc965-115">Landscape</span></span>  <br/> |<span data-ttu-id="cc965-116">**visPPOLandscape**</span><span class="sxs-lookup"><span data-stu-id="cc965-116">**visPPOLandscape**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc965-117">备注</span><span class="sxs-lookup"><span data-stu-id="cc965-117">Remarks</span></span>

<span data-ttu-id="cc965-118">在文档中插入新页面时，此设置默认为活动页中的设置。</span><span class="sxs-lookup"><span data-stu-id="cc965-118">When you insert new pages in a document, this setting defaults to the setting in the active page.</span></span>
  
<span data-ttu-id="cc965-119">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PrintPageOrientation 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cc965-119">To get a reference to the PrintPageOrientation cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cc965-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cc965-120">Cell name:</span></span>  <br/> | <span data-ttu-id="cc965-121">PrintPageOrientation</span><span class="sxs-lookup"><span data-stu-id="cc965-121">PrintPageOrientation</span></span>  <br/> |
   
<span data-ttu-id="cc965-122">要从某个程序按索引获取对 PrintPageOrientation 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cc965-122">To get a reference to the PrintPageOrientation cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cc965-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cc965-123">Section index:</span></span>  <br/> |<span data-ttu-id="cc965-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="cc965-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="cc965-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="cc965-125">Row index:</span></span>  <br/> |<span data-ttu-id="cc965-126">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="cc965-126">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="cc965-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cc965-127">Cell index:</span></span>  <br/> |<span data-ttu-id="cc965-128">**visPrintPropertiesPageOrientation**</span><span class="sxs-lookup"><span data-stu-id="cc965-128">**visPrintPropertiesPageOrientation**</span></span> <br/> |
   

