---
title: Disabled 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60038
localization_priority: Normal
ms.assetid: bf0a80c9-0fdb-e2cf-3ab0-74cb6338fdce
description: 指示动作标记是否在绘图窗口中显示。
ms.openlocfilehash: 867d36e27cb890509b0687500caf719362a711fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439665"
---
# <a name="disabled-cell-action-tags-section"></a><span data-ttu-id="16a20-103">Disabled 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="16a20-103">Disabled Cell (Action Tags Section)</span></span>

<span data-ttu-id="16a20-104">指示动作标记是否在绘图窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="16a20-104">Indicates whether the action tag appears in the drawing window.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16a20-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="16a20-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="16a20-106">**值**</span><span class="sxs-lookup"><span data-stu-id="16a20-106">**Value**</span></span>|<span data-ttu-id="16a20-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="16a20-107">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="16a20-108">TRUE</span><span class="sxs-lookup"><span data-stu-id="16a20-108">TRUE</span></span>  <br/> | <span data-ttu-id="16a20-109">禁用动作标记。</span><span class="sxs-lookup"><span data-stu-id="16a20-109">The action tag is disabled.</span></span>  <br/> |
| <span data-ttu-id="16a20-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="16a20-110">FALSE</span></span>  <br/> | <span data-ttu-id="16a20-111">启用动作标记（默认值）。</span><span class="sxs-lookup"><span data-stu-id="16a20-111">The action tag is enabled (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="16a20-112">说明</span><span class="sxs-lookup"><span data-stu-id="16a20-112">Remarks</span></span>

<span data-ttu-id="16a20-113">动作标记被禁用后，在重新启用之前完全不显示。</span><span class="sxs-lookup"><span data-stu-id="16a20-113">When an action tag is disabled, it does not appear at all until it is re-enabled.</span></span> 
  
<span data-ttu-id="16a20-114">若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Disabled 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="16a20-114">To get a reference to the Disabled cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="16a20-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="16a20-115">Cell name:</span></span>  <br/> | <span data-ttu-id="16a20-116">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="16a20-116">SmartTags.</span></span>  <span data-ttu-id="16a20-117">*名称*。在智能标记中禁用。</span><span class="sxs-lookup"><span data-stu-id="16a20-117">*name*  .Disabled           where SmartTags.</span></span> <span data-ttu-id="16a20-118">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="16a20-118">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="16a20-119">要从某个程序按索引获取对 Disabled 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="16a20-119">To get a reference to the Disabled cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="16a20-120">内容索引：</span><span class="sxs-lookup"><span data-stu-id="16a20-120">Section index:</span></span>  <br/> |<span data-ttu-id="16a20-121">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="16a20-121">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="16a20-122">行索引：</span><span class="sxs-lookup"><span data-stu-id="16a20-122">Row index:</span></span>  <br/> |<span data-ttu-id="16a20-123">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="16a20-123">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="16a20-124">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="16a20-124">Cell index:</span></span>  <br/> |<span data-ttu-id="16a20-125">**visSmartTagDisabled**</span><span class="sxs-lookup"><span data-stu-id="16a20-125">**visSmartTagDisabled**</span></span> <br/> |
   

