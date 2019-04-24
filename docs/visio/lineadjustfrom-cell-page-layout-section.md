---
title: LineAdjustFrom 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251887
localization_priority: Normal
ms.assetid: 6949c717-dc69-1d17-5215-eb6efce56fcb
description: 确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。
ms.openlocfilehash: 3eb9f5513ee3ce2f5dce96cb47c356bca29a289c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359323"
---
# <a name="lineadjustfrom-cell-page-layout-section"></a><span data-ttu-id="07d1e-103">LineAdjustFrom 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="07d1e-103">LineAdjustFrom Cell (Page Layout Section)</span></span>

<span data-ttu-id="07d1e-104">确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。</span><span class="sxs-lookup"><span data-stu-id="07d1e-104">Determines which dynamic connectors the application spaces apart if they route on top of each other.</span></span>
  
|<span data-ttu-id="07d1e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="07d1e-105">**Value**</span></span>|<span data-ttu-id="07d1e-106">**调**</span><span class="sxs-lookup"><span data-stu-id="07d1e-106">**Adjustment**</span></span>|<span data-ttu-id="07d1e-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="07d1e-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07d1e-108">0</span><span class="sxs-lookup"><span data-stu-id="07d1e-108">0</span></span>  <br/> |<span data-ttu-id="07d1e-109">无关的线条</span><span class="sxs-lookup"><span data-stu-id="07d1e-109">Unrelated lines</span></span>  <br/> |<span data-ttu-id="07d1e-110">**visPLOLineAdjustFromNotRelated**</span><span class="sxs-lookup"><span data-stu-id="07d1e-110">**visPLOLineAdjustFromNotRelated**</span></span> <br/> |
|<span data-ttu-id="07d1e-111">1</span><span class="sxs-lookup"><span data-stu-id="07d1e-111">1</span></span>  <br/> |<span data-ttu-id="07d1e-112">所有线条</span><span class="sxs-lookup"><span data-stu-id="07d1e-112">All lines</span></span>  <br/> |<span data-ttu-id="07d1e-113">**visPLOLineAdjustFromAll**</span><span class="sxs-lookup"><span data-stu-id="07d1e-113">**visPLOLineAdjustFromAll**</span></span> <br/> |
|<span data-ttu-id="07d1e-114">双面</span><span class="sxs-lookup"><span data-stu-id="07d1e-114">2</span></span>  <br/> |<span data-ttu-id="07d1e-115">无线条</span><span class="sxs-lookup"><span data-stu-id="07d1e-115">No lines</span></span>  <br/> |<span data-ttu-id="07d1e-116">**visPLOLineAdjustFromNone**</span><span class="sxs-lookup"><span data-stu-id="07d1e-116">**visPLOLineAdjustFromNone**</span></span> <br/> |
|<span data-ttu-id="07d1e-117">第三章</span><span class="sxs-lookup"><span data-stu-id="07d1e-117">3</span></span>  <br/> |<span data-ttu-id="07d1e-118">默认的排列样式</span><span class="sxs-lookup"><span data-stu-id="07d1e-118">Routing style default</span></span>  <br/> |<span data-ttu-id="07d1e-119">**visPLOLineAdjustFromRoutingDefault**</span><span class="sxs-lookup"><span data-stu-id="07d1e-119">**visPLOLineAdjustFromRoutingDefault**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07d1e-120">注解</span><span class="sxs-lookup"><span data-stu-id="07d1e-120">Remarks</span></span>

<span data-ttu-id="07d1e-121">还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="07d1e-121">You can also set the value of this cell on the **Layout and Routing** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then click **Layout and Routing**).</span></span>
  
<span data-ttu-id="07d1e-122">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineAdjustFrom 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="07d1e-122">To get a reference to the LineAdjustFrom cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="07d1e-123">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="07d1e-123">Cell name:</span></span>  <br/> |<span data-ttu-id="07d1e-124">LineAdjustFrom</span><span class="sxs-lookup"><span data-stu-id="07d1e-124">LineAdjustFrom</span></span>  <br/> |
   
<span data-ttu-id="07d1e-125">若要从某个程序按索引获取对 LineAdjustFrom 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="07d1e-125">To get a reference to the LineAdjustFrom cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="07d1e-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="07d1e-126">Section index:</span></span>  <br/> |<span data-ttu-id="07d1e-127">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="07d1e-127">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="07d1e-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="07d1e-128">Row index:</span></span>  <br/> |<span data-ttu-id="07d1e-129">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="07d1e-129">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="07d1e-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="07d1e-130">Cell index:</span></span>  <br/> |<span data-ttu-id="07d1e-131">**visPLOLineAdjustFrom**</span><span class="sxs-lookup"><span data-stu-id="07d1e-131">**visPLOLineAdjustFrom**</span></span> <br/> |
   

