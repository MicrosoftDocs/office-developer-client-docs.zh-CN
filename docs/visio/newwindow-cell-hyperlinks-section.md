---
title: NewWindow 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm695
localization_priority: Normal
ms.assetid: 44995137-d241-937a-c097-0f9d79203cdf
description: 指定是否在新窗口中打开超链接。
ms.openlocfilehash: 0f9d1e4b1294dea3f211c8d0d69ffc49b6180066
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396335"
---
# <a name="newwindow-cell-hyperlinks-section"></a><span data-ttu-id="e1db7-103">NewWindow 单元格（“Hyperlinks”部分）</span><span class="sxs-lookup"><span data-stu-id="e1db7-103">NewWindow Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="e1db7-104">指定是否在新窗口中打开超链接。</span><span class="sxs-lookup"><span data-stu-id="e1db7-104">Specifies whether to open the hyperlink in a new window.</span></span>
  
|<span data-ttu-id="e1db7-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e1db7-105">**Value**</span></span>|<span data-ttu-id="e1db7-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1db7-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e1db7-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="e1db7-107">TRUE</span></span>  <br/> | <span data-ttu-id="e1db7-108">在新窗口中打开链接的页面、 文档或网站。</span><span class="sxs-lookup"><span data-stu-id="e1db7-108">Open the linked page, document, or website in a new window.</span></span>  <br/> |
| <span data-ttu-id="e1db7-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="e1db7-109">FALSE</span></span>  <br/> | <span data-ttu-id="e1db7-p101">默认值。不为超链接打开新窗口。</span><span class="sxs-lookup"><span data-stu-id="e1db7-p101">Default. Do not open a new window for the hyperlink.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1db7-112">注释</span><span class="sxs-lookup"><span data-stu-id="e1db7-112">Remarks</span></span>

<span data-ttu-id="e1db7-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NewWindow 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e1db7-113">To get a reference to the NewWindow cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e1db7-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e1db7-114">Cell name:</span></span>  <br/> | <span data-ttu-id="e1db7-115">超链接。</span><span class="sxs-lookup"><span data-stu-id="e1db7-115">Hyperlink.</span></span>  <span data-ttu-id="e1db7-116">*名称*。NewWindow 其中超链接。</span><span class="sxs-lookup"><span data-stu-id="e1db7-116">*Name*  .NewWindow            where Hyperlink.</span></span>  <span data-ttu-id="e1db7-117">*Name*是行名称</span><span class="sxs-lookup"><span data-stu-id="e1db7-117">*Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="e1db7-118">要从某个程序按索引获取对 NewWindow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e1db7-118">To get a reference to the NewWindow cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e1db7-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e1db7-119">Section index:</span></span>  <br/> |<span data-ttu-id="e1db7-120">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="e1db7-120">**visSectionHyperlink**</span></span> <br/> |
| <span data-ttu-id="e1db7-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="e1db7-121">Row index:</span></span>  <br/> |<span data-ttu-id="e1db7-122">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="e1db7-122">**visRow1stHyperlink** +  *i*            where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
| <span data-ttu-id="e1db7-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e1db7-123">Cell index:</span></span>  <br/> |<span data-ttu-id="e1db7-124">**visHLinkNewWin**</span><span class="sxs-lookup"><span data-stu-id="e1db7-124">**visHLinkNewWin**</span></span> <br/> |
   

