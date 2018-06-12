---
title: EventDblClick 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251312
localization_priority: Normal
ms.assetid: ca949013-f998-1bce-39e5-ac6f68ab2392
description: 一种事件单元格，双击某个形状后会对其求值。
ms.openlocfilehash: 623d1d095d3269cd9c82fa8d0d6601933a163f92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780192"
---
# <a name="eventdblclick-cell-events-section"></a><span data-ttu-id="ed553-103">EventDblClick 单元格（“Events”内容）</span><span class="sxs-lookup"><span data-stu-id="ed553-103">EventDblClick Cell (Events Section)</span></span>

<span data-ttu-id="ed553-104">一种事件单元格，双击某个形状后会对其求值。</span><span class="sxs-lookup"><span data-stu-id="ed553-104">An event cell that is evaluated when a shape is double-clicked.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ed553-105">注释</span><span class="sxs-lookup"><span data-stu-id="ed553-105">Remarks</span></span>

<span data-ttu-id="ed553-106">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="ed553-106">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="ed553-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 EventDblClick 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ed553-107">To get a reference to the EventDblClick cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ed553-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ed553-108">Cell name:</span></span>  <br/> | <span data-ttu-id="ed553-109">EventDblClick</span><span class="sxs-lookup"><span data-stu-id="ed553-109">EventDblClick</span></span>  <br/> |
   
<span data-ttu-id="ed553-110">若要从某个程序按索引获取对 EventDblClick 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="ed553-110">To get a reference to the EventDblClick cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ed553-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ed553-111">Section index:</span></span>  <br/> |<span data-ttu-id="ed553-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ed553-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ed553-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="ed553-113">Row index:</span></span>  <br/> |<span data-ttu-id="ed553-114">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="ed553-114">**visRowEvent**</span></span> <br/> |
| <span data-ttu-id="ed553-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ed553-115">Cell index:</span></span>  <br/> |<span data-ttu-id="ed553-116">**visEvtCellDblClick**</span><span class="sxs-lookup"><span data-stu-id="ed553-116">**visEvtCellDblClick**</span></span> <br/> |
   

