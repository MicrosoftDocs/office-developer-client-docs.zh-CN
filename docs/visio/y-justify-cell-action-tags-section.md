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
description: Y-偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。
ms.openlocfilehash: 8f8323d1f392654bf118ece2f78890f2a1b860ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781711"
---
# <a name="y-justify-cell-action-tags-section"></a><span data-ttu-id="75370-103">Y Justify 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="75370-103">Y Justify Cell (Action Tags Section)</span></span>

<span data-ttu-id="75370-104">*Y* -偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。</span><span class="sxs-lookup"><span data-stu-id="75370-104">The  *y*  -offset of the action tag button relative to the point defined by the X and Y cells.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="75370-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="75370-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="75370-106">**值**</span><span class="sxs-lookup"><span data-stu-id="75370-106">**Value**</span></span>|<span data-ttu-id="75370-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="75370-107">**Description**</span></span>|<span data-ttu-id="75370-108">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="75370-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="75370-109">0</span><span class="sxs-lookup"><span data-stu-id="75370-109">0</span></span>  <br/> | <span data-ttu-id="75370-110">靠上对齐（默认值）。</span><span class="sxs-lookup"><span data-stu-id="75370-110">Top justified (the default).</span></span>  <br/> |<span data-ttu-id="75370-111">**visSmartTagYJustifyTop**</span><span class="sxs-lookup"><span data-stu-id="75370-111">**visSmartTagYJustifyTop**</span></span> <br/> |
| <span data-ttu-id="75370-112">1</span><span class="sxs-lookup"><span data-stu-id="75370-112">1</span></span>  <br/> | <span data-ttu-id="75370-113">居中。</span><span class="sxs-lookup"><span data-stu-id="75370-113">Centered.</span></span>  <br/> |<span data-ttu-id="75370-114">**visSmartTagYJustifyMiddle**</span><span class="sxs-lookup"><span data-stu-id="75370-114">**visSmartTagYJustifyMiddle**</span></span> <br/> |
| <span data-ttu-id="75370-115">2</span><span class="sxs-lookup"><span data-stu-id="75370-115">2</span></span>  <br/> | <span data-ttu-id="75370-116">靠下对齐。</span><span class="sxs-lookup"><span data-stu-id="75370-116">Bottom justified.</span></span>  <br/> |<span data-ttu-id="75370-117">**visSmartTagYJustifyBottom**</span><span class="sxs-lookup"><span data-stu-id="75370-117">**visSmartTagYJustifyBottom**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="75370-118">备注</span><span class="sxs-lookup"><span data-stu-id="75370-118">Remarks</span></span>

<span data-ttu-id="75370-119">X Justify 和 Y Justify 单元格确定动作标记按钮相对于 X 和 Y 单元格中定义的点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="75370-119">The X Justify and Y Justify cells determine where the action tag button is placed in relation to the point defined in the X and Y cells.</span></span>
  
<span data-ttu-id="75370-120">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y Justify 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="75370-120">To get a reference to the Y Justify cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="75370-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="75370-121">Cell name:</span></span>  <br/> | <span data-ttu-id="75370-122">智能标记。</span><span class="sxs-lookup"><span data-stu-id="75370-122">SmartTags.</span></span>  <span data-ttu-id="75370-123">*名称*。YJustify 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="75370-123">*name*  .YJustify           where SmartTags.</span></span> <span data-ttu-id="75370-124">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="75370-124">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="75370-125">若要从某个程序按索引获取对 Y Justify 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="75370-125">To get a reference to the Y Justify cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="75370-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="75370-126">Section index:</span></span>  <br/> |<span data-ttu-id="75370-127">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="75370-127">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="75370-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="75370-128">Row index:</span></span>  <br/> |<span data-ttu-id="75370-129">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="75370-129">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="75370-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="75370-130">Cell index:</span></span>  <br/> |<span data-ttu-id="75370-131">**visSmartTagYJustify**</span><span class="sxs-lookup"><span data-stu-id="75370-131">**visSmartTagYJustify**</span></span> <br/> |
   

