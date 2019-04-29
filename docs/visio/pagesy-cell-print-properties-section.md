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
ms.openlocfilehash: 43d4081439525c516d3da28b6c0e46e9273d85c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429780"
---
# <a name="pagesy-cell-print-properties-section"></a><span data-ttu-id="7b347-103">PagesY 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="7b347-103">PagesY Cell (Print Properties Section)</span></span>

<span data-ttu-id="7b347-104">确定从纵向适合绘图页的打印纸的数目。</span><span class="sxs-lookup"><span data-stu-id="7b347-104">Determines the number of printer pages on which to fit the drawing page vertically.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7b347-105">说明</span><span class="sxs-lookup"><span data-stu-id="7b347-105">Remarks</span></span>

<span data-ttu-id="7b347-106">只有在 OnPage 单元格设置为 TRUE 后才使用此值。</span><span class="sxs-lookup"><span data-stu-id="7b347-106">This value is used only when the OnPage cell is set to TRUE.</span></span> 
  
<span data-ttu-id="7b347-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PagesY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7b347-107">To get a reference to the PagesY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b347-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7b347-108">Cell name:</span></span>  <br/> | <span data-ttu-id="7b347-109">PagesY</span><span class="sxs-lookup"><span data-stu-id="7b347-109">PagesY</span></span>  <br/> |
   
<span data-ttu-id="7b347-110">要从某个程序按索引获取对 PagesY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7b347-110">To get a reference to the PagesY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b347-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7b347-111">Section index:</span></span>  <br/> |<span data-ttu-id="7b347-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7b347-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7b347-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="7b347-113">Row index:</span></span>  <br/> |<span data-ttu-id="7b347-114">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="7b347-114">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="7b347-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7b347-115">Cell index:</span></span>  <br/> |<span data-ttu-id="7b347-116">**visPrintPropertiesPagesY**</span><span class="sxs-lookup"><span data-stu-id="7b347-116">**visPrintPropertiesPagesY**</span></span> <br/> |
   

