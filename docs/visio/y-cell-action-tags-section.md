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
description: 形状的本地坐标中放置了动作标记按钮的位置的 y 坐标。
ms.openlocfilehash: 02797a849a262cb506f4617aadaccedabccdab77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430222"
---
# <a name="y-cell-action-tags-section"></a><span data-ttu-id="c5f9d-103">Y 单元格（“Action Tags”内容）</span><span class="sxs-lookup"><span data-stu-id="c5f9d-103">Y Cell (Action Tags Section)</span></span>

<span data-ttu-id="c5f9d-104">形状的本地坐标中放置了动作标记按钮的位置的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="c5f9d-104">The  *y*  -coordinate position in the shape's local coordinates around which the action tag button is placed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c5f9d-105">在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。</span><span class="sxs-lookup"><span data-stu-id="c5f9d-105">In previous versions of Microsoft Visio, action tags are called smart tags.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c5f9d-106">说明</span><span class="sxs-lookup"><span data-stu-id="c5f9d-106">Remarks</span></span>

<span data-ttu-id="c5f9d-107">X 单元格和 Y 单元格定义形状的本地坐标系中的某一点，X Justify 单元格和 Y Justify 单元格定义动作标记按钮相对于该点的放置位置。</span><span class="sxs-lookup"><span data-stu-id="c5f9d-107">The X and Y cells define a point in the shape's local coordinates, and the X Justify and Y Justify cells define where to place the action tag button in relation to that point.</span></span> 
  
<span data-ttu-id="c5f9d-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-108">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c5f9d-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-109">Cell name:</span></span>  <br/> | <span data-ttu-id="c5f9d-110">SmartTags.</span><span class="sxs-lookup"><span data-stu-id="c5f9d-110">SmartTags.</span></span>  <span data-ttu-id="c5f9d-111">*名称*。Y 其中的智能标记。</span><span class="sxs-lookup"><span data-stu-id="c5f9d-111">*name*  .Y           where SmartTags.</span></span> <span data-ttu-id="c5f9d-112">*name*是操作标记行的名称</span><span class="sxs-lookup"><span data-stu-id="c5f9d-112">*name*  is the name of the action tag row</span></span>  <br/> |
   
<span data-ttu-id="c5f9d-113">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-113">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c5f9d-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-114">Section index:</span></span>  <br/> |<span data-ttu-id="c5f9d-115">**visSectionSmartTag**</span><span class="sxs-lookup"><span data-stu-id="c5f9d-115">**visSectionSmartTag**</span></span> <br/> |
| <span data-ttu-id="c5f9d-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-116">Row index:</span></span>  <br/> |<span data-ttu-id="c5f9d-117">**visRowSmartTag** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="c5f9d-117">**visRowSmartTag** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c5f9d-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c5f9d-118">Cell index:</span></span>  <br/> |<span data-ttu-id="c5f9d-119">**visSmartTagY**</span><span class="sxs-lookup"><span data-stu-id="c5f9d-119">**visSmartTagY**</span></span> <br/> |
   

