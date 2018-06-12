---
title: ShapePermeablePlace 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm885
localization_priority: Normal
ms.assetid: b647cbb5-2769-068d-bbda-2dc983c47ac9
description: 确定是否可放置形状时，可放置在形状的顶部排放形状在配置布局对话框 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: 1873575eb4322d31f81c0dd34557c6167750ce82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781264"
---
# <a name="shapepermeableplace-cell-shape-layout-section"></a><span data-ttu-id="1b9d6-103">ShapePermeablePlace 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="1b9d6-103">ShapePermeablePlace Cell (Shape Layout Section)</span></span>

<span data-ttu-id="1b9d6-104">确定是否可放置形状时，可放置在形状的顶部排放形状在**配置布局**对话框 （**设计**选项卡上，在**布局**组中，单击**Re 布局页**，然后单击**更多布局选项**).</span><span class="sxs-lookup"><span data-stu-id="1b9d6-104">Determines whether placeable shapes can be placed on top of a shape when laying out shapes in the **Configure Layout** dialog box (on the **Design** tab, in the **Layout** group, click **Re-Layout Page**, and then click **More Layout Options**).</span></span>
  
|<span data-ttu-id="1b9d6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="1b9d6-105">**Value**</span></span>|<span data-ttu-id="1b9d6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="1b9d6-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b9d6-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="1b9d6-107">TRUE</span></span>  <br/> |<span data-ttu-id="1b9d6-108">使形状能够放置在某个形状的顶部。</span><span class="sxs-lookup"><span data-stu-id="1b9d6-108">Enable shapes to be placed on top of a shape.</span></span>  <br/> |
|<span data-ttu-id="1b9d6-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="1b9d6-109">FALSE</span></span>  <br/> |<span data-ttu-id="1b9d6-110">使形状不能放置在某个形状的顶部。</span><span class="sxs-lookup"><span data-stu-id="1b9d6-110">Do not enable shapes to be placed on top of a shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1b9d6-111">注解</span><span class="sxs-lookup"><span data-stu-id="1b9d6-111">Remarks</span></span>

<span data-ttu-id="1b9d6-112">您还可以在**行为**对话框中的**位置**选项卡上设置此单元格的值 （与选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，，然后单击**位置**选项卡).</span><span class="sxs-lookup"><span data-stu-id="1b9d6-112">You can also set the value of this cell on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="1b9d6-113">在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。</span><span class="sxs-lookup"><span data-stu-id="1b9d6-113">In versions earlier than Visio 2000, you set this behavior using the ObjInteract cell in the Miscellaneous section.</span></span>
  
<span data-ttu-id="1b9d6-114">若要获取对 ShapePermeablePlace 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-114">To get a reference to the ShapePermeablePlace cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1b9d6-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-115">Cell name:</span></span>  <br/> |<span data-ttu-id="1b9d6-116">ShapePermeablePlace</span><span class="sxs-lookup"><span data-stu-id="1b9d6-116">ShapePermeablePlace</span></span>  <br/> |
   
<span data-ttu-id="1b9d6-117">若要从某个程序按索引获取对 ShapePermeablePlace 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-117">To get a reference to the ShapePermeablePlace cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1b9d6-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-118">Section index:</span></span>  <br/> |<span data-ttu-id="1b9d6-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1b9d6-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="1b9d6-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-120">Row index:</span></span>  <br/> |<span data-ttu-id="1b9d6-121">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="1b9d6-121">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="1b9d6-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1b9d6-122">Cell index:</span></span>  <br/> |<span data-ttu-id="1b9d6-123">**visSLOPermeablePlace**</span><span class="sxs-lookup"><span data-stu-id="1b9d6-123">**visSLOPermeablePlace**</span></span> <br/> |
   

