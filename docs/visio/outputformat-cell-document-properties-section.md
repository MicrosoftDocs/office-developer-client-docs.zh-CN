---
title: OutputFormat 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251617
localization_priority: Normal
ms.assetid: 17238019-c800-5d3a-32f6-fb0008d4e25f
description: 确定绘图的输出格式。绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。
ms.openlocfilehash: 7103fa5c2bc721add3496b7a497989d6632d58f1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780813"
---
# <a name="outputformat-cell-document-properties-section"></a><span data-ttu-id="d5fd7-104">OutputFormat 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="d5fd7-104">OutputFormat Cell (Document Properties Section)</span></span>

<span data-ttu-id="d5fd7-p102">确定绘图的输出格式。绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。</span><span class="sxs-lookup"><span data-stu-id="d5fd7-p102">Determines the output format for a drawing. Drawing pages are usually formatted for printing (default); however, you can choose other output formats.</span></span>
  
|<span data-ttu-id="d5fd7-107">**值**</span><span class="sxs-lookup"><span data-stu-id="d5fd7-107">**Value**</span></span>|<span data-ttu-id="d5fd7-108">**输出格式**</span><span class="sxs-lookup"><span data-stu-id="d5fd7-108">**Output format**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d5fd7-109">0</span><span class="sxs-lookup"><span data-stu-id="d5fd7-109">0</span></span>  <br/> | <span data-ttu-id="d5fd7-110">打印（默认值）</span><span class="sxs-lookup"><span data-stu-id="d5fd7-110">Printing (default)</span></span>  <br/> |
| <span data-ttu-id="d5fd7-111">1</span><span class="sxs-lookup"><span data-stu-id="d5fd7-111">1</span></span>  <br/> | <span data-ttu-id="d5fd7-112">PowerPoint 幻灯片放映</span><span class="sxs-lookup"><span data-stu-id="d5fd7-112">PowerPoint slide show</span></span>  <br/> |
| <span data-ttu-id="d5fd7-113">2</span><span class="sxs-lookup"><span data-stu-id="d5fd7-113">2</span></span>  <br/> | <span data-ttu-id="d5fd7-114">HTML 或 GIF 输出</span><span class="sxs-lookup"><span data-stu-id="d5fd7-114">HTML or GIF output</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5fd7-115">注释</span><span class="sxs-lookup"><span data-stu-id="d5fd7-115">Remarks</span></span>

<span data-ttu-id="d5fd7-116">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 OutputFormat 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-116">To get a reference to the OutputFormat cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d5fd7-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-117">Cell name:</span></span>  <br/> | <span data-ttu-id="d5fd7-118">OutputFormat</span><span class="sxs-lookup"><span data-stu-id="d5fd7-118">OutputFormat</span></span>  <br/> |
   
<span data-ttu-id="d5fd7-119">要从某个程序按索引获取对 OutputFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-119">To get a reference to the OutputFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d5fd7-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-120">Section index:</span></span>  <br/> |<span data-ttu-id="d5fd7-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d5fd7-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d5fd7-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-122">Row index:</span></span>  <br/> |<span data-ttu-id="d5fd7-123">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="d5fd7-123">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="d5fd7-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d5fd7-124">Cell index:</span></span>  <br/> |<span data-ttu-id="d5fd7-125">**visDocOutputFormat**</span><span class="sxs-lookup"><span data-stu-id="d5fd7-125">**visDocOutputFormat**</span></span> <br/> |
   

