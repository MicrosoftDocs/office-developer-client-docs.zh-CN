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
ms.openlocfilehash: 12c953a160ab99aad007e9b2bb9089d651aee553
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781577"
---
# <a name="type--c-cell-connection-points-section"></a><span data-ttu-id="6cbf8-103">Type / C 单元格（“Connection Points”内容）</span><span class="sxs-lookup"><span data-stu-id="6cbf8-103">Type / C Cell (Connection Points Section)</span></span>

<span data-ttu-id="6cbf8-104">确定连接点类型。</span><span class="sxs-lookup"><span data-stu-id="6cbf8-104">Determines the connection point type.</span></span>
  
|<span data-ttu-id="6cbf8-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-105">**Value**</span></span>|<span data-ttu-id="6cbf8-106">**类型**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-106">**Type**</span></span>|<span data-ttu-id="6cbf8-107">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6cbf8-108">0</span><span class="sxs-lookup"><span data-stu-id="6cbf8-108">0</span></span>  <br/> |<span data-ttu-id="6cbf8-109">向内</span><span class="sxs-lookup"><span data-stu-id="6cbf8-109">Inward</span></span>  <br/> |<span data-ttu-id="6cbf8-110">**visCnnctTypeInward**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-110">**visCnnctTypeInward**</span></span> <br/> |
|<span data-ttu-id="6cbf8-111">1</span><span class="sxs-lookup"><span data-stu-id="6cbf8-111">1</span></span>  <br/> |<span data-ttu-id="6cbf8-112">向外</span><span class="sxs-lookup"><span data-stu-id="6cbf8-112">Outward</span></span>  <br/> |<span data-ttu-id="6cbf8-113">**visCnnctTypeOutward**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-113">**visCnnctTypeOutward**</span></span> <br/> |
|<span data-ttu-id="6cbf8-114">2</span><span class="sxs-lookup"><span data-stu-id="6cbf8-114">2</span></span>  <br/> |<span data-ttu-id="6cbf8-115">向内&amp;向外</span><span class="sxs-lookup"><span data-stu-id="6cbf8-115">Inward &amp; Outward</span></span>  <br/> |<span data-ttu-id="6cbf8-116">**visCnnctTypeInwardOutward**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-116">**visCnnctTypeInwardOutward**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6cbf8-117">备注</span><span class="sxs-lookup"><span data-stu-id="6cbf8-117">Remarks</span></span>

<span data-ttu-id="6cbf8-118">您还可以通过选择**连接器**工具，选择一个形状，然后右键单击连接点设置连接点类型。</span><span class="sxs-lookup"><span data-stu-id="6cbf8-118">You can also set the connection point type by choosing the **Connector** tool, selecting a shape, and then right-clicking a connection point.</span></span> <span data-ttu-id="6cbf8-119">若要执行此操作，您需要以[开发人员](run-in-developer-mode-display-the-developer-tab.md)模式运行。</span><span class="sxs-lookup"><span data-stu-id="6cbf8-119">To do this, you need to run in [developer](run-in-developer-mode-display-the-developer-tab.md) mode.</span></span> 
  
<span data-ttu-id="6cbf8-120">若要获取的引用类型 / C 单元格按名称从另一个公式或从程序使用**CellsU**属性，使用：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-120">To get a reference to the Type / C cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6cbf8-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-121">Cell name:</span></span>  <br/> |<span data-ttu-id="6cbf8-122">Connections.Type [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="6cbf8-122">Connections.Type[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="6cbf8-123">若要获取的引用类型 / C 单元格从某个程序按索引使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-123">To get a reference to the Type / C cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6cbf8-124">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-124">Section index:</span></span>  <br/> |<span data-ttu-id="6cbf8-125">**visSectionConnectionPts**</span><span class="sxs-lookup"><span data-stu-id="6cbf8-125">**visSectionConnectionPts**</span></span> <br/> |
|<span data-ttu-id="6cbf8-126">行索引：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-126">Row index:</span></span>  <br/> |<span data-ttu-id="6cbf8-127">**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="6cbf8-127">**visRowConnectionPts** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="6cbf8-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6cbf8-128">Cell index:</span></span>  <br/> |<span data-ttu-id="6cbf8-129">**visCnnctType**（非扩展行）**visCnnctC**（扩展的行）</span><span class="sxs-lookup"><span data-stu-id="6cbf8-129">**visCnnctType** (non-extended rows) **visCnnctC** (extended rows)</span></span>  <br/> |
   
<span data-ttu-id="6cbf8-130">有关扩展行和非扩展行的信息，请参见 Connection Points 行。</span><span class="sxs-lookup"><span data-stu-id="6cbf8-130">For information about non-extended and extended rows, see Connection Points row.</span></span>
  

