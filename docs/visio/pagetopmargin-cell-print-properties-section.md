---
title: PageTopMargin 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033785
localization_priority: Normal
ms.assetid: 2ba0fd22-65a6-6cb6-da00-08f391705544
description: 指定打印页顶部的边距。
ms.openlocfilehash: ff2bffffed39c5571386e792d2ffc8d20d6b291e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416578"
---
# <a name="pagetopmargin-cell-print-properties-section"></a><span data-ttu-id="0b8dc-103">PageTopMargin 单元格（“Print Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="0b8dc-103">PageTopMargin Cell (Print Properties Section)</span></span>

<span data-ttu-id="0b8dc-104">指定打印页顶部的边距。</span><span class="sxs-lookup"><span data-stu-id="0b8dc-104">Specifies the margin at the top of the printer page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0b8dc-105">备注</span><span class="sxs-lookup"><span data-stu-id="0b8dc-105">Remarks</span></span>

<span data-ttu-id="0b8dc-p101">此值表示物理单位并且不受缩放单位或绘图单位的影响。例如，如果此单元格的值为 0.25 in.，那么，即使页面单位是英尺，此边距仍为 0.25 英寸。如果没有明确规定单位，则此值默认为页面单位。</span><span class="sxs-lookup"><span data-stu-id="0b8dc-p101">This value represents physical units and is unaffected by scale or drawing units. For example, if this cell has a value of 0.25 in., this margin is 0.25 inch even if page units are feet. If units are not explicitly stated, this value defaults to page units.</span></span> 
  
<span data-ttu-id="0b8dc-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageTopMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-109">To get a reference to the PageTopMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0b8dc-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-110">Cell name:</span></span>  <br/> | <span data-ttu-id="0b8dc-111">PageTopMargin</span><span class="sxs-lookup"><span data-stu-id="0b8dc-111">PageTopMargin</span></span>  <br/> |
   
<span data-ttu-id="0b8dc-112">要从某个程序按索引获取对 PageTopMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-112">To get a reference to the PageTopMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0b8dc-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-113">Section index:</span></span>  <br/> |<span data-ttu-id="0b8dc-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0b8dc-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="0b8dc-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-115">Row index:</span></span>  <br/> |<span data-ttu-id="0b8dc-116">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="0b8dc-116">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="0b8dc-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0b8dc-117">Cell index:</span></span>  <br/> |<span data-ttu-id="0b8dc-118">**visPrintPropertiesTopMargin**</span><span class="sxs-lookup"><span data-stu-id="0b8dc-118">**visPrintPropertiesTopMargin**</span></span> <br/> |
   

