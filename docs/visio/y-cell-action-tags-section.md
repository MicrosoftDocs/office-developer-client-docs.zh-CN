---
title: Y 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026934
localization_priority: Normal
ms.assetid: b213fc46-7f80-99fd-60ba-8ddf3d0f6ee3
description: Y-坐标周围放置动作标记按钮的形状的本地坐标系中的位置。
ms.openlocfilehash: 641c868703c6e4b0b7e749f68813b5869b5728c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781700"
---
# <a name="y-cell-action-tags-section"></a><span data-ttu-id="07d76-103">Y 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="07d76-103">Y Cell (Action Tags Section)</span></span>

<span data-ttu-id="07d76-104">*Y* -坐标周围放置动作标记按钮的形状的本地坐标系中的位置。</span><span class="sxs-lookup"><span data-stu-id="07d76-104">The  *y*  -coordinate position in the shape's local coordinates around which the action tag button is placed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="07d76-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="07d76-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="07d76-106">注释</span><span class="sxs-lookup"><span data-stu-id="07d76-106">Remarks</span></span>

<span data-ttu-id="07d76-107">X 单元格和 Y 单元格定义形状的本地坐标系中的某一点，X Justify 单元格和 Y Justify 单元格定义动作标记按钮相对于该点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="07d76-107">The X and Y cells define a point in the shape's local coordinates, and the X Justify and Y Justify cells define where to place the action tag button in relation to that point.</span></span> 
  
<span data-ttu-id="07d76-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="07d76-108">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="07d76-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="07d76-109">Cell name:</span></span>  <br/> | <span data-ttu-id="07d76-110">智能标记。</span><span class="sxs-lookup"><span data-stu-id="07d76-110">SmartTags.</span></span>  <span data-ttu-id="07d76-111">*名称*。Y 其中智能标记。</span><span class="sxs-lookup"><span data-stu-id="07d76-111">*name*  .Y           where SmartTags.</span></span> <span data-ttu-id="07d76-112">*name*是动作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="07d76-112">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="07d76-113">若要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="07d76-113">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="07d76-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="07d76-114">Section index:</span></span>  <br/> |<span data-ttu-id="07d76-115">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="07d76-115">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="07d76-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="07d76-116">Row index:</span></span>  <br/> |<span data-ttu-id="07d76-117">**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="07d76-117">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="07d76-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="07d76-118">Cell index:</span></span>  <br/> |<span data-ttu-id="07d76-119">**visSmartTagY**</span><span class="sxs-lookup"><span data-stu-id="07d76-119">**visSmartTagY**</span></span> <br/> |
   

