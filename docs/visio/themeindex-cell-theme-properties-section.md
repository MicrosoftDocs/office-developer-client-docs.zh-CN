---
title: ThemeIndex 单元格 (主题 Properties)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21002267-1400-4398-b937-f5b289cf0ed2
description: 存储内置 Microsoft Visio 主题应用于文档，作为整数的枚举。 当文档选择新主题时，文档和所有页面和形状及其包含的 ThemeIndex 单元格的内置的主题的索引的更新。
ms.openlocfilehash: 8a9202631bc4d9131d52dea1f852983e1d7528e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781505"
---
# <a name="themeindex-cell-theme-properties-section"></a><span data-ttu-id="51f82-104">ThemeIndex 单元格 (主题 Properties)</span><span class="sxs-lookup"><span data-stu-id="51f82-104">ThemeIndex Cell (Theme Properties Section)</span></span>

<span data-ttu-id="51f82-105">存储内置 Microsoft Visio 主题应用于文档，作为整数的枚举。</span><span class="sxs-lookup"><span data-stu-id="51f82-105">Stores the enumeration of the built-in Microsoft Visio theme applied to the document, as an integer.</span></span> <span data-ttu-id="51f82-106">当新主题选择文档，文档的**ThemeIndex**单元格和所有页面和它包含的形状的内置的主题的索引的都更新。</span><span class="sxs-lookup"><span data-stu-id="51f82-106">When a new theme is chosen for the document, the **ThemeIndex** cell for the document and all pages and shapes it contains is updated with the index of the built-in theme.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="51f82-107">备注</span><span class="sxs-lookup"><span data-stu-id="51f82-107">Remarks</span></span>

<span data-ttu-id="51f82-108">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ThemeIndex**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="51f82-108">To get a reference to the **ThemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="51f82-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="51f82-109">Cell name:</span></span>  <br/> | <span data-ttu-id="51f82-110">ThemeIndex</span><span class="sxs-lookup"><span data-stu-id="51f82-110">ThemeIndex</span></span>  <br/> |
   
<span data-ttu-id="51f82-111">若要从某个程序按索引获取对**ThemeIndex**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="51f82-111">To get a reference to the **ThemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="51f82-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="51f82-112">Section index:</span></span>  <br/> |<span data-ttu-id="51f82-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="51f82-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="51f82-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="51f82-114">Row index:</span></span>  <br/> |<span data-ttu-id="51f82-115">**visRowThemeProperties**</span><span class="sxs-lookup"><span data-stu-id="51f82-115">**visRowThemeProperties**</span></span> <br/> |
| <span data-ttu-id="51f82-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="51f82-116">Cell index:</span></span>  <br/> |<span data-ttu-id="51f82-117">**visThemeIndex**</span><span class="sxs-lookup"><span data-stu-id="51f82-117">**visThemeIndex**</span></span> <br/> |
   

