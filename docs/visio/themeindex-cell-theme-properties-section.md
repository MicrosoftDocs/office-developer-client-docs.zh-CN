---
title: ThemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21002267-1400-4398-b937-f5b289cf0ed2
description: 将应用于文档的内置 Microsoft Visio 主题的枚举存储为一个整数。 为文档选择新主题时, 将使用内置主题的索引更新文档的 ThemeIndex 单元格以及它包含的所有页面和形状。
ms.openlocfilehash: 6ddede864a54fbd7127552499d3ee1ae3d36efc1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411909"
---
# <a name="themeindex-cell-theme-properties-section"></a><span data-ttu-id="42dd7-104">ThemeIndex 单元格 ("主题属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="42dd7-104">ThemeIndex Cell (Theme Properties Section)</span></span>

<span data-ttu-id="42dd7-105">将应用于文档的内置 Microsoft Visio 主题的枚举存储为一个整数。</span><span class="sxs-lookup"><span data-stu-id="42dd7-105">Stores the enumeration of the built-in Microsoft Visio theme applied to the document, as an integer.</span></span> <span data-ttu-id="42dd7-106">为文档选择新主题时, 将使用内置主题的索引更新文档的**ThemeIndex**单元格以及它包含的所有页面和形状。</span><span class="sxs-lookup"><span data-stu-id="42dd7-106">When a new theme is chosen for the document, the **ThemeIndex** cell for the document and all pages and shapes it contains is updated with the index of the built-in theme.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="42dd7-107">说明</span><span class="sxs-lookup"><span data-stu-id="42dd7-107">Remarks</span></span>

<span data-ttu-id="42dd7-108">若要从另一个公式按名称获取对**ThemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="42dd7-108">To get a reference to the **ThemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="42dd7-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="42dd7-109">Cell name:</span></span>  <br/> | <span data-ttu-id="42dd7-110">ThemeIndex</span><span class="sxs-lookup"><span data-stu-id="42dd7-110">ThemeIndex</span></span>  <br/> |
   
<span data-ttu-id="42dd7-111">若要从某个程序按索引获取对**ThemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="42dd7-111">To get a reference to the **ThemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="42dd7-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="42dd7-112">Section index:</span></span>  <br/> |<span data-ttu-id="42dd7-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="42dd7-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="42dd7-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="42dd7-114">Row index:</span></span>  <br/> |<span data-ttu-id="42dd7-115">**visRowThemeProperties**</span><span class="sxs-lookup"><span data-stu-id="42dd7-115">**visRowThemeProperties**</span></span> <br/> |
| <span data-ttu-id="42dd7-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="42dd7-116">Cell index:</span></span>  <br/> |<span data-ttu-id="42dd7-117">**visThemeIndex**</span><span class="sxs-lookup"><span data-stu-id="42dd7-117">**visThemeIndex**</span></span> <br/> |
   

