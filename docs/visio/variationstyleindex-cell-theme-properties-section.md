---
title: VariationStyleIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 932195d5-2cb7-49f7-bc64-4ce00bf780b2
description: 以整数形式确定页面上活动主题变体的样式索引。
ms.openlocfilehash: 57d4b2493b7278064daf7b0cb986e58ebacf4be2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355886"
---
# <a name="variationstyleindex-cell-theme-properties-section"></a><span data-ttu-id="85469-103">VariationStyleIndex 单元格 ("主题属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="85469-103">VariationStyleIndex Cell (Theme Properties Section)</span></span>

<span data-ttu-id="85469-104">以整数形式确定页面上活动主题变体的样式索引。</span><span class="sxs-lookup"><span data-stu-id="85469-104">Determines the style index of the active theme variation on the page, as an integer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="85469-105">注解</span><span class="sxs-lookup"><span data-stu-id="85469-105">Remarks</span></span>

<span data-ttu-id="85469-106">若要从另一个公式按名称获取对**VariationStyleIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="85469-106">To get a reference to the **VariationStyleIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="85469-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="85469-107">Cell name:</span></span>  <br/> | <span data-ttu-id="85469-108">VariationStyleIndex</span><span class="sxs-lookup"><span data-stu-id="85469-108">VariationStyleIndex</span></span>  <br/> |
   
<span data-ttu-id="85469-109">若要从某个程序按索引获取对**VariationStyleIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="85469-109">To get a reference to the **VariationStyleIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="85469-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="85469-110">Section index:</span></span>  <br/> |<span data-ttu-id="85469-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="85469-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="85469-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="85469-112">Row index:</span></span>  <br/> |<span data-ttu-id="85469-113">**visRowThemeProperties**</span><span class="sxs-lookup"><span data-stu-id="85469-113">**visRowThemeProperties**</span></span> <br/> |
| <span data-ttu-id="85469-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="85469-114">Cell index:</span></span>  <br/> |<span data-ttu-id="85469-115">**visVariationStyleIndex**</span><span class="sxs-lookup"><span data-stu-id="85469-115">**visVariationStyleIndex**</span></span> <br/> |
   

