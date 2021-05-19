---
title: ShapePlowCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm900
localization_priority: Normal
ms.assetid: acf07fd7-6aa6-1a92-9b7a-bd6fea8a7cb2
description: 确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。
ms.openlocfilehash: 6e155103f7bfc70a78826297f441fc9ce78942ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423893"
---
# <a name="shapeplowcode-cell-shape-layout-section"></a><span data-ttu-id="f5468-103">ShapePlowCode 单元格（“Shape Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="f5468-103">ShapePlowCode Cell (Shape Layout Section)</span></span>

<span data-ttu-id="f5468-104">确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。</span><span class="sxs-lookup"><span data-stu-id="f5468-104">Determines whether this placeable shape moves away when you drop another placeable shape near this shape on the drawing page.</span></span>
  
|<span data-ttu-id="f5468-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f5468-105">**Value**</span></span>|<span data-ttu-id="f5468-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5468-106">**Description**</span></span>|<span data-ttu-id="f5468-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="f5468-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f5468-108">0</span><span class="sxs-lookup"><span data-stu-id="f5468-108">0</span></span>  <br/> |<span data-ttu-id="f5468-109">按页上指定绘制。</span><span class="sxs-lookup"><span data-stu-id="f5468-109">Plow as page specifies.</span></span>  <br/> |<span data-ttu-id="f5468-110">**visSLOPlowDefault**</span><span class="sxs-lookup"><span data-stu-id="f5468-110">**visSLOPlowDefault**</span></span> <br/> |
|<span data-ttu-id="f5468-111">1</span><span class="sxs-lookup"><span data-stu-id="f5468-111">1</span></span>  <br/> |<span data-ttu-id="f5468-112">不绘制任何形状。</span><span class="sxs-lookup"><span data-stu-id="f5468-112">Plow no shapes.</span></span>  <br/> |<span data-ttu-id="f5468-113">**visSLOPlowNever**</span><span class="sxs-lookup"><span data-stu-id="f5468-113">**visSLOPlowNever**</span></span> <br/> |
|<span data-ttu-id="f5468-114">2</span><span class="sxs-lookup"><span data-stu-id="f5468-114">2</span></span>  <br/> |<span data-ttu-id="f5468-115">绘制每一个形状。</span><span class="sxs-lookup"><span data-stu-id="f5468-115">Plow every shape.</span></span>  <br/> |<span data-ttu-id="f5468-116">**visSLOPlowAlways**</span><span class="sxs-lookup"><span data-stu-id="f5468-116">**visSLOPlowAlways**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f5468-117">备注</span><span class="sxs-lookup"><span data-stu-id="f5468-117">Remarks</span></span>

<span data-ttu-id="f5468-118">您还可以在"行为"对话框"放置"选项卡上设置此单元格的值，该单元格位于"行为"选项卡上 (（已选定形状）中，[](run-in-developer-mode-display-the-developer-tab.md)在"开发工具"选项卡上的"形状设计"组中，单击"行为"，然后单击"放置"选项卡) 。  </span><span class="sxs-lookup"><span data-stu-id="f5468-118">You can also set the value of this cell for a particular shape on the **Placement** tab in the **Behavior** dialog box (with a shape selected, on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, in the **Shape Design** group, click **Behavior**, and then click the **Placement** tab).</span></span> 
  
<span data-ttu-id="f5468-119">若要为绘图页上  *的所有*  形状设置此行为，请使用"页面布局"部分中的 PlowCode 单元格。</span><span class="sxs-lookup"><span data-stu-id="f5468-119">To set this behavior for  *all*  the shapes on the drawing page, use the PlowCode cell in the Page Layout section.</span></span> 
  
<span data-ttu-id="f5468-120">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePlowCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f5468-120">To get a reference to the ShapePlowCode cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5468-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f5468-121">Cell name:</span></span>  <br/> |<span data-ttu-id="f5468-122">ShapePlowCode</span><span class="sxs-lookup"><span data-stu-id="f5468-122">ShapePlowCode</span></span>  <br/> |
   
<span data-ttu-id="f5468-123">若要从某个程序按索引获取对 ShapePlowCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f5468-123">To get a reference to the ShapePlowCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5468-124">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f5468-124">Section index:</span></span>  <br/> |<span data-ttu-id="f5468-125">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f5468-125">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f5468-126">行索引：</span><span class="sxs-lookup"><span data-stu-id="f5468-126">Row index:</span></span>  <br/> |<span data-ttu-id="f5468-127">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="f5468-127">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="f5468-128">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f5468-128">Cell index:</span></span>  <br/> |<span data-ttu-id="f5468-129">**visSLOPlowCode**</span><span class="sxs-lookup"><span data-stu-id="f5468-129">**visSLOPlowCode**</span></span> <br/> |
   

