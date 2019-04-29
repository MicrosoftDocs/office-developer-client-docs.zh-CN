---
title: Y Justify 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026937
localization_priority: Normal
ms.assetid: 27042b62-7623-95d7-7e10-f589d74605c7
description: 动作标记按钮相对于由 X 单元格和 y 单元格定义的点的 y 轴偏移量。
ms.openlocfilehash: d7a1f5c1feda3624c9f96039e7247c737a91a813
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419980"
---
# <a name="y-justify-cell-action-tags-section"></a><span data-ttu-id="c6c40-103">Y Justify 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="c6c40-103">Y Justify Cell (Action Tags Section)</span></span>

<span data-ttu-id="c6c40-104">动作标记按钮相对于由 X 单元格和 y 单元格定义的点的*y 轴*偏移量。</span><span class="sxs-lookup"><span data-stu-id="c6c40-104">The  *y*  -offset of the action tag button relative to the point defined by the X and Y cells.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c6c40-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="c6c40-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="c6c40-106">**值**</span><span class="sxs-lookup"><span data-stu-id="c6c40-106">**Value**</span></span>|<span data-ttu-id="c6c40-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="c6c40-107">**Description**</span></span>|<span data-ttu-id="c6c40-108">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="c6c40-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="c6c40-109">0</span><span class="sxs-lookup"><span data-stu-id="c6c40-109">0</span></span>  <br/> | <span data-ttu-id="c6c40-110">靠上对齐（默认值）。</span><span class="sxs-lookup"><span data-stu-id="c6c40-110">Top justified (the default).</span></span>  <br/> |<span data-ttu-id="c6c40-111">**visSmartTagYJustifyTop**</span><span class="sxs-lookup"><span data-stu-id="c6c40-111">**visSmartTagYJustifyTop**</span></span> <br/> |
| <span data-ttu-id="c6c40-112">1</span><span class="sxs-lookup"><span data-stu-id="c6c40-112">1</span></span>  <br/> | <span data-ttu-id="c6c40-113">居中。</span><span class="sxs-lookup"><span data-stu-id="c6c40-113">Centered.</span></span>  <br/> |<span data-ttu-id="c6c40-114">**visSmartTagYJustifyMiddle**</span><span class="sxs-lookup"><span data-stu-id="c6c40-114">**visSmartTagYJustifyMiddle**</span></span> <br/> |
| <span data-ttu-id="c6c40-115">双面</span><span class="sxs-lookup"><span data-stu-id="c6c40-115">2</span></span>  <br/> | <span data-ttu-id="c6c40-116">靠下对齐。</span><span class="sxs-lookup"><span data-stu-id="c6c40-116">Bottom justified.</span></span>  <br/> |<span data-ttu-id="c6c40-117">**visSmartTagYJustifyBottom**</span><span class="sxs-lookup"><span data-stu-id="c6c40-117">**visSmartTagYJustifyBottom**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6c40-118">说明</span><span class="sxs-lookup"><span data-stu-id="c6c40-118">Remarks</span></span>

<span data-ttu-id="c6c40-119">x 两端对齐和 y 调整单元格确定操作标记按钮相对于 X 和 Y 单元格定义的点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="c6c40-119">The X Justify and Y Justify cells determine where the action tag button is placed in relation to the point defined in the X and Y cells.</span></span>
  
<span data-ttu-id="c6c40-120">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Justify 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c6c40-120">To get a reference to the Y Justify cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c6c40-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c6c40-121">Cell name:</span></span>  <br/> | <span data-ttu-id="c6c40-122">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="c6c40-122">SmartTags.</span></span>  <span data-ttu-id="c6c40-123">*名称*。YJustify 其中的智能标记。</span><span class="sxs-lookup"><span data-stu-id="c6c40-123">*name*  .YJustify           where SmartTags.</span></span> <span data-ttu-id="c6c40-124">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="c6c40-124">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="c6c40-125">要从某个程序按索引获取对 Y Justify 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c6c40-125">To get a reference to the Y Justify cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c6c40-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c6c40-126">Section index:</span></span>  <br/> |<span data-ttu-id="c6c40-127">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="c6c40-127">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="c6c40-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="c6c40-128">Row index:</span></span>  <br/> |<span data-ttu-id="c6c40-129">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="c6c40-129">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c6c40-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c6c40-130">Cell index:</span></span>  <br/> |<span data-ttu-id="c6c40-131">**visSmartTagYJustify**</span><span class="sxs-lookup"><span data-stu-id="c6c40-131">**visSmartTagYJustify**</span></span> <br/> |
   

