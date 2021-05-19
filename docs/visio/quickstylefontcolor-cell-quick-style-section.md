---
title: 'QuickStyleFontColor Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31c56d08-19ea-4b8b-8be7-42e1c736fbca
description: 确定形状的文本从活动主题继承的快速样式中的字体颜色，作为 0-1 的整数。
ms.openlocfilehash: bd645383df02260fcf6a2045764d9a1b44126090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415024"
---
# <a name="quickstylefontcolor-cell-quick-style-section"></a><span data-ttu-id="ea28b-103">QuickStyleFontColor Cell (Quick Style Section) </span><span class="sxs-lookup"><span data-stu-id="ea28b-103">QuickStyleFontColor Cell (Quick Style Section)</span></span>

<span data-ttu-id="ea28b-104">确定形状的文本从活动主题继承的快速样式中的字体颜色，作为 0-1 的整数。</span><span class="sxs-lookup"><span data-stu-id="ea28b-104">Determines the font color from the Quick Styles that a shape's text inherits from the active theme, as an integer from 0-1.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ea28b-105">值</span><span class="sxs-lookup"><span data-stu-id="ea28b-105">Value</span></span>  <br/> |<span data-ttu-id="ea28b-106">说明</span><span class="sxs-lookup"><span data-stu-id="ea28b-106">Description</span></span>  <br/> |
|<span data-ttu-id="ea28b-107">0</span><span class="sxs-lookup"><span data-stu-id="ea28b-107">0</span></span>  <br/> |<span data-ttu-id="ea28b-108">形状文本使用深色字体颜色。</span><span class="sxs-lookup"><span data-stu-id="ea28b-108">The shape text uses the Dark font color.</span></span>  <br/> |
|<span data-ttu-id="ea28b-109">1</span><span class="sxs-lookup"><span data-stu-id="ea28b-109">1</span></span>  <br/> |<span data-ttu-id="ea28b-110">形状文本使用浅色字体颜色。</span><span class="sxs-lookup"><span data-stu-id="ea28b-110">The shape text uses the Light font color.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ea28b-111">备注</span><span class="sxs-lookup"><span data-stu-id="ea28b-111">Remarks</span></span>

<span data-ttu-id="ea28b-112">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **QuickStyleFontColor** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ea28b-112">To get a reference to the **QuickStyleFontColor** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea28b-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ea28b-113">Cell name:</span></span>  <br/> | <span data-ttu-id="ea28b-114">QuickStyleFontColor</span><span class="sxs-lookup"><span data-stu-id="ea28b-114">QuickStyleFontColor</span></span>  <br/> |
   
<span data-ttu-id="ea28b-115">若要从程序按索引获取对 **QuickStyleFontColor** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ea28b-115">To get a reference to the **QuickStyleFontColor** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ea28b-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ea28b-116">Section index:</span></span>  <br/> |<span data-ttu-id="ea28b-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ea28b-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ea28b-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="ea28b-118">Row index:</span></span>  <br/> |<span data-ttu-id="ea28b-119">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="ea28b-119">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="ea28b-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ea28b-120">Cell index:</span></span>  <br/> |<span data-ttu-id="ea28b-121">**visQuickStyleFontColor**</span><span class="sxs-lookup"><span data-stu-id="ea28b-121">**visQuickStyleFontColor**</span></span> <br/> |
   

