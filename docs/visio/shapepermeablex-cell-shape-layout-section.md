---
title: ShapePermeableX 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm890
localization_priority: Normal
ms.assetid: 7e27b36c-4fd1-34e0-c168-f49eb5757b0e
description: 确定连接线是否可以水平穿绕可放置形状。
ms.openlocfilehash: 21fa1683c4b1afd24992ec7a8a6daa52a8280825
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357048"
---
# <a name="shapepermeablex-cell-shape-layout-section"></a><span data-ttu-id="2f8ff-103">ShapePermeableX 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="2f8ff-103">ShapePermeableX Cell (Shape Layout Section)</span></span>

<span data-ttu-id="2f8ff-104">确定连接线是否可以水平穿绕可放置形状。</span><span class="sxs-lookup"><span data-stu-id="2f8ff-104">Determines whether a connector can route horizontally through a placeable shape.</span></span>
  
|<span data-ttu-id="2f8ff-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="2f8ff-105">**Value**</span></span>|<span data-ttu-id="2f8ff-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2f8ff-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f8ff-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="2f8ff-107">TRUE</span></span>  <br/> |<span data-ttu-id="2f8ff-108">允许连接线水平穿绕可放置形状。</span><span class="sxs-lookup"><span data-stu-id="2f8ff-108">Enable connectors to route horizontally through a placeable shape.</span></span>  <br/> |
|<span data-ttu-id="2f8ff-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="2f8ff-109">FALSE</span></span>  <br/> |<span data-ttu-id="2f8ff-110">不允许连接线水平穿绕可放置形状。</span><span class="sxs-lookup"><span data-stu-id="2f8ff-110">Do not let connectors route horizontally through a placeable shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2f8ff-111">注解</span><span class="sxs-lookup"><span data-stu-id="2f8ff-111">Remarks</span></span>

<span data-ttu-id="2f8ff-112">您还可以在 "**行为**" 对话框 (在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击 "**位置**" 选项卡) 中的 "**放置**" 选项卡上设置此单元格的值。).</span><span class="sxs-lookup"><span data-stu-id="2f8ff-112">You can also set the value of this cell on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="2f8ff-113">在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。</span><span class="sxs-lookup"><span data-stu-id="2f8ff-113">In versions earlier than Visio 2000, you set this behavior by using the ObjInteract cell in the Miscellaneous section.</span></span> 
  
<span data-ttu-id="2f8ff-114">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePermeableX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-114">To get a reference to the ShapePermeableX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f8ff-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-115">Cell name:</span></span>  <br/> |<span data-ttu-id="2f8ff-116">ShapePermeableX</span><span class="sxs-lookup"><span data-stu-id="2f8ff-116">ShapePermeableX</span></span>  <br/> |
   
<span data-ttu-id="2f8ff-117">若要从某个程序按索引获取对 ShapePermeableX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-117">To get a reference to the ShapePermeableX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f8ff-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-118">Section index:</span></span>  <br/> |<span data-ttu-id="2f8ff-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2f8ff-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="2f8ff-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-120">Row index:</span></span>  <br/> |<span data-ttu-id="2f8ff-121">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="2f8ff-121">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="2f8ff-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2f8ff-122">Cell index:</span></span>  <br/> |<span data-ttu-id="2f8ff-123">**visSLOPermX**</span><span class="sxs-lookup"><span data-stu-id="2f8ff-123">**visSLOPermX**</span></span> <br/> |
   

