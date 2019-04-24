---
title: Type / C 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251723
localization_priority: Normal
ms.assetid: 2264d026-2041-3855-2b23-553ce67ae69d
description: 确定连接点类型。
ms.openlocfilehash: a73554d9f3a3bce6a039689d2c0b192a1c5b69aa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359582"
---
# <a name="type--c-cell-connection-points-section"></a><span data-ttu-id="e9e56-103">Type / C 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="e9e56-103">Type / C Cell (Connection Points Section)</span></span>

<span data-ttu-id="e9e56-104">确定连接点类型。</span><span class="sxs-lookup"><span data-stu-id="e9e56-104">Determines the connection point type.</span></span>
  
|<span data-ttu-id="e9e56-105">**值**</span><span class="sxs-lookup"><span data-stu-id="e9e56-105">**Value**</span></span>|<span data-ttu-id="e9e56-106">**类型**</span><span class="sxs-lookup"><span data-stu-id="e9e56-106">**Type**</span></span>|<span data-ttu-id="e9e56-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="e9e56-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9e56-108">0</span><span class="sxs-lookup"><span data-stu-id="e9e56-108">0</span></span>  <br/> |<span data-ttu-id="e9e56-109">拖动</span><span class="sxs-lookup"><span data-stu-id="e9e56-109">Inward</span></span>  <br/> |<span data-ttu-id="e9e56-110">**visCnnctTypeInward**</span><span class="sxs-lookup"><span data-stu-id="e9e56-110">**visCnnctTypeInward**</span></span> <br/> |
|<span data-ttu-id="e9e56-111">1</span><span class="sxs-lookup"><span data-stu-id="e9e56-111">1</span></span>  <br/> |<span data-ttu-id="e9e56-112">提</span><span class="sxs-lookup"><span data-stu-id="e9e56-112">Outward</span></span>  <br/> |<span data-ttu-id="e9e56-113">**visCnnctTypeOutward**</span><span class="sxs-lookup"><span data-stu-id="e9e56-113">**visCnnctTypeOutward**</span></span> <br/> |
|<span data-ttu-id="e9e56-114">双面</span><span class="sxs-lookup"><span data-stu-id="e9e56-114">2</span></span>  <br/> |<span data-ttu-id="e9e56-115">向&amp;外</span><span class="sxs-lookup"><span data-stu-id="e9e56-115">Inward &amp; Outward</span></span>  <br/> |<span data-ttu-id="e9e56-116">**visCnnctTypeInwardOutward**</span><span class="sxs-lookup"><span data-stu-id="e9e56-116">**visCnnctTypeInwardOutward**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e9e56-117">注解</span><span class="sxs-lookup"><span data-stu-id="e9e56-117">Remarks</span></span>

<span data-ttu-id="e9e56-p101">您也可以通过选择 **“连接线”** 工具，再选择一个形状，然后右键单击连接点，来设置连接点类型。若要完成此操作，需要在[开发工具](run-in-developer-mode-display-the-developer-tab.md)模式下运行。</span><span class="sxs-lookup"><span data-stu-id="e9e56-p101">You can also set the connection point type by choosing the **Connector** tool, selecting a shape, and then right-clicking a connection point. To do this, you need to run in [developer](run-in-developer-mode-display-the-developer-tab.md) mode.</span></span> 
  
<span data-ttu-id="e9e56-120">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type / C 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e9e56-120">To get a reference to the Type / C cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e9e56-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e9e56-121">Cell name:</span></span>  <br/> |<span data-ttu-id="e9e56-122">连接。键入 [ *i* ] where \*\* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="e9e56-122">Connections.Type[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e9e56-123">若要从某个程序按索引获取对 Type / C 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9e56-123">To get a reference to the Type / C cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e9e56-124">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e9e56-124">Section index:</span></span>  <br/> |<span data-ttu-id="e9e56-125">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="e9e56-125">**visSectionConnectionPts**</span></span> <br/> |
|<span data-ttu-id="e9e56-126">行索引：</span><span class="sxs-lookup"><span data-stu-id="e9e56-126">Row index:</span></span>  <br/> |<span data-ttu-id="e9e56-127">**visRowConnectionPts** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="e9e56-127">**visRowConnectionPts** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="e9e56-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e9e56-128">Cell index:</span></span>  <br/> |<span data-ttu-id="e9e56-129">**visCnnctType**(非扩展行)**visCnnctC**(扩展行)</span><span class="sxs-lookup"><span data-stu-id="e9e56-129">**visCnnctType** (non-extended rows) **visCnnctC** (extended rows)</span></span>  <br/> |
   
<span data-ttu-id="e9e56-130">有关扩展行和非扩展行的信息，请参见 Connection Points 行。</span><span class="sxs-lookup"><span data-stu-id="e9e56-130">For information about non-extended and extended rows, see Connection Points row.</span></span>
  

