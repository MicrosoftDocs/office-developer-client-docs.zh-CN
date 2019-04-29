---
title: QuickStyleFontMatrix 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 304ee083-e9c8-45df-b411-ba5e7db4c086
description: 确定每个快速样式的字体样式 (从1到6的整数)。
ms.openlocfilehash: 0708a243b001c7b4e03158b5a332a3166727cabc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407247"
---
# <a name="quickstylefontmatrix-cell-quick-style-section"></a><span data-ttu-id="b99cc-103">QuickStyleFontMatrix 单元格 ("快速样式" 部分)</span><span class="sxs-lookup"><span data-stu-id="b99cc-103">QuickStyleFontMatrix Cell (Quick Style Section)</span></span>

<span data-ttu-id="b99cc-104">确定每个快速样式的字体样式 (从1到6的整数)。</span><span class="sxs-lookup"><span data-stu-id="b99cc-104">Determines the style of the font for each Quick Style, as an integer from 1 to 6.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b99cc-105">说明</span><span class="sxs-lookup"><span data-stu-id="b99cc-105">Remarks</span></span>

<span data-ttu-id="b99cc-106">若要从另一个公式按名称获取对**QuickStyleFontMatrix**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="b99cc-106">To get a reference to the **QuickStyleFontMatrix** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b99cc-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="b99cc-107">Cell name:</span></span>  <br/> | <span data-ttu-id="b99cc-108">QuickStyleFontMatrix</span><span class="sxs-lookup"><span data-stu-id="b99cc-108">QuickStyleFontMatrix</span></span>  <br/> |
   
<span data-ttu-id="b99cc-109">若要从某个程序按索引获取对**QuickStyleFontMatrix**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="b99cc-109">To get a reference to the **QuickStyleFontMatrix** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="b99cc-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="b99cc-110">Section index:</span></span>  <br/> |<span data-ttu-id="b99cc-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b99cc-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="b99cc-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="b99cc-112">Row index:</span></span>  <br/> |<span data-ttu-id="b99cc-113">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="b99cc-113">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="b99cc-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="b99cc-114">Cell index:</span></span>  <br/> |<span data-ttu-id="b99cc-115">**visQuickStyleFontMatrix**</span><span class="sxs-lookup"><span data-stu-id="b99cc-115">**visQuickStyleFontMatrix**</span></span> <br/> |
   

