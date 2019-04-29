---
title: FontSchemeIndex 单元格 ("主题属性" 部分
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b832d75b-dac2-495f-b86e-d7fc5a484cab
description: 确定应用于形状的主题的字体方案, 以整数形式表示。
ms.openlocfilehash: 3a527b93b95f86dc1b9b92c931f3877ef28523ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420498"
---
# <a name="fontschemeindex-cell-theme-properties-section"></a><span data-ttu-id="15440-103">FontSchemeIndex 单元格 ("主题属性" 部分</span><span class="sxs-lookup"><span data-stu-id="15440-103">FontSchemeIndex Cell (Theme Properties Section</span></span>

<span data-ttu-id="15440-104">确定应用于形状的主题的字体方案, 以整数形式表示。</span><span class="sxs-lookup"><span data-stu-id="15440-104">Determines the font scheme of a theme that is applied to the shape, as an integer.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="15440-105">说明</span><span class="sxs-lookup"><span data-stu-id="15440-105">Remarks</span></span>

<span data-ttu-id="15440-106">若要从另一个公式按名称获取对**FontSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="15440-106">To get a reference to the **FontSchemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="15440-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="15440-107">Cell name:</span></span>  <br/> | <span data-ttu-id="15440-108">FontSchemeIndex</span><span class="sxs-lookup"><span data-stu-id="15440-108">FontSchemeIndex</span></span>  <br/> |
   
<span data-ttu-id="15440-109">若要从某个程序按索引获取对**FontSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="15440-109">To get a reference to the **FontSchemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="15440-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="15440-110">Section index:</span></span>  <br/> |<span data-ttu-id="15440-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="15440-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="15440-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="15440-112">Row index:</span></span>  <br/> |<span data-ttu-id="15440-113">**visRowThemeProperties**</span><span class="sxs-lookup"><span data-stu-id="15440-113">**visRowThemeProperties**</span></span> <br/> |
| <span data-ttu-id="15440-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="15440-114">Cell index:</span></span>  <br/> |<span data-ttu-id="15440-115">**visFontSchemeIndex**</span><span class="sxs-lookup"><span data-stu-id="15440-115">**visFontSchemeIndex**</span></span> <br/> |
   

