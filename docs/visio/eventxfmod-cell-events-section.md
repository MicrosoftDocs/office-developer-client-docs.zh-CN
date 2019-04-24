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
description: 当形状在页面上的位置或方向被转换 (XF) 时计算的事件单元格。
ms.openlocfilehash: c4ed4ddd9b255a9a52fc81349b514dbd25772c98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350972"
---
# <a name="eventxfmod-cell-events-section"></a><span data-ttu-id="49fed-103">EventXFMod 单元格（“Events”内容）</span><span class="sxs-lookup"><span data-stu-id="49fed-103">EventXFMod Cell (Events Section)</span></span>

<span data-ttu-id="49fed-104">一种事件单元格，当形状的位置或方向在绘图页上发生变化时会对它求值（“XF”）。</span><span class="sxs-lookup"><span data-stu-id="49fed-104">An event cell that is evaluated when a shape's position or orientation on the page is transformed ("XF").</span></span>
  
## <a name="remarks"></a><span data-ttu-id="49fed-105">注解</span><span class="sxs-lookup"><span data-stu-id="49fed-105">Remarks</span></span>

<span data-ttu-id="49fed-106">只在事件发生后（而非输入公式后）才对事件单元格求值。</span><span class="sxs-lookup"><span data-stu-id="49fed-106">Event cells are evaluated only when the event occurs, not upon formula entry.</span></span>
  
<span data-ttu-id="49fed-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EventXFMod 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="49fed-107">To get a reference to the EventXFMod cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="49fed-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="49fed-108">Cell name:</span></span>  <br/> | <span data-ttu-id="49fed-109">EventXFMod</span><span class="sxs-lookup"><span data-stu-id="49fed-109">EventXFMod</span></span>  <br/> |
   
<span data-ttu-id="49fed-110">要从某个程序按索引获取对 EventXFMod 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="49fed-110">To get a reference to the EventXFMod cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="49fed-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="49fed-111">Section index:</span></span>  <br/> |<span data-ttu-id="49fed-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="49fed-112">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="49fed-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="49fed-113">Row index:</span></span>  <br/> |<span data-ttu-id="49fed-114">**visRowEvent**</span><span class="sxs-lookup"><span data-stu-id="49fed-114">**visRowEvent**</span></span> <br/> |
| <span data-ttu-id="49fed-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="49fed-115">Cell index:</span></span>  <br/> |<span data-ttu-id="49fed-116">**visEvtCellXFMod**</span><span class="sxs-lookup"><span data-stu-id="49fed-116">**visEvtCellXFMod**</span></span> <br/> |
   

