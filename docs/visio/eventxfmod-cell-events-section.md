---
title: EventXFMod 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251313
localization_priority: Normal
ms.assetid: b88588a2-c651-7eab-9c7a-ed78f20d1ba3
description: 一种事件单元格形状的位置或方向在上的时计算的转换 (XF)。
ms.openlocfilehash: 5884aabc11798ae0440fbfa024b9cc2f2418b9cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780219"
---
# <a name="eventxfmod-cell-events-section"></a><span data-ttu-id="2168b-103">EventXFMod 单元格（“Events”部分）</span><span class="sxs-lookup"><span data-stu-id="2168b-103">EventXFMod Cell (Events Section)</span></span>

<span data-ttu-id="2168b-104">一种事件单元格，当形状的位置或方向在绘图页上发生变化时会对它求值（“XF”）。</span><span class="sxs-lookup"><span data-stu-id="2168b-104">An event cell that is evaluated when a shape's position or orientation on the page is transformed ("XF").</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2168b-105">注释</span><span class="sxs-lookup"><span data-stu-id="2168b-105">Remarks</span></span>

<span data-ttu-id="2168b-106">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="2168b-106">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="2168b-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EventXFMod 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2168b-107">To get a reference to the EventXFMod cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2168b-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2168b-108">Cell name:</span></span>  <br/> | <span data-ttu-id="2168b-109">EventXFMod</span><span class="sxs-lookup"><span data-stu-id="2168b-109">EventXFMod</span></span>  <br/> |
   
<span data-ttu-id="2168b-110">要从某个程序按索引获取对 EventXFMod 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2168b-110">To get a reference to the EventXFMod cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2168b-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2168b-111">Section index:</span></span>  <br/> |<span data-ttu-id="2168b-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2168b-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2168b-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="2168b-113">Row index:</span></span>  <br/> |<span data-ttu-id="2168b-114">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="2168b-114">**visRowEvent**</span></span> <br/> |
| <span data-ttu-id="2168b-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2168b-115">Cell index:</span></span>  <br/> |<span data-ttu-id="2168b-116">**visEvtCellXFMod**</span><span class="sxs-lookup"><span data-stu-id="2168b-116">**visEvtCellXFMod**</span></span> <br/> |
   

