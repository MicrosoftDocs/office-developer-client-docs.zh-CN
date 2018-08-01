---
title: PagesY 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033790
localization_priority: Normal
ms.assetid: 396a0f3e-dbbb-3f5b-3c5d-f7dd454a765f
description: 确定从纵向适合绘图页的打印纸的数目。
ms.openlocfilehash: 1663fac8efdf06599d1e3c00d5eb0d00ec52e476
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780835"
---
# <a name="pagesy-cell-print-properties-section"></a><span data-ttu-id="e622b-103">PagesY 单元格（“Print Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="e622b-103">PagesY Cell (Print Properties Section)</span></span>

<span data-ttu-id="e622b-104">确定从纵向适合绘图页的打印纸的数目。</span><span class="sxs-lookup"><span data-stu-id="e622b-104">Determines the number of printer pages on which to fit the drawing page vertically.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e622b-105">注释</span><span class="sxs-lookup"><span data-stu-id="e622b-105">Remarks</span></span>

<span data-ttu-id="e622b-106">只有在 OnPage 单元格设置为 TRUE 后才使用此值。</span><span class="sxs-lookup"><span data-stu-id="e622b-106">This value is used only when the OnPage cell is set to TRUE.</span></span> 
  
<span data-ttu-id="e622b-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PagesY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e622b-107">To get a reference to the PagesY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e622b-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e622b-108">Cell name:</span></span>  <br/> | <span data-ttu-id="e622b-109">PagesY</span><span class="sxs-lookup"><span data-stu-id="e622b-109">PagesY</span></span>  <br/> |
   
<span data-ttu-id="e622b-110">要从某个程序按索引获取对 PagesY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e622b-110">To get a reference to the PagesY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e622b-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e622b-111">Section index:</span></span>  <br/> |<span data-ttu-id="e622b-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e622b-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e622b-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="e622b-113">Row index:</span></span>  <br/> |<span data-ttu-id="e622b-114">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="e622b-114">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="e622b-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e622b-115">Cell index:</span></span>  <br/> |<span data-ttu-id="e622b-116">**visPrintPropertiesPagesY**</span><span class="sxs-lookup"><span data-stu-id="e622b-116">**visPrintPropertiesPagesY**</span></span> <br/> |
   

