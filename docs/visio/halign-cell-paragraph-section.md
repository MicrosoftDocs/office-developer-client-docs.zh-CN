---
title: HAlign 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm425
localization_priority: Normal
ms.assetid: a8d6b622-60b3-e43f-b6a1-55db561204ed
description: 确定形状的文本块中文本的水平对齐方式。
ms.openlocfilehash: 224e495e8aea70c418a0ab7f5a7d56975d9868e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780385"
---
# <a name="halign-cell-paragraph-section"></a><span data-ttu-id="95ee5-103">HAlign 单元格（“Paragraph”部分）</span><span class="sxs-lookup"><span data-stu-id="95ee5-103">HAlign Cell (Paragraph Section)</span></span>

<span data-ttu-id="95ee5-104">确定形状的文本块中文本的水平对齐方式。</span><span class="sxs-lookup"><span data-stu-id="95ee5-104">Determines the horizontal alignment of text in the shape's text block.</span></span>
  
|<span data-ttu-id="95ee5-105">**值**</span><span class="sxs-lookup"><span data-stu-id="95ee5-105">**Value**</span></span>|<span data-ttu-id="95ee5-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="95ee5-106">**Description**</span></span>|<span data-ttu-id="95ee5-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="95ee5-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="95ee5-108">0</span><span class="sxs-lookup"><span data-stu-id="95ee5-108">0</span></span>  <br/> | <span data-ttu-id="95ee5-109">左对齐</span><span class="sxs-lookup"><span data-stu-id="95ee5-109">Left align</span></span>  <br/> |<span data-ttu-id="95ee5-110">**visHorzLeft**</span><span class="sxs-lookup"><span data-stu-id="95ee5-110">**visHorzLeft**</span></span> <br/> |
| <span data-ttu-id="95ee5-111">1</span><span class="sxs-lookup"><span data-stu-id="95ee5-111">1</span></span>  <br/> | <span data-ttu-id="95ee5-112">居中</span><span class="sxs-lookup"><span data-stu-id="95ee5-112">Center</span></span>  <br/> |<span data-ttu-id="95ee5-113">**visHorzCenter**</span><span class="sxs-lookup"><span data-stu-id="95ee5-113">**visHorzCenter**</span></span> <br/> |
| <span data-ttu-id="95ee5-114">2</span><span class="sxs-lookup"><span data-stu-id="95ee5-114">2</span></span>  <br/> | <span data-ttu-id="95ee5-115">右对齐</span><span class="sxs-lookup"><span data-stu-id="95ee5-115">Right align</span></span>  <br/> |<span data-ttu-id="95ee5-116">**visHorzRight**</span><span class="sxs-lookup"><span data-stu-id="95ee5-116">**visHorzRight**</span></span> <br/> |
| <span data-ttu-id="95ee5-117">3</span><span class="sxs-lookup"><span data-stu-id="95ee5-117">3</span></span>  <br/> | <span data-ttu-id="95ee5-118">两端对齐</span><span class="sxs-lookup"><span data-stu-id="95ee5-118">Justify</span></span>  <br/> |<span data-ttu-id="95ee5-119">**visHorzJustify**</span><span class="sxs-lookup"><span data-stu-id="95ee5-119">**visHorzJustify**</span></span> <br/> |
| <span data-ttu-id="95ee5-120">4</span><span class="sxs-lookup"><span data-stu-id="95ee5-120">4</span></span>  <br/> | <span data-ttu-id="95ee5-121">强制对齐</span><span class="sxs-lookup"><span data-stu-id="95ee5-121">Force justify</span></span>  <br/> |<span data-ttu-id="95ee5-122">**visHorzForce**</span><span class="sxs-lookup"><span data-stu-id="95ee5-122">**visHorzForce**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="95ee5-123">注释</span><span class="sxs-lookup"><span data-stu-id="95ee5-123">Remarks</span></span>

<span data-ttu-id="95ee5-124">两端对齐就是在段落中每一行（最后一行除外）的字与字之间添加空格，以便文本的左右两端都与边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="95ee5-124">Justify adds space between words in every line except the last line of the paragraph to align both the left and right sides of text with the margins.</span></span>
  
<span data-ttu-id="95ee5-125">强制对齐就是将段落中每一行（包括最后一行）的两端对齐。</span><span class="sxs-lookup"><span data-stu-id="95ee5-125">Force justify justifies every line in the paragraph, including the last.</span></span>
  
<span data-ttu-id="95ee5-126">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 HAlign 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="95ee5-126">To get a reference to the HAlign cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="95ee5-127">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="95ee5-127">Cell name:</span></span>  <br/> | <span data-ttu-id="95ee5-128">Para.HorzAlign [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="95ee5-128">Para.HorzAlign[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="95ee5-129">要从某个程序按索引获取对 HAlign 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="95ee5-129">To get a reference to the HAlign cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="95ee5-130">内容索引：</span><span class="sxs-lookup"><span data-stu-id="95ee5-130">Section index:</span></span>  <br/> |<span data-ttu-id="95ee5-131">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="95ee5-131">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="95ee5-132">行索引：</span><span class="sxs-lookup"><span data-stu-id="95ee5-132">Row index:</span></span>  <br/> |<span data-ttu-id="95ee5-133">**visRowParagraph** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="95ee5-133">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="95ee5-134">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="95ee5-134">Cell index:</span></span>  <br/> |<span data-ttu-id="95ee5-135">**visHorzAlign**</span><span class="sxs-lookup"><span data-stu-id="95ee5-135">**visHorzAlign**</span></span> <br/> |
   

