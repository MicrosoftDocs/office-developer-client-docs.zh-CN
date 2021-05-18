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
ms.openlocfilehash: cae3eab64be3a91c48ae9f7fb49aa2a321087f43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421443"
---
# <a name="issnaptarget-cell-group-properties-section"></a><span data-ttu-id="f3155-103">IsSnapTarget 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="f3155-103">IsSnapTarget Cell (Group Properties Section)</span></span>

<span data-ttu-id="f3155-104">确定是对齐组合还是对齐该组合内的形状。</span><span class="sxs-lookup"><span data-stu-id="f3155-104">Determines whether you snap to a group or to shapes within the group.</span></span>
  
|<span data-ttu-id="f3155-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f3155-105">**Value**</span></span>|<span data-ttu-id="f3155-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3155-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3155-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f3155-107">TRUE</span></span>  <br/> |<span data-ttu-id="f3155-108">启用对齐组合内的形状。</span><span class="sxs-lookup"><span data-stu-id="f3155-108">Enable snapping to shapes within a group.</span></span>  <br/> |
|<span data-ttu-id="f3155-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f3155-109">FALSE</span></span>  <br/> |<span data-ttu-id="f3155-110">只对齐组合。</span><span class="sxs-lookup"><span data-stu-id="f3155-110">Snap only to the group.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3155-111">备注</span><span class="sxs-lookup"><span data-stu-id="f3155-111">Remarks</span></span>

<span data-ttu-id="f3155-112">您还可以采用以下方法设置此值：选择该组合，在 [“开发工具”](run-in-developer-mode-display-the-developer-tab.md)选项卡上单击 **“行为”**，然后选中 **“对齐成员形状”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="f3155-112">You can also set this value by selecting the group, clicking **Behavior** on the [Developer](run-in-developer-mode-display-the-developer-tab.md) tab, and then selecting the **Snap to member shapes** check box.</span></span> 
  
<span data-ttu-id="f3155-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 IsSnapTarget 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f3155-113">To get a reference to the IsSnapTarget cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3155-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f3155-114">Cell name:</span></span>  <br/> |<span data-ttu-id="f3155-115">IsSnapTarget</span><span class="sxs-lookup"><span data-stu-id="f3155-115">IsSnapTarget</span></span>  <br/> |
   
<span data-ttu-id="f3155-116">若要从某个程序按索引获取对 IsSnapTarget 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f3155-116">To get a reference to the IsSnapTarget cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3155-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f3155-117">Section index:</span></span>  <br/> |<span data-ttu-id="f3155-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f3155-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="f3155-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="f3155-119">Row index:</span></span>  <br/> |<span data-ttu-id="f3155-120">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="f3155-120">**visRowGroup**</span></span> <br/> |
|<span data-ttu-id="f3155-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f3155-121">Cell index:</span></span>  <br/> |<span data-ttu-id="f3155-122">**visGroupIsSnapTarget**</span><span class="sxs-lookup"><span data-stu-id="f3155-122">**visGroupIsSnapTarget**</span></span> <br/> |
   

