---
title: DontMoveChildren 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm255
localization_priority: Normal
ms.assetid: ff5bbf05-4851-30ce-7ee1-f0ce7b2781ab
description: 确定是否可以使用鼠标拖动组合中的形状。
ms.openlocfilehash: 2b15d75a98b5f5a72bce8b80758d27b197a346ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338582"
---
# <a name="dontmovechildren-cell-group-properties-section"></a><span data-ttu-id="bbb2d-103">DontMoveChildren 单元格（“Group Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="bbb2d-103">DontMoveChildren Cell (Group Properties Section)</span></span>

<span data-ttu-id="bbb2d-104">确定是否可以使用鼠标拖动组合中的形状。</span><span class="sxs-lookup"><span data-stu-id="bbb2d-104">Determines whether you can drag shapes in a group using the mouse.</span></span>
  
|<span data-ttu-id="bbb2d-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="bbb2d-105">**Value**</span></span>|<span data-ttu-id="bbb2d-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="bbb2d-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="bbb2d-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="bbb2d-107">TRUE</span></span>  <br/> | <span data-ttu-id="bbb2d-108">不允许使用鼠标拖动组合中的形状。</span><span class="sxs-lookup"><span data-stu-id="bbb2d-108">Don't allow shapes in a group to be dragged using the mouse.</span></span>  <br/> |
| <span data-ttu-id="bbb2d-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="bbb2d-109">FALSE</span></span>  <br/> | <span data-ttu-id="bbb2d-110">允许使用鼠标拖动组合中的形状。</span><span class="sxs-lookup"><span data-stu-id="bbb2d-110">Allow shapes in a group to be dragged using the mouse.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bbb2d-111">注解</span><span class="sxs-lookup"><span data-stu-id="bbb2d-111">Remarks</span></span>

<span data-ttu-id="bbb2d-112">如果该单元格的值为 TRUE，您还可以使用其他方法翻转、旋转或重定位组合中的形状，或者更改这些形状的大小。</span><span class="sxs-lookup"><span data-stu-id="bbb2d-112">When the value of this cell is TRUE, you can still flip, rotate, resize, or reposition shapes in groups using other methods.</span></span>
  
<span data-ttu-id="bbb2d-113">对于主控形状中的组合以及在低于 Visio 2000 的版本中创建的主控形状实例中的组合，该单元格的值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bbb2d-113">The value of this cell is TRUE for groups in masters and groups in instances of masters that were created in versions of Visio earlier than version 2000.</span></span>
  
<span data-ttu-id="bbb2d-114">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DontMoveChildren 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-114">To get a reference to the DontMoveChildren cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bbb2d-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-115">Cell name:</span></span>  <br/> | <span data-ttu-id="bbb2d-116">DontMoveChildren</span><span class="sxs-lookup"><span data-stu-id="bbb2d-116">DontMoveChildren</span></span>  <br/> |
   
<span data-ttu-id="bbb2d-117">要从某个程序按索引获取对 DontMoveChildren 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-117">To get a reference to the DontMoveChildren cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bbb2d-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-118">Section index:</span></span>  <br/> |<span data-ttu-id="bbb2d-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bbb2d-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="bbb2d-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-120">Row index:</span></span>  <br/> |<span data-ttu-id="bbb2d-121">**visRowGroup**</span><span class="sxs-lookup"><span data-stu-id="bbb2d-121">**visRowGroup**</span></span> <br/> |
| <span data-ttu-id="bbb2d-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bbb2d-122">Cell index:</span></span>  <br/> |<span data-ttu-id="bbb2d-123">**visGroupDontMoveChildren**</span><span class="sxs-lookup"><span data-stu-id="bbb2d-123">**visGroupDontMoveChildren**</span></span> <br/> |
   

