---
title: X Justify 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026936
localization_priority: Normal
ms.assetid: a8995020-3eaa-2b2c-eca0-dd475de4d06f
description: X-偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。
ms.openlocfilehash: 043d7b198ae5a529c623545fb54ef5aa1d32217d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781681"
---
# <a name="x-justify-cell-action-tags-section"></a><span data-ttu-id="0136d-103">X Justify 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="0136d-103">X Justify Cell (Action Tags Section)</span></span>

<span data-ttu-id="0136d-104">*X* -偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。</span><span class="sxs-lookup"><span data-stu-id="0136d-104">The  *x*  -offset of the action tag button relative to the point defined by the X and Y cells.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0136d-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="0136d-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
|<span data-ttu-id="0136d-106">**值**</span><span class="sxs-lookup"><span data-stu-id="0136d-106">**Value**</span></span>|<span data-ttu-id="0136d-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="0136d-107">**Description**</span></span>|<span data-ttu-id="0136d-108">**自动化常量**</span><span class="sxs-lookup"><span data-stu-id="0136d-108">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="0136d-109">0</span><span class="sxs-lookup"><span data-stu-id="0136d-109">0</span></span>  <br/> | <span data-ttu-id="0136d-110">左对齐（默认值）。</span><span class="sxs-lookup"><span data-stu-id="0136d-110">Left justified (the default).</span></span>  <br/> |<span data-ttu-id="0136d-111">**visSmartTagXJustifyLeft**</span><span class="sxs-lookup"><span data-stu-id="0136d-111">**visSmartTagXJustifyLeft**</span></span> <br/> |
| <span data-ttu-id="0136d-112">1</span><span class="sxs-lookup"><span data-stu-id="0136d-112">1</span></span>  <br/> | <span data-ttu-id="0136d-113">居中。</span><span class="sxs-lookup"><span data-stu-id="0136d-113">Centered.</span></span>  <br/> |<span data-ttu-id="0136d-114">**visSmartTagXJustifyCenter**</span><span class="sxs-lookup"><span data-stu-id="0136d-114">**visSmartTagXJustifyCenter**</span></span> <br/> |
| <span data-ttu-id="0136d-115">2</span><span class="sxs-lookup"><span data-stu-id="0136d-115">2</span></span>  <br/> | <span data-ttu-id="0136d-116">右对齐。</span><span class="sxs-lookup"><span data-stu-id="0136d-116">Right justified.</span></span>  <br/> |<span data-ttu-id="0136d-117">**visSmartTagXJustifyRight**</span><span class="sxs-lookup"><span data-stu-id="0136d-117">**visSmartTagXJustifyRight**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0136d-118">备注</span><span class="sxs-lookup"><span data-stu-id="0136d-118">Remarks</span></span>

<span data-ttu-id="0136d-119">X Justify 和 Y Justify 单元格确定动作标记按钮相对于 X 和 Y 单元格中定义的点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="0136d-119">The X Justify and Y Justify cells determine where the action tag button is placed in relation to the point defined in the X and Y cells.</span></span> 
  
<span data-ttu-id="0136d-120">若要获取对 X Justify 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="0136d-120">To get a reference to the X Justify cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0136d-121">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0136d-121">Cell name:</span></span>  <br/> | <span data-ttu-id="0136d-122">智能标记。</span><span class="sxs-lookup"><span data-stu-id="0136d-122">SmartTags.</span></span>  <span data-ttu-id="0136d-123">*名称*。XJustify 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="0136d-123">*name*  .XJustify           where SmartTags.</span></span> <span data-ttu-id="0136d-124">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="0136d-124">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="0136d-125">若要从某个程序按索引获取对 X Justify 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="0136d-125">To get a reference to the X Justify cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0136d-126">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0136d-126">Section index:</span></span>  <br/> |<span data-ttu-id="0136d-127">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="0136d-127">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="0136d-128">行索引：</span><span class="sxs-lookup"><span data-stu-id="0136d-128">Row index:</span></span>  <br/> |<span data-ttu-id="0136d-129">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="0136d-129">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="0136d-130">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0136d-130">Cell index:</span></span>  <br/> |<span data-ttu-id="0136d-131">**visSmartTagXJustify**</span><span class="sxs-lookup"><span data-stu-id="0136d-131">**visSmartTagXJustify**</span></span> <br/> |
   

