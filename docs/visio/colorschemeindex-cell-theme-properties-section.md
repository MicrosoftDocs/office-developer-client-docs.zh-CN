---
title: ColorSchemeIndex 单元格 ("主题属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fb84f71e-59c4-43d4-a28b-c3d6f267d2ae
description: 确定形状的配色方案在其后面采用的主题的索引 (作为整数)。
ms.openlocfilehash: d67363b48454a717914b8ff9e39952609d848118
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430761"
---
# <a name="colorschemeindex-cell-theme-properties-section"></a><span data-ttu-id="974bc-103">ColorSchemeIndex 单元格 ("主题属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="974bc-103">ColorSchemeIndex Cell (Theme Properties Section)</span></span>

<span data-ttu-id="974bc-104">确定形状的配色方案在其后面采用的主题的索引 (作为整数)。</span><span class="sxs-lookup"><span data-stu-id="974bc-104">Determines the index of the theme that the shape's color scheme takes after, as an integer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="974bc-105">说明</span><span class="sxs-lookup"><span data-stu-id="974bc-105">Remarks</span></span>

<span data-ttu-id="974bc-106">若要从另一个公式按名称获取对**ColorSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="974bc-106">To get a reference to the **ColorSchemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="974bc-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="974bc-107">Cell name:</span></span>  <br/> | <span data-ttu-id="974bc-108">ColorSchemeIndex</span><span class="sxs-lookup"><span data-stu-id="974bc-108">ColorSchemeIndex</span></span>  <br/> |
   
<span data-ttu-id="974bc-109">若要从某个程序按索引获取对**ColorSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="974bc-109">To get a reference to the **ColorSchemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="974bc-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="974bc-110">Section index:</span></span>  <br/> |<span data-ttu-id="974bc-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="974bc-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="974bc-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="974bc-112">Row index:</span></span>  <br/> |<span data-ttu-id="974bc-113">**visRowThemeProperties**</span><span class="sxs-lookup"><span data-stu-id="974bc-113">**visRowThemeProperties**</span></span> <br/> |
| <span data-ttu-id="974bc-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="974bc-114">Cell index:</span></span>  <br/> |<span data-ttu-id="974bc-115">**visColorSchemeIndex**</span><span class="sxs-lookup"><span data-stu-id="974bc-115">**visColorSchemeIndex**</span></span> <br/> |
   

