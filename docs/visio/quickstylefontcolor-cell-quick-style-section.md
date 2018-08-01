---
title: QuickStyleFontColor 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31c56d08-19ea-4b8b-8be7-42e1c736fbca
description: 确定从形状的文本为从 0 1 的整数继承的活动主题的快速样式的字体颜色。
ms.openlocfilehash: 8f2d77508dccffccf472f8ab80517e840f860541
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781001"
---
# <a name="quickstylefontcolor-cell-quick-style-section"></a><span data-ttu-id="53812-103">QuickStyleFontColor 单元格（“Quick Style”部分）</span><span class="sxs-lookup"><span data-stu-id="53812-103">QuickStyleFontColor Cell (Quick Style Section)</span></span>

<span data-ttu-id="53812-104">确定从形状的文本为从 0 1 的整数继承的活动主题的快速样式的字体颜色。</span><span class="sxs-lookup"><span data-stu-id="53812-104">Determines the font color from the Quick Styles that a shape's text inherits from the active theme, as an integer from 0-1.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="53812-105">值</span><span class="sxs-lookup"><span data-stu-id="53812-105">Value</span></span>  <br/> |<span data-ttu-id="53812-106">说明</span><span class="sxs-lookup"><span data-stu-id="53812-106">Description</span></span>  <br/> |
|<span data-ttu-id="53812-107">0</span><span class="sxs-lookup"><span data-stu-id="53812-107">0</span></span>  <br/> |<span data-ttu-id="53812-108">形状文本使用深色字体颜色。</span><span class="sxs-lookup"><span data-stu-id="53812-108">The shape text uses the Dark font color.</span></span>  <br/> |
|<span data-ttu-id="53812-109">1</span><span class="sxs-lookup"><span data-stu-id="53812-109">1</span></span>  <br/> |<span data-ttu-id="53812-110">形状文本使用浅字体颜色。</span><span class="sxs-lookup"><span data-stu-id="53812-110">The shape text uses the Light font color.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="53812-111">说明</span><span class="sxs-lookup"><span data-stu-id="53812-111">Remarks</span></span>

<span data-ttu-id="53812-112">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleFontColor**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="53812-112">To get a reference to the **QuickStyleFontColor** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="53812-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="53812-113">Cell name:</span></span>  <br/> | <span data-ttu-id="53812-114">QuickStyleFontColor</span><span class="sxs-lookup"><span data-stu-id="53812-114">QuickStyleFontColor</span></span>  <br/> |
   
<span data-ttu-id="53812-115">若要从某个程序按索引获取对**QuickStyleFontColor**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="53812-115">To get a reference to the **QuickStyleFontColor** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="53812-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="53812-116">Section index:</span></span>  <br/> |<span data-ttu-id="53812-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="53812-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="53812-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="53812-118">Row index:</span></span>  <br/> |<span data-ttu-id="53812-119">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="53812-119">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="53812-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="53812-120">Cell index:</span></span>  <br/> |<span data-ttu-id="53812-121">**visQuickStyleFontColor**</span><span class="sxs-lookup"><span data-stu-id="53812-121">**visQuickStyleFontColor**</span></span> <br/> |
   

