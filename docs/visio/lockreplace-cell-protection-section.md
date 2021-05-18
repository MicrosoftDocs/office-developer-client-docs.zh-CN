---
title: 'LockReplace Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b3880511-dd27-4dc2-9e50-a49084ef8195
description: 指示形状是否可以参与替换操作 (作为目标或替换形状) 。
ms.openlocfilehash: 8b0e3175cacd9b906d91a4185dcd98fad604d8bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404139"
---
# <a name="lockreplace-cell-protection-section"></a><span data-ttu-id="0fb20-103">LockReplace Cell (Protection Section) </span><span class="sxs-lookup"><span data-stu-id="0fb20-103">LockReplace Cell (Protection Section)</span></span>

<span data-ttu-id="0fb20-104">指示形状是否可以参与替换操作 (作为目标或替换形状) 。</span><span class="sxs-lookup"><span data-stu-id="0fb20-104">Indicates whether a shape can participate in a replacement operation (as either a target or a replacement shape).</span></span> 
  
|<span data-ttu-id="0fb20-105">**值**</span><span class="sxs-lookup"><span data-stu-id="0fb20-105">**Value**</span></span>|<span data-ttu-id="0fb20-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="0fb20-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fb20-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fb20-107">TRUE</span></span>  <br/> |<span data-ttu-id="0fb20-108">该形状不能替换或用作替换形状。</span><span class="sxs-lookup"><span data-stu-id="0fb20-108">The shape cannot be replaced or be used as a replacement shape.</span></span>  <br/> <span data-ttu-id="0fb20-109">对于画布上的形状，选择形状时，"更改形状"按钮处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="0fb20-109">For a shape on the canvas, the **Change Shape** button is disabled when the shape is selected.</span></span>  <br/> <span data-ttu-id="0fb20-110">对于模具上的形状，单击"更改形状"按钮时，该形状不会显示为替换形状。 </span><span class="sxs-lookup"><span data-stu-id="0fb20-110">For a shape on a stencil, the shape does not appear as a replacement shape when the **Change Shape** button is clicked.</span></span>  <br/> |
|<span data-ttu-id="0fb20-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="0fb20-111">FALSE</span></span>  <br/> |<span data-ttu-id="0fb20-112">该形状可以替换或用作替换形状。</span><span class="sxs-lookup"><span data-stu-id="0fb20-112">The shape can be replaced or used as a replacement shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0fb20-113">备注</span><span class="sxs-lookup"><span data-stu-id="0fb20-113">Remarks</span></span>

<span data-ttu-id="0fb20-114">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockReplace** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0fb20-114">To get a reference to the **LockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0fb20-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0fb20-115">Cell name:</span></span>  <br/> | <span data-ttu-id="0fb20-116">LockReplace</span><span class="sxs-lookup"><span data-stu-id="0fb20-116">LockReplace</span></span>  <br/> |
   
<span data-ttu-id="0fb20-117">若要从程序按索引获取对 **LockReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0fb20-117">To get a reference to the **LockReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0fb20-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0fb20-118">Section index:</span></span>  <br/> |<span data-ttu-id="0fb20-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="0fb20-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="0fb20-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="0fb20-120">Row index:</span></span>  <br/> |<span data-ttu-id="0fb20-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="0fb20-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="0fb20-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0fb20-122">Cell index:</span></span>  <br/> |<span data-ttu-id="0fb20-123">**visLockReplace**</span><span class="sxs-lookup"><span data-stu-id="0fb20-123">**visLockReplace**</span></span> <br/> |
   

