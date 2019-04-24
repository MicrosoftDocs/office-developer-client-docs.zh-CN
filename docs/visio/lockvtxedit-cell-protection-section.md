---
title: LockVtxEdit 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251224
localization_priority: Normal
ms.assetid: 966cde5c-f04e-7149-3660-720ffa4f7079
description: 锁定形状的顶点，以使它们无法编辑。
ms.openlocfilehash: 1703769fe54171a14f7052f0f6686e1eb5ec92fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358056"
---
# <a name="lockvtxedit-cell-protection-section"></a><span data-ttu-id="48fff-103">LockVtxEdit 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="48fff-103">LockVtxEdit Cell (Protection Section)</span></span>

<span data-ttu-id="48fff-104">锁定形状的顶点，以使它们无法编辑。</span><span class="sxs-lookup"><span data-stu-id="48fff-104">Locks the vertices of a shape so that they cannot be edited.</span></span>
  
|<span data-ttu-id="48fff-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="48fff-105">**Value**</span></span>|<span data-ttu-id="48fff-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="48fff-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48fff-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="48fff-107">TRUE</span></span>  <br/> |<span data-ttu-id="48fff-108">不能编辑顶点。</span><span class="sxs-lookup"><span data-stu-id="48fff-108">Vertices cannot be edited.</span></span>  <br/> |
|<span data-ttu-id="48fff-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="48fff-109">FALSE</span></span>  <br/> |<span data-ttu-id="48fff-110">能够编辑顶点。</span><span class="sxs-lookup"><span data-stu-id="48fff-110">Vertices can be edited.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48fff-111">注解</span><span class="sxs-lookup"><span data-stu-id="48fff-111">Remarks</span></span>

<span data-ttu-id="48fff-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockVtxEdit 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="48fff-112">To get a reference to the LockVtxEdit cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="48fff-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="48fff-113">Cell name:</span></span>  <br/> |<span data-ttu-id="48fff-114">LockVtxEdit</span><span class="sxs-lookup"><span data-stu-id="48fff-114">LockVtxEdit</span></span>  <br/> |
   
<span data-ttu-id="48fff-115">若要从某个程序按索引获取对 LockVtxEdit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="48fff-115">To get a reference to the LockVtxEdit cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="48fff-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="48fff-116">Section index:</span></span>  <br/> |<span data-ttu-id="48fff-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="48fff-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="48fff-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="48fff-118">Row index:</span></span>  <br/> |<span data-ttu-id="48fff-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="48fff-119">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="48fff-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="48fff-120">Cell index:</span></span>  <br/> |<span data-ttu-id="48fff-121">**visLockVtxEdit**</span><span class="sxs-lookup"><span data-stu-id="48fff-121">**visLockVtxEdit**</span></span> <br/> |
   

