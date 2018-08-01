---
title: VerticalAlign 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1105
localization_priority: Normal
ms.assetid: ff34a23b-2881-864f-42e4-871c4fde0992
description: 确定文本块内文本的垂直对齐方式。
ms.openlocfilehash: cfd34f17eec597c306b69f76929877013b39015e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781637"
---
# <a name="verticalalign-cell-text-block-format-section"></a><span data-ttu-id="ed129-103">VerticalAlign 单元格（“Text Block Format”部分）</span><span class="sxs-lookup"><span data-stu-id="ed129-103">VerticalAlign Cell (Text Block Format Section)</span></span>

<span data-ttu-id="ed129-104">确定文本块内文本的垂直对齐方式。</span><span class="sxs-lookup"><span data-stu-id="ed129-104">Determines the vertical alignment of text within the text block.</span></span>
  
|<span data-ttu-id="ed129-105">**值**</span><span class="sxs-lookup"><span data-stu-id="ed129-105">**Value**</span></span>|<span data-ttu-id="ed129-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed129-106">**Description**</span></span>|<span data-ttu-id="ed129-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="ed129-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="ed129-108">0</span><span class="sxs-lookup"><span data-stu-id="ed129-108">0</span></span>  <br/> | <span data-ttu-id="ed129-109">靠上</span><span class="sxs-lookup"><span data-stu-id="ed129-109">Top</span></span>  <br/> |<span data-ttu-id="ed129-110">**visVertTop**</span><span class="sxs-lookup"><span data-stu-id="ed129-110">**visVertTop**</span></span> <br/> |
| <span data-ttu-id="ed129-111">1</span><span class="sxs-lookup"><span data-stu-id="ed129-111">1</span></span>  <br/> | <span data-ttu-id="ed129-112">居中</span><span class="sxs-lookup"><span data-stu-id="ed129-112">Middle</span></span>  <br/> |<span data-ttu-id="ed129-113">**visVertMiddle**</span><span class="sxs-lookup"><span data-stu-id="ed129-113">**visVertMiddle**</span></span> <br/> |
| <span data-ttu-id="ed129-114">2</span><span class="sxs-lookup"><span data-stu-id="ed129-114">2</span></span>  <br/> | <span data-ttu-id="ed129-115">靠下</span><span class="sxs-lookup"><span data-stu-id="ed129-115">Bottom</span></span>  <br/> |<span data-ttu-id="ed129-116">**visVertBottom**</span><span class="sxs-lookup"><span data-stu-id="ed129-116">**visVertBottom**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed129-117">说明</span><span class="sxs-lookup"><span data-stu-id="ed129-117">Remarks</span></span>

<span data-ttu-id="ed129-118">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 VerticalAlign 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ed129-118">To get a reference to the VerticalAlign cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ed129-119">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ed129-119">Cell name:</span></span>  <br/> | <span data-ttu-id="ed129-120">VerticalAlign</span><span class="sxs-lookup"><span data-stu-id="ed129-120">VerticalAlign</span></span>  <br/> |
   
<span data-ttu-id="ed129-121">要从某个程序按索引获取对 VerticalAlign 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ed129-121">To get a reference to the VerticalAlign cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ed129-122">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ed129-122">Section index:</span></span>  <br/> |<span data-ttu-id="ed129-123">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ed129-123">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ed129-124">行索引：</span><span class="sxs-lookup"><span data-stu-id="ed129-124">Row index:</span></span>  <br/> |<span data-ttu-id="ed129-125">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="ed129-125">**visRowText**</span></span> <br/> |
| <span data-ttu-id="ed129-126">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ed129-126">Cell index:</span></span>  <br/> |<span data-ttu-id="ed129-127">**visTxtBlkVerticalAlign**</span><span class="sxs-lookup"><span data-stu-id="ed129-127">**visTxtBlkVerticalAlign**</span></span> <br/> |
   

