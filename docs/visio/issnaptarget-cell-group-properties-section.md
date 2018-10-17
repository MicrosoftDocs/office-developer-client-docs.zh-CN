---
title: IsSnapTarget 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251626
localization_priority: Normal
ms.assetid: b58131f6-a566-d9ca-bad4-4f4b66e03aaf
description: 确定是对齐组合还是对齐该组合内的形状。
ms.openlocfilehash: 89536923617f80768d7c14658cb07c97595824ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780495"
---
# <a name="issnaptarget-cell-group-properties-section"></a><span data-ttu-id="56c3f-103">IsSnapTarget 单元格（“Group Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="56c3f-103">IsSnapTarget Cell (Group Properties Section)</span></span>

<span data-ttu-id="56c3f-104">确定是对齐组合还是对齐该组合内的形状。</span><span class="sxs-lookup"><span data-stu-id="56c3f-104">Determines whether you snap to a group or to shapes within the group.</span></span>
  
|<span data-ttu-id="56c3f-105">**值**</span><span class="sxs-lookup"><span data-stu-id="56c3f-105">**Value**</span></span>|<span data-ttu-id="56c3f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="56c3f-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56c3f-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="56c3f-107">TRUE</span></span>  <br/> |<span data-ttu-id="56c3f-108">启用对齐组合内的形状。</span><span class="sxs-lookup"><span data-stu-id="56c3f-108">Enable snapping to shapes within a group.</span></span>  <br/> |
|<span data-ttu-id="56c3f-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="56c3f-109">FALSE</span></span>  <br/> |<span data-ttu-id="56c3f-110">只对齐组合。</span><span class="sxs-lookup"><span data-stu-id="56c3f-110">Snap only to the group.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="56c3f-111">注解</span><span class="sxs-lookup"><span data-stu-id="56c3f-111">Remarks</span></span>

<span data-ttu-id="56c3f-112">您还可以采用以下方法设置此值：选择该组合，在[“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“对齐成员形状”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="56c3f-112">You can also set this value by selecting the group, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Snap to member shapes** check box.</span></span> 
  
<span data-ttu-id="56c3f-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsSnapTarget 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="56c3f-113">To get a reference to the IsSnapTarget cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56c3f-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="56c3f-114">Cell name:</span></span>  <br/> |<span data-ttu-id="56c3f-115">IsSnapTarget</span><span class="sxs-lookup"><span data-stu-id="56c3f-115">IsSnapTarget</span></span>  <br/> |
   
<span data-ttu-id="56c3f-116">若要从某个程序按索引获取对 IsSnapTarget 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="56c3f-116">To get a reference to the IsSnapTarget cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56c3f-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="56c3f-117">Section index:</span></span>  <br/> |<span data-ttu-id="56c3f-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="56c3f-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="56c3f-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="56c3f-119">Row index:</span></span>  <br/> |<span data-ttu-id="56c3f-120">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="56c3f-120">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="56c3f-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="56c3f-121">Cell index:</span></span>  <br/> |<span data-ttu-id="56c3f-122">**visGroupIsSnapTarget**</span><span class="sxs-lookup"><span data-stu-id="56c3f-122">**visGroupIsSnapTarget**</span></span> <br/> |
   
