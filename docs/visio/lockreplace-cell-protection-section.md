---
title: LockReplace 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b3880511-dd27-4dc2-9e50-a49084ef8195
description: 指示某个形状是否可以参与替换操作 （作为目标或替换形状中）。
ms.openlocfilehash: 6f3e41d6a6c5b28c55e21961de63d0cc20eeb129
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780630"
---
# <a name="lockreplace-cell-protection-section"></a><span data-ttu-id="77f7e-103">LockReplace 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="77f7e-103">LockReplace Cell (Protection Section)</span></span>

<span data-ttu-id="77f7e-104">指示某个形状是否可以参与替换操作 （作为目标或替换形状中）。</span><span class="sxs-lookup"><span data-stu-id="77f7e-104">Indicates whether a shape can participate in a replacement operation (as either a target or a replacement shape).</span></span> 
  
|<span data-ttu-id="77f7e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="77f7e-105">**Value**</span></span>|<span data-ttu-id="77f7e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="77f7e-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77f7e-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="77f7e-107">TRUE</span></span>  <br/> |<span data-ttu-id="77f7e-108">形状不能取代或用作替换形状。</span><span class="sxs-lookup"><span data-stu-id="77f7e-108">The shape cannot be replaced or be used as a replacement shape.</span></span>  <br/> <span data-ttu-id="77f7e-109">画布上的形状，**更改形状**按钮被禁用时选择形状。</span><span class="sxs-lookup"><span data-stu-id="77f7e-109">For a shape on the canvas, the **Change Shape** button is disabled when the shape is selected.</span></span>  <br/> <span data-ttu-id="77f7e-110">模具上形状，该形状不显示为替换形状时单击**更改形状**按钮。</span><span class="sxs-lookup"><span data-stu-id="77f7e-110">For a shape on a stencil, the shape does not appear as a replacement shape when the **Change Shape** button is clicked.</span></span>  <br/> |
|<span data-ttu-id="77f7e-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="77f7e-111">FALSE</span></span>  <br/> |<span data-ttu-id="77f7e-112">形状可以替换或用作替换形状。</span><span class="sxs-lookup"><span data-stu-id="77f7e-112">The shape can be replaced or used as a replacement shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="77f7e-113">说明</span><span class="sxs-lookup"><span data-stu-id="77f7e-113">Remarks</span></span>

<span data-ttu-id="77f7e-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockReplace**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="77f7e-114">To get a reference to the **LockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="77f7e-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="77f7e-115">Cell name:</span></span>  <br/> | <span data-ttu-id="77f7e-116">LockReplace</span><span class="sxs-lookup"><span data-stu-id="77f7e-116">LockReplace</span></span>  <br/> |
   
<span data-ttu-id="77f7e-117">若要从某个程序按索引获取对**LockReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="77f7e-117">To get a reference to the **LockReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="77f7e-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="77f7e-118">Section index:</span></span>  <br/> |<span data-ttu-id="77f7e-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="77f7e-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="77f7e-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="77f7e-120">Row index:</span></span>  <br/> |<span data-ttu-id="77f7e-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="77f7e-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="77f7e-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="77f7e-122">Cell index:</span></span>  <br/> |<span data-ttu-id="77f7e-123">**visLockReplace**</span><span class="sxs-lookup"><span data-stu-id="77f7e-123">**visLockReplace**</span></span> <br/> |
   

