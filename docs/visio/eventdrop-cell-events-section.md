---
title: EventDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm350
localization_priority: Normal
ms.assetid: f84afe83-8391-0c13-f442-ea8794b38642
description: 一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。
ms.openlocfilehash: e2624c50896de061727003a48f7dc1559c6a72c4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780190"
---
# <a name="eventdrop-cell-events-section"></a><span data-ttu-id="7d2ac-103">EventDrop 单元格（“Events”内容）</span><span class="sxs-lookup"><span data-stu-id="7d2ac-103">EventDrop Cell (Events Section)</span></span>

<span data-ttu-id="7d2ac-104">一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。</span><span class="sxs-lookup"><span data-stu-id="7d2ac-104">An event cell that is evaluated when a shape is dropped on the drawing page, either as an instance or when the shape is duplicated or pasted.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7d2ac-105">注释</span><span class="sxs-lookup"><span data-stu-id="7d2ac-105">Remarks</span></span>

<span data-ttu-id="7d2ac-106">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="7d2ac-106">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="7d2ac-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 EventDrop 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-107">To get a reference to the EventDrop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7d2ac-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-108">Cell name:</span></span>  <br/> | <span data-ttu-id="7d2ac-109">EventDrop</span><span class="sxs-lookup"><span data-stu-id="7d2ac-109">EventDrop</span></span>  <br/> |
   
<span data-ttu-id="7d2ac-110">若要从某个程序按索引获取对 EventDrop 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-110">To get a reference to the EventDrop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7d2ac-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-111">Section index:</span></span>  <br/> |<span data-ttu-id="7d2ac-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7d2ac-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7d2ac-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-113">Row index:</span></span>  <br/> |<span data-ttu-id="7d2ac-114">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="7d2ac-114">**visRowEvent**</span></span> <br/> |
| <span data-ttu-id="7d2ac-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7d2ac-115">Cell index:</span></span>  <br/> |<span data-ttu-id="7d2ac-116">**visEvtCellDrop**</span><span class="sxs-lookup"><span data-stu-id="7d2ac-116">**visEvtCellDrop**</span></span> <br/> |
   

