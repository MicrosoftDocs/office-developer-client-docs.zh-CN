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
ms.openlocfilehash: 559a2930d9ef62612cabab79ccf55ca2c30e877b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406225"
---
# <a name="textdirection-cell-text-block-format-section"></a><span data-ttu-id="ea779-103">TextDirection 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="ea779-103">TextDirection Cell (Text Block Format Section)</span></span>

<span data-ttu-id="ea779-104">确定文本块中字符的方向。</span><span class="sxs-lookup"><span data-stu-id="ea779-104">Determines the direction of the characters in a text block.</span></span>
  
|<span data-ttu-id="ea779-105">**值**</span><span class="sxs-lookup"><span data-stu-id="ea779-105">**Value**</span></span>|<span data-ttu-id="ea779-106">**方向**</span><span class="sxs-lookup"><span data-stu-id="ea779-106">**Direction**</span></span>|<span data-ttu-id="ea779-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="ea779-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="ea779-108">0</span><span class="sxs-lookup"><span data-stu-id="ea779-108">0</span></span>  <br/> | <span data-ttu-id="ea779-109">水平</span><span class="sxs-lookup"><span data-stu-id="ea779-109">Horizontal</span></span>  <br/> |<span data-ttu-id="ea779-110">**visTxtBlkLeftToRight**</span><span class="sxs-lookup"><span data-stu-id="ea779-110">**visTxtBlkLeftToRight**</span></span> <br/> |
| <span data-ttu-id="ea779-111">1</span><span class="sxs-lookup"><span data-stu-id="ea779-111">1</span></span>  <br/> | <span data-ttu-id="ea779-112">垂直</span><span class="sxs-lookup"><span data-stu-id="ea779-112">Vertical</span></span>  <br/> |<span data-ttu-id="ea779-113">**visTxtBlkTopToBottom**</span><span class="sxs-lookup"><span data-stu-id="ea779-113">**visTxtBlkTopToBottom**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ea779-114">备注</span><span class="sxs-lookup"><span data-stu-id="ea779-114">Remarks</span></span>

<span data-ttu-id="ea779-115">在 Visio 5.0 日语版产品中，此单元格的值存储在“Miscellaneous”内容的 VerticalText 单元格中。</span><span class="sxs-lookup"><span data-stu-id="ea779-115">In Visio version 5.0 Japanese products, the value of this cell was stored in the VerticalText cell in the Miscellaneous section.</span></span>
  
<span data-ttu-id="ea779-116">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TextDirection 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ea779-116">To get a reference to the TextDirection cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea779-117">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ea779-117">Cell name:</span></span>  <br/> | <span data-ttu-id="ea779-118">TextDirection</span><span class="sxs-lookup"><span data-stu-id="ea779-118">TextDirection</span></span>  <br/> |
   
<span data-ttu-id="ea779-119">要从某个程序按索引获取对 TextDirection 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ea779-119">To get a reference to the TextDirection cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea779-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ea779-120">Section index:</span></span>  <br/> |<span data-ttu-id="ea779-121">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ea779-121">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ea779-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="ea779-122">Row index:</span></span>  <br/> |<span data-ttu-id="ea779-123">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="ea779-123">**visRowText**</span></span> <br/> |
| <span data-ttu-id="ea779-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ea779-124">Cell index:</span></span>  <br/> |<span data-ttu-id="ea779-125">**visTxtBlkDirection**</span><span class="sxs-lookup"><span data-stu-id="ea779-125">**visTxtBlkDirection**</span></span> <br/> |
   

