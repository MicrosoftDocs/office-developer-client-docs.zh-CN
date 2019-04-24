---
title: EventMultiDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f496d698-7f08-69cc-4379-df18a2c2fd7e
ms.openlocfilehash: caa86e33d0d7aa9ca31cbbf8939e17b581877669
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337189"
---
# <a name="eventmultidrop-cell-events-section"></a><span data-ttu-id="5da29-102">EventMultiDrop 单元格（“Events”内容）</span><span class="sxs-lookup"><span data-stu-id="5da29-102">EventMultiDrop Cell (Events Section)</span></span>

<span data-ttu-id="5da29-103">当多个形状作为实例放置在绘图页上或者在复制或粘贴形状时计算的事件单元格。</span><span class="sxs-lookup"><span data-stu-id="5da29-103">An event cell that is evaluated when multiple shapes are dropped on the drawing page, either as instances or when shapes are duplicated or pasted.</span></span>
  
<span data-ttu-id="5da29-104">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="5da29-104">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="5da29-105">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 EventMultiDrop 单元格，请使用：</span><span class="sxs-lookup"><span data-stu-id="5da29-105">To refer to the EventMultiDrop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5da29-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5da29-106">Cell name:</span></span>  <br/> |<span data-ttu-id="5da29-107">EventMultiDrop</span><span class="sxs-lookup"><span data-stu-id="5da29-107">EventMultiDrop</span></span>  <br/> |
   
<span data-ttu-id="5da29-108">若要从某个程序按索引引用 EventMultiDrop 单元格，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5da29-108">To refer to the EventMultiDrop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5da29-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5da29-109">Section index:</span></span>  <br/> |<span data-ttu-id="5da29-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5da29-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="5da29-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="5da29-111">Row index:</span></span>  <br/> |<span data-ttu-id="5da29-112">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="5da29-112">**visRowEvent**</span></span> <br/> |
|<span data-ttu-id="5da29-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5da29-113">Cell index:</span></span>  <br/> |<span data-ttu-id="5da29-114">**visEvtCellMultiDrop**</span><span class="sxs-lookup"><span data-stu-id="5da29-114">**visEvtCellMultiDrop**</span></span> <br/> |
   

