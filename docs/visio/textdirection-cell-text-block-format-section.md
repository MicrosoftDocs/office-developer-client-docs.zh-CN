---
title: TextDirection 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm995
localization_priority: Normal
ms.assetid: 1df3a50e-7ea5-9244-1286-c1d00c217a9a
description: 确定文本块中字符的方向。
ms.openlocfilehash: c238b6b2a47c968809869f8eb3e38b6f0db1dcad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781513"
---
# <a name="textdirection-cell-text-block-format-section"></a><span data-ttu-id="3cd6f-103">TextDirection 单元格（“Text Block Format”部分）</span><span class="sxs-lookup"><span data-stu-id="3cd6f-103">TextDirection Cell (Text Block Format Section)</span></span>

<span data-ttu-id="3cd6f-104">确定文本块中字符的方向。</span><span class="sxs-lookup"><span data-stu-id="3cd6f-104">Determines the direction of the characters in a text block.</span></span>
  
|<span data-ttu-id="3cd6f-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-105">**Value**</span></span>|<span data-ttu-id="3cd6f-106">**Direction**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-106">**Direction**</span></span>|<span data-ttu-id="3cd6f-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="3cd6f-108">0</span><span class="sxs-lookup"><span data-stu-id="3cd6f-108">0</span></span>  <br/> | <span data-ttu-id="3cd6f-109">水平</span><span class="sxs-lookup"><span data-stu-id="3cd6f-109">Horizontal</span></span>  <br/> |<span data-ttu-id="3cd6f-110">**visTxtBlkLeftToRight**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-110">**visTxtBlkLeftToRight**</span></span> <br/> |
| <span data-ttu-id="3cd6f-111">1</span><span class="sxs-lookup"><span data-stu-id="3cd6f-111">1</span></span>  <br/> | <span data-ttu-id="3cd6f-112">垂直</span><span class="sxs-lookup"><span data-stu-id="3cd6f-112">Vertical</span></span>  <br/> |<span data-ttu-id="3cd6f-113">**visTxtBlkTopToBottom**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-113">**visTxtBlkTopToBottom**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cd6f-114">注释</span><span class="sxs-lookup"><span data-stu-id="3cd6f-114">Remarks</span></span>

<span data-ttu-id="3cd6f-115">在 Visio 5.0 日语版产品中，此单元格的值存储在“Miscellaneous”内容的 VerticalText 单元格中。</span><span class="sxs-lookup"><span data-stu-id="3cd6f-115">In Visio version 5.0 Japanese products, the value of this cell was stored in the VerticalText cell in the Miscellaneous section.</span></span>
  
<span data-ttu-id="3cd6f-116">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TextDirection 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-116">To get a reference to the TextDirection cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3cd6f-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-117">Cell name:</span></span>  <br/> | <span data-ttu-id="3cd6f-118">TextDirection</span><span class="sxs-lookup"><span data-stu-id="3cd6f-118">TextDirection</span></span>  <br/> |
   
<span data-ttu-id="3cd6f-119">要从某个程序按索引获取对 TextDirection 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-119">To get a reference to the TextDirection cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3cd6f-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-120">Section index:</span></span>  <br/> |<span data-ttu-id="3cd6f-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3cd6f-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-122">Row index:</span></span>  <br/> |<span data-ttu-id="3cd6f-123">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-123">**visRowText**</span></span> <br/> |
| <span data-ttu-id="3cd6f-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3cd6f-124">Cell index:</span></span>  <br/> |<span data-ttu-id="3cd6f-125">**visTxtBlkDirection**</span><span class="sxs-lookup"><span data-stu-id="3cd6f-125">**visTxtBlkDirection**</span></span> <br/> |
   

