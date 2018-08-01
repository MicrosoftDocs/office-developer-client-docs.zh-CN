---
title: EventMultiDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f496d698-7f08-69cc-4379-df18a2c2fd7e
ms.openlocfilehash: e44cd18c3f7673761f457db9cd4bfe00a8ab89bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780207"
---
# <a name="eventmultidrop-cell-events-section"></a><span data-ttu-id="27107-102">EventMultiDrop 单元格（“Events”部分）</span><span class="sxs-lookup"><span data-stu-id="27107-102">EventMultiDrop Cell (Events Section)</span></span>

<span data-ttu-id="27107-103">一种事件单元格的多个形状放在绘图页上，或者作为实例时复制或粘贴形状时计算。</span><span class="sxs-lookup"><span data-stu-id="27107-103">An event cell that is evaluated when multiple shapes are dropped on the drawing page, either as instances or when shapes are duplicated or pasted.</span></span>
  
<span data-ttu-id="27107-104">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="27107-104">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="27107-105">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 EventMultiDrop 单元格，请使用：

</span><span class="sxs-lookup"><span data-stu-id="27107-105">To refer to the EventMultiDrop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="27107-106">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="27107-106">Cell name:</span></span>  <br/> |<span data-ttu-id="27107-107">EventMultiDrop</span><span class="sxs-lookup"><span data-stu-id="27107-107">EventMultiDrop</span></span>  <br/> |
   
<span data-ttu-id="27107-108">若要从某个程序按索引引用 EventMultiDrop 单元格，请使用带下列参数的 **CellsSRC** 属性：

</span><span class="sxs-lookup"><span data-stu-id="27107-108">To refer to the EventMultiDrop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="27107-109">内容索引：</span><span class="sxs-lookup"><span data-stu-id="27107-109">Section index:</span></span>  <br/> |<span data-ttu-id="27107-110">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="27107-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="27107-111">行索引：</span><span class="sxs-lookup"><span data-stu-id="27107-111">Row index:</span></span>  <br/> |<span data-ttu-id="27107-112">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="27107-112">**visRowEvent**</span></span> <br/> |
|<span data-ttu-id="27107-113">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="27107-113">Cell index:</span></span>  <br/> |<span data-ttu-id="27107-114">**visEvtCellMultiDrop**</span><span class="sxs-lookup"><span data-stu-id="27107-114">**visEvtCellMultiDrop**</span></span> <br/> |
   

