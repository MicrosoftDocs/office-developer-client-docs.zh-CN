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
ms.openlocfilehash: 1b7be63e3f21365231120c602d8edfe1dc727f88
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780838"
---
# <a name="pagetopmargin-cell-print-properties-section"></a><span data-ttu-id="7e67a-103">PageTopMargin 单元格（“Print Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="7e67a-103">PageTopMargin Cell (Print Properties Section)</span></span>

<span data-ttu-id="7e67a-104">指定打印页顶部的边距。</span><span class="sxs-lookup"><span data-stu-id="7e67a-104">Specifies the margin at the top of the printer page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7e67a-105">注释</span><span class="sxs-lookup"><span data-stu-id="7e67a-105">Remarks</span></span>

<span data-ttu-id="7e67a-p101">此值表示物理单位并且不受缩放单位或绘图单位的影响。例如，如果此单元格的值为 0.25 in.，那么，即使页面单位是英尺，此边距仍为 0.25 英寸。如果没有明确规定单位，则此值默认为页面单位。</span><span class="sxs-lookup"><span data-stu-id="7e67a-p101">This value represents physical units and is unaffected by scale or drawing units. For example, if this cell has a value of 0.25 in., this margin is 0.25 inch even if page units are feet. If units are not explicitly stated, this value defaults to page units.</span></span> 
  
<span data-ttu-id="7e67a-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageTopMargin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7e67a-109">To get a reference to the PageTopMargin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e67a-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7e67a-110">Cell name:</span></span>  <br/> | <span data-ttu-id="7e67a-111">PageTopMargin</span><span class="sxs-lookup"><span data-stu-id="7e67a-111">PageTopMargin</span></span>  <br/> |
   
<span data-ttu-id="7e67a-112">要从某个程序按索引获取对 PageTopMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7e67a-112">To get a reference to the PageTopMargin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e67a-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7e67a-113">Section index:</span></span>  <br/> |<span data-ttu-id="7e67a-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7e67a-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7e67a-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="7e67a-115">Row index:</span></span>  <br/> |<span data-ttu-id="7e67a-116">**visRowPrintProperties**</span><span class="sxs-lookup"><span data-stu-id="7e67a-116">**visRowPrintProperties**</span></span> <br/> |
| <span data-ttu-id="7e67a-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7e67a-117">Cell index:</span></span>  <br/> |<span data-ttu-id="7e67a-118">**visPrintPropertiesTopMargin**</span><span class="sxs-lookup"><span data-stu-id="7e67a-118">**visPrintPropertiesTopMargin**</span></span> <br/> |
   

