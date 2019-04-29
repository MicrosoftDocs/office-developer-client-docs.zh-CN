---
title: SpLine 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm970
localization_priority: Normal
ms.assetid: 84f4e5f1-7c28-9e83-8644-28d117bb10a5
description: 确定一行文本和下一行文本之间的距离，用百分比表示，其中 100% 是文本行的高度。
ms.openlocfilehash: 82b2604a62608c0cc4333892d678b1eb886a9c7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434912"
---
# <a name="spline-cell-paragraph-section"></a><span data-ttu-id="1a22b-103">SpLine 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="1a22b-103">SpLine Cell (Paragraph Section)</span></span>

<span data-ttu-id="1a22b-104">确定一行文本和下一行文本之间的距离，用百分比表示，其中 100% 是文本行的高度。</span><span class="sxs-lookup"><span data-stu-id="1a22b-104">Determines the distance between one line of text and the next, expressed as a percentage, where 100% is the height of a text line.</span></span>
  
|<span data-ttu-id="1a22b-105">**值**</span><span class="sxs-lookup"><span data-stu-id="1a22b-105">**Value**</span></span>|<span data-ttu-id="1a22b-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a22b-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1a22b-107">\>0</span><span class="sxs-lookup"><span data-stu-id="1a22b-107">\>0</span></span>  <br/> | <span data-ttu-id="1a22b-108">绝对间距，与字体大小无关</span><span class="sxs-lookup"><span data-stu-id="1a22b-108">Absolute spacing, regardless of font size</span></span>  <br/> |
| <span data-ttu-id="1a22b-109">= 0</span><span class="sxs-lookup"><span data-stu-id="1a22b-109">=0</span></span>  <br/> | <span data-ttu-id="1a22b-110">设置纯色（间距 = 100% 的字体大小）</span><span class="sxs-lookup"><span data-stu-id="1a22b-110">Set solid (spacing = 100% of font size)</span></span>  <br/> |
| <span data-ttu-id="1a22b-111">\<0</span><span class="sxs-lookup"><span data-stu-id="1a22b-111">\<0</span></span>  <br/> | <span data-ttu-id="1a22b-112">字体大小的百分比（例如，-120% 生成 120% 间距）</span><span class="sxs-lookup"><span data-stu-id="1a22b-112">A percentage of font size (for example, -120% yields 120% spacing)</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a22b-113">说明</span><span class="sxs-lookup"><span data-stu-id="1a22b-113">Remarks</span></span>

<span data-ttu-id="1a22b-114">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 SpLine 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1a22b-114">To get a reference to the SpLine cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1a22b-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1a22b-115">Cell name:</span></span>  <br/> | <span data-ttu-id="1a22b-116">&.</span><span class="sxs-lookup"><span data-stu-id="1a22b-116">Para.</span></span> <span data-ttu-id="1a22b-117">样条 [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="1a22b-117">SpLine [  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="1a22b-118">要从某个程序按索引获取对 SpLine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1a22b-118">To get a reference to the SpLine cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1a22b-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1a22b-119">Section index:</span></span>  <br/> |<span data-ttu-id="1a22b-120">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="1a22b-120">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="1a22b-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="1a22b-121">Row index:</span></span>  <br/> |<span data-ttu-id="1a22b-122">**visRowParagraph** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="1a22b-122">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="1a22b-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1a22b-123">Cell index:</span></span>  <br/> |<span data-ttu-id="1a22b-124">**visSpaceLine**</span><span class="sxs-lookup"><span data-stu-id="1a22b-124">**visSpaceLine**</span></span> <br/> |
   

