---
title: ShapePermeableY 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251666
localization_priority: Normal
ms.assetid: 90701ecf-3d34-2eac-9ee9-7965e16c0f7c
description: 确定连接线是否可以垂直穿绕形状。
ms.openlocfilehash: 4a7a389ec1d753b8582b7ff0b921a615e582b1ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781261"
---
# <a name="shapepermeabley-cell-shape-layout-section"></a><span data-ttu-id="944bc-103">ShapePermeableY 单元格（“Shape Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="944bc-103">ShapePermeableY Cell (Shape Layout Section)</span></span>

<span data-ttu-id="944bc-104">确定连接线是否可以垂直穿绕形状。</span><span class="sxs-lookup"><span data-stu-id="944bc-104">Determines whether a connector can route vertically through a shape.</span></span>
  
|<span data-ttu-id="944bc-105">**值**</span><span class="sxs-lookup"><span data-stu-id="944bc-105">**Value**</span></span>|<span data-ttu-id="944bc-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="944bc-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="944bc-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="944bc-107">TRUE</span></span>  <br/> |<span data-ttu-id="944bc-108">允许连接线垂直穿绕形状。</span><span class="sxs-lookup"><span data-stu-id="944bc-108">Enable connectors to route vertically through a shape.</span></span>  <br/> |
|<span data-ttu-id="944bc-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="944bc-109">FALSE</span></span>  <br/> |<span data-ttu-id="944bc-110">不允许连接线垂直穿绕形状。</span><span class="sxs-lookup"><span data-stu-id="944bc-110">Do not let connectors route vertically through a shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="944bc-111">注解</span><span class="sxs-lookup"><span data-stu-id="944bc-111">Remarks</span></span>

<span data-ttu-id="944bc-112">您还可以在**行为**对话框中的**位置**选项卡上设置此单元格的值 （与选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，，然后单击**位置**选项卡).</span><span class="sxs-lookup"><span data-stu-id="944bc-112">You can also set the value of this cell on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="944bc-113">在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。</span><span class="sxs-lookup"><span data-stu-id="944bc-113">In versions earlier than Visio 2000, you set this behavior by using the ObjInteract cell in the Miscellaneous section.</span></span>
  
<span data-ttu-id="944bc-114">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePermeableY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="944bc-114">To get a reference to the ShapePermeableY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="944bc-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="944bc-115">Cell name:</span></span>  <br/> |<span data-ttu-id="944bc-116">ShapePermeableY</span><span class="sxs-lookup"><span data-stu-id="944bc-116">ShapePermeableY</span></span>  <br/> |
   
<span data-ttu-id="944bc-117">若要从某个程序按索引获取对 ShapePermeableY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="944bc-117">To get a reference to the ShapePermeableY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="944bc-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="944bc-118">Section index:</span></span>  <br/> |<span data-ttu-id="944bc-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="944bc-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="944bc-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="944bc-120">Row index:</span></span>  <br/> |<span data-ttu-id="944bc-121">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="944bc-121">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="944bc-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="944bc-122">Cell index:</span></span>  <br/> |<span data-ttu-id="944bc-123">**visSLOPermY**</span><span class="sxs-lookup"><span data-stu-id="944bc-123">**visSLOPermY**</span></span> <br/> |
   

