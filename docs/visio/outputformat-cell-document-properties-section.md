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
description: 确定绘图的输出格式。 绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。
ms.openlocfilehash: 09fa34095772936ab1c6a3025ed1884a533f55e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359281"
---
# <a name="outputformat-cell-document-properties-section"></a><span data-ttu-id="42fcc-104">OutputFormat 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="42fcc-104">OutputFormat Cell (Document Properties Section)</span></span>

<span data-ttu-id="42fcc-105">确定绘图的输出格式。</span><span class="sxs-lookup"><span data-stu-id="42fcc-105">Determines the output format for a drawing.</span></span> <span data-ttu-id="42fcc-106">绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。</span><span class="sxs-lookup"><span data-stu-id="42fcc-106">Drawing pages are usually formatted for printing (default); however, you can choose other output formats.</span></span>
  
|<span data-ttu-id="42fcc-107">**值**</span><span class="sxs-lookup"><span data-stu-id="42fcc-107">**Value**</span></span>|<span data-ttu-id="42fcc-108">**输出格式**</span><span class="sxs-lookup"><span data-stu-id="42fcc-108">**Output format**</span></span>|
|:-----|:-----|
| <span data-ttu-id="42fcc-109">0</span><span class="sxs-lookup"><span data-stu-id="42fcc-109">0</span></span>  <br/> | <span data-ttu-id="42fcc-110">打印（默认值）</span><span class="sxs-lookup"><span data-stu-id="42fcc-110">Printing (default)</span></span>  <br/> |
| <span data-ttu-id="42fcc-111">1</span><span class="sxs-lookup"><span data-stu-id="42fcc-111">1</span></span>  <br/> | <span data-ttu-id="42fcc-112">PowerPoint 幻灯片放映</span><span class="sxs-lookup"><span data-stu-id="42fcc-112">PowerPoint slide show</span></span>  <br/> |
| <span data-ttu-id="42fcc-113">双面</span><span class="sxs-lookup"><span data-stu-id="42fcc-113">2</span></span>  <br/> | <span data-ttu-id="42fcc-114">HTML 或 GIF 输出</span><span class="sxs-lookup"><span data-stu-id="42fcc-114">HTML or GIF output</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42fcc-115">注解</span><span class="sxs-lookup"><span data-stu-id="42fcc-115">Remarks</span></span>

<span data-ttu-id="42fcc-116">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 OutputFormat 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="42fcc-116">To get a reference to the OutputFormat cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="42fcc-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="42fcc-117">Cell name:</span></span>  <br/> | <span data-ttu-id="42fcc-118">OutputFormat</span><span class="sxs-lookup"><span data-stu-id="42fcc-118">OutputFormat</span></span>  <br/> |
   
<span data-ttu-id="42fcc-119">要从某个程序按索引获取对 OutputFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="42fcc-119">To get a reference to the OutputFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="42fcc-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="42fcc-120">Section index:</span></span>  <br/> |<span data-ttu-id="42fcc-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="42fcc-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="42fcc-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="42fcc-122">Row index:</span></span>  <br/> |<span data-ttu-id="42fcc-123">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="42fcc-123">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="42fcc-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="42fcc-124">Cell index:</span></span>  <br/> |<span data-ttu-id="42fcc-125">**visDocOutputFormat**</span><span class="sxs-lookup"><span data-stu-id="42fcc-125">**visDocOutputFormat**</span></span> <br/> |
   

