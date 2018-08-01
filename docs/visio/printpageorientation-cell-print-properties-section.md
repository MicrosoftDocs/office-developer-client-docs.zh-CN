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
ms.openlocfilehash: 2adc7dadcb3702e6c5307bb569b2ae1df7aee54e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780984"
---
# <a name="printpageorientation-cell-print-properties-section"></a><span data-ttu-id="3320b-103">PrintPageOrientation 单元格（“Print Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="3320b-103">PrintPageOrientation Cell (Print Properties Section)</span></span>

<span data-ttu-id="3320b-104">确定是纵向打印页面还是横向打印页面。</span><span class="sxs-lookup"><span data-stu-id="3320b-104">Determines whether the page prints using portrait or landscape orientation.</span></span>
  
|<span data-ttu-id="3320b-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3320b-105">**Value**</span></span>|<span data-ttu-id="3320b-106">**Orientation**</span><span class="sxs-lookup"><span data-stu-id="3320b-106">**Orientation**</span></span>|<span data-ttu-id="3320b-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="3320b-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="3320b-108">0</span><span class="sxs-lookup"><span data-stu-id="3320b-108">0</span></span>  <br/> | <span data-ttu-id="3320b-109">同于打印机</span><span class="sxs-lookup"><span data-stu-id="3320b-109">Same as printer</span></span>  <br/> |<span data-ttu-id="3320b-110">**visPPOSameAsPrinter**</span><span class="sxs-lookup"><span data-stu-id="3320b-110">**visPPOSameAsPrinter**</span></span> <br/> |
| <span data-ttu-id="3320b-111">1</span><span class="sxs-lookup"><span data-stu-id="3320b-111">1</span></span>  <br/> | <span data-ttu-id="3320b-112">纵向</span><span class="sxs-lookup"><span data-stu-id="3320b-112">Portrait</span></span>  <br/> |<span data-ttu-id="3320b-113">**visPPOPortrait**</span><span class="sxs-lookup"><span data-stu-id="3320b-113">**visPPOPortrait**</span></span> <br/> |
|<span data-ttu-id="3320b-114">2</span><span class="sxs-lookup"><span data-stu-id="3320b-114">2</span></span>  <br/> |<span data-ttu-id="3320b-115">横向</span><span class="sxs-lookup"><span data-stu-id="3320b-115">Landscape</span></span>  <br/> |<span data-ttu-id="3320b-116">**visPPOLandscape**</span><span class="sxs-lookup"><span data-stu-id="3320b-116">**visPPOLandscape**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3320b-117">说明</span><span class="sxs-lookup"><span data-stu-id="3320b-117">Remarks</span></span>

<span data-ttu-id="3320b-118">当在文档中插入新的页面时，此设置将默认为活动页中的设置。</span><span class="sxs-lookup"><span data-stu-id="3320b-118">When you insert new pages in a document, this setting defaults to the setting in the active page.</span></span>
  
<span data-ttu-id="3320b-119">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PrintPageOrientation 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3320b-119">To get a reference to the PrintPageOrientation cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3320b-120">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3320b-120">Cell name:</span></span>  <br/> | <span data-ttu-id="3320b-121">PrintPageOrientation</span><span class="sxs-lookup"><span data-stu-id="3320b-121">PrintPageOrientation</span></span>  <br/> |
   
<span data-ttu-id="3320b-122">要从某个程序按索引获取对 PrintPageOrientation 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3320b-122">To get a reference to the PrintPageOrientation cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3320b-123">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3320b-123">Section index:</span></span>  <br/> |<span data-ttu-id="3320b-124">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3320b-124">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3320b-125">行索引：</span><span class="sxs-lookup"><span data-stu-id="3320b-125">Row index:</span></span>  <br/> |<span data-ttu-id="3320b-126">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="3320b-126">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="3320b-127">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3320b-127">Cell index:</span></span>  <br/> |<span data-ttu-id="3320b-128">**visPrintPropertiesPageOrientation**</span><span class="sxs-lookup"><span data-stu-id="3320b-128">**visPrintPropertiesPageOrientation**</span></span> <br/> |
   

