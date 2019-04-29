---
title: PagesX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60064
localization_priority: Normal
ms.assetid: a10bf4c2-24f4-4c53-39ba-2b8cd5b50d2c
description: 确定从横向适合绘图页的打印纸的数目。
ms.openlocfilehash: e912aef2277f5a7d2af5352897654ee986836c48
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438692"
---
# <a name="pagesx-cell-print-properties-section"></a><span data-ttu-id="8ab48-103">PagesX 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="8ab48-103">PagesX Cell (Print Properties Section)</span></span>

<span data-ttu-id="8ab48-104">确定从横向适合绘图页的打印纸的数目。</span><span class="sxs-lookup"><span data-stu-id="8ab48-104">Determines the number of printer pages on which to fit the drawing page horizontally.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8ab48-105">说明</span><span class="sxs-lookup"><span data-stu-id="8ab48-105">Remarks</span></span>

<span data-ttu-id="8ab48-106">只有在 OnPage 单元格设置为 TRUE 后才使用此值。</span><span class="sxs-lookup"><span data-stu-id="8ab48-106">This value is used only when the OnPage cell is set to TRUE.</span></span> 
  
<span data-ttu-id="8ab48-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PagesX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8ab48-107">To get a reference to the PagesX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ab48-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8ab48-108">Cell name:</span></span>  <br/> | <span data-ttu-id="8ab48-109">PagesX</span><span class="sxs-lookup"><span data-stu-id="8ab48-109">PagesX</span></span>  <br/> |
   
<span data-ttu-id="8ab48-110">要从某个程序按索引获取对 PagesX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8ab48-110">To get a reference to the PagesX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ab48-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8ab48-111">Section index:</span></span>  <br/> |<span data-ttu-id="8ab48-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8ab48-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8ab48-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="8ab48-113">Row index:</span></span>  <br/> |<span data-ttu-id="8ab48-114">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="8ab48-114">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="8ab48-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8ab48-115">Cell index:</span></span>  <br/> |<span data-ttu-id="8ab48-116">**visPrintPropertiesPagesX**</span><span class="sxs-lookup"><span data-stu-id="8ab48-116">**visPrintPropertiesPagesX**</span></span> <br/> |
   

