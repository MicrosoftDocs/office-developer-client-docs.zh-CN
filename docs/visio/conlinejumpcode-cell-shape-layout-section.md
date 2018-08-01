---
title: ConLineJumpCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251652
localization_priority: Normal
ms.assetid: af85588e-8e83-5168-7a8c-d7e8b4af5c27
description: 确定连接线何时跨线。
ms.openlocfilehash: 002f628841356ec8a22afbb9d4aeca8236058222
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779958"
---
# <a name="conlinejumpcode-cell-shape-layout-section"></a><span data-ttu-id="7e297-103">ConLineJumpCode 单元格（“Shape Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="7e297-103">ConLineJumpCode Cell (Shape Layout Section)</span></span>

<span data-ttu-id="7e297-104">确定连接线何时跨线。</span><span class="sxs-lookup"><span data-stu-id="7e297-104">Determines when a connector jumps.</span></span>
  
|<span data-ttu-id="7e297-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7e297-105">**Value**</span></span>|<span data-ttu-id="7e297-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e297-106">**Description**</span></span>|<span data-ttu-id="7e297-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="7e297-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e297-108">0</span><span class="sxs-lookup"><span data-stu-id="7e297-108">0</span></span>  <br/> |<span data-ttu-id="7e297-109">
          按照页面上指定的那样：在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，然后单击 **“布局与排列”** 选项卡，查看页面规格
</span><span class="sxs-lookup"><span data-stu-id="7e297-109">As page specifies; on the **Design** tab, click the arrow in the **Page Setup** group, and then click the **Layout and Routing** tab to see the page specifications</span></span>  <br/> |<span data-ttu-id="7e297-110">**visSLOJumpDefault**</span><span class="sxs-lookup"><span data-stu-id="7e297-110">**visSLOJumpDefault**</span></span> <br/> |
|<span data-ttu-id="7e297-111">1</span><span class="sxs-lookup"><span data-stu-id="7e297-111">1</span></span>  <br/> |<span data-ttu-id="7e297-112">从不</span><span class="sxs-lookup"><span data-stu-id="7e297-112">Never</span></span>  <br/> |<span data-ttu-id="7e297-113">**visSLOJumpNever**</span><span class="sxs-lookup"><span data-stu-id="7e297-113">**visSLOJumpNever**</span></span> <br/> |
|<span data-ttu-id="7e297-114">2</span><span class="sxs-lookup"><span data-stu-id="7e297-114">2</span></span>  <br/> |<span data-ttu-id="7e297-115">两者都显示</span><span class="sxs-lookup"><span data-stu-id="7e297-115">Always</span></span>  <br/> |<span data-ttu-id="7e297-116">**visSLOJumpAlways**</span><span class="sxs-lookup"><span data-stu-id="7e297-116">**visSLOJumpAlways**</span></span> <br/> |
|<span data-ttu-id="7e297-117">3</span><span class="sxs-lookup"><span data-stu-id="7e297-117">3</span></span>  <br/> |<span data-ttu-id="7e297-118">其他连接线跨线</span><span class="sxs-lookup"><span data-stu-id="7e297-118">Other connector jumps</span></span>  <br/> |<span data-ttu-id="7e297-119">**visSLOJumpOther**</span><span class="sxs-lookup"><span data-stu-id="7e297-119">**visSLOJumpOther**</span></span> <br/> |
|<span data-ttu-id="7e297-120">4</span><span class="sxs-lookup"><span data-stu-id="7e297-120">4</span></span>  <br/> |<span data-ttu-id="7e297-121">
          两条连接线都不跨线
</span><span class="sxs-lookup"><span data-stu-id="7e297-121">Neither connector jumps</span></span>  <br/> |<span data-ttu-id="7e297-122">**visSLOJumpNeither**</span><span class="sxs-lookup"><span data-stu-id="7e297-122">**visSLOJumpNeither**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e297-123">说明</span><span class="sxs-lookup"><span data-stu-id="7e297-123">Remarks</span></span>

<span data-ttu-id="7e297-124">您还可以设置此单元格的值选择动态连接线，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡上的**形状设计**组中单击**行为**，然后单击**连接器**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7e297-124">You can also set the value of this cell by selecting a dynamic connector, clicking **Behavior** in the **Shape Design** group on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then clicking the **Connector** tab.</span></span> 
  
<span data-ttu-id="7e297-125">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpCode 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7e297-125">To get a reference to the ConLineJumpCode cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7e297-126">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7e297-126">Cell name:</span></span>  <br/> |<span data-ttu-id="7e297-127">ConLineJumpCode</span><span class="sxs-lookup"><span data-stu-id="7e297-127">ConLineJumpCode</span></span>  <br/> |
   
<span data-ttu-id="7e297-128">若要从某个程序按索引获取对 ConLineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7e297-128">To get a reference to the ConLineJumpCode cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7e297-129">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7e297-129">Section index:</span></span>  <br/> |<span data-ttu-id="7e297-130">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7e297-130">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="7e297-131">行索引：</span><span class="sxs-lookup"><span data-stu-id="7e297-131">Row index:</span></span>  <br/> |<span data-ttu-id="7e297-132">**visRowShapeLayout**</span><span class="sxs-lookup"><span data-stu-id="7e297-132">**visRowShapeLayout**</span></span> <br/> |
|<span data-ttu-id="7e297-133">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7e297-133">Cell index:</span></span>  <br/> |<span data-ttu-id="7e297-134">**visSLOJumpCode**</span><span class="sxs-lookup"><span data-stu-id="7e297-134">**visSLOJumpCode**</span></span> <br/> |
   

