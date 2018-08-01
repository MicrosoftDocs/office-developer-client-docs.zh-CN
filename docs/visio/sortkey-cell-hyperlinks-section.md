---
title: SortKey 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60086
localization_priority: Normal
ms.assetid: 93d7b00c-bd34-6b4e-44fe-afeb8aa9a294
description: 确定超链接在快捷菜单上显示的顺序的数字。
ms.openlocfilehash: 03596918924b04a776eb7ffd2f16db1c57de8194
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781416"
---
# <a name="sortkey-cell-hyperlinks-section"></a><span data-ttu-id="56465-103">SortKey 单元格（“Hyperlinks”部分）</span><span class="sxs-lookup"><span data-stu-id="56465-103">SortKey Cell (Hyperlinks Section)</span></span>

<span data-ttu-id="56465-104">确定超链接在快捷菜单上显示的顺序的数字。</span><span class="sxs-lookup"><span data-stu-id="56465-104">A number that determines the order of hyperlinks that appear on a shortcut menu.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="56465-105">注解</span><span class="sxs-lookup"><span data-stu-id="56465-105">Remarks</span></span>

<span data-ttu-id="56465-p101">超链接按照从低到高的顺序在快捷菜单上显示，最低的数字显示在菜单的顶部。如果两个超链接行具有相同的 SortKey 单元格值，则顺序由物理行顺序确定。默认值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="56465-p101">The hyperlinks on a shortcut menu appear on the menu sorted from lowest to highest, with lower numbers appearing at the top of the menu. If two hyperlink rows have the same SortKey cell value, the order is determined by physical row order. The default is 0 (zero).</span></span> 
  
<span data-ttu-id="56465-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="56465-109">To get a reference to the SortKey cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56465-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="56465-110">Cell name:</span></span>  <br/> |<span data-ttu-id="56465-111">超链接。</span><span class="sxs-lookup"><span data-stu-id="56465-111">Hyperlink.</span></span> <span data-ttu-id="56465-112">*名称*。SortKey 其中超链接 *.name*是行名称</span><span class="sxs-lookup"><span data-stu-id="56465-112">*name*  .SortKey where Hyperlink  *.name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="56465-113">若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="56465-113">To get a reference to the SortKey cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56465-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="56465-114">Section index:</span></span>  <br/> |<span data-ttu-id="56465-115">**visSectionHyperlink**</span><span class="sxs-lookup"><span data-stu-id="56465-115">**visSectionHyperlink**</span></span> <br/> |
|<span data-ttu-id="56465-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="56465-116">Row index:</span></span>  <br/> |<span data-ttu-id="56465-117">**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="56465-117">**visRow1stHyperlink** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="56465-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="56465-118">Cell index:</span></span>  <br/> |<span data-ttu-id="56465-119">**visHLinkSortKey**</span><span class="sxs-lookup"><span data-stu-id="56465-119">**visHLinkSortKey**</span></span> <br/> |
   

