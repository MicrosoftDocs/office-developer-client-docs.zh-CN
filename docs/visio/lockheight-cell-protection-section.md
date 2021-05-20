---
title: LockHeight 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm635
localization_priority: Normal
ms.assetid: 218b957e-5af6-e53b-1453-a84164ae456e
description: 锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。
ms.openlocfilehash: 099f6597656d4389476818253f34e741ddd404de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432084"
---
# <a name="lockheight-cell-protection-section"></a><span data-ttu-id="764b4-103">LockHeight 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="764b4-103">LockHeight Cell (Protection Section)</span></span>

<span data-ttu-id="764b4-104">锁定形状的高度，以便在调整该形状的大小时使其高度保持不变。</span><span class="sxs-lookup"><span data-stu-id="764b4-104">Locks the height of the shape so that its height remains unchanged when the shape is resized.</span></span>
  
|<span data-ttu-id="764b4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="764b4-105">**Value**</span></span>|<span data-ttu-id="764b4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="764b4-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="764b4-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="764b4-107">TRUE</span></span>  <br/> | <span data-ttu-id="764b4-108">已锁定高度。</span><span class="sxs-lookup"><span data-stu-id="764b4-108">Height is locked.</span></span>  <br/> |
| <span data-ttu-id="764b4-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="764b4-109">FALSE</span></span>  <br/> | <span data-ttu-id="764b4-110">未锁定高度。</span><span class="sxs-lookup"><span data-stu-id="764b4-110">Height is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="764b4-111">备注</span><span class="sxs-lookup"><span data-stu-id="764b4-111">Remarks</span></span>

<span data-ttu-id="764b4-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockHeight 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="764b4-112">To get a reference to the LockHeight cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="764b4-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="764b4-113">Cell name:</span></span>  <br/> | <span data-ttu-id="764b4-114">LockHeight</span><span class="sxs-lookup"><span data-stu-id="764b4-114">LockHeight</span></span>  <br/> |
   
<span data-ttu-id="764b4-115">要从某个程序按索引获取对 LockHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="764b4-115">To get a reference to the LockHeight cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="764b4-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="764b4-116">Section index:</span></span>  <br/> |<span data-ttu-id="764b4-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="764b4-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="764b4-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="764b4-118">Row index:</span></span>  <br/> |<span data-ttu-id="764b4-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="764b4-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="764b4-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="764b4-120">Cell index:</span></span>  <br/> |<span data-ttu-id="764b4-121">**visLockHeight**</span><span class="sxs-lookup"><span data-stu-id="764b4-121">**visLockHeight**</span></span> <br/> |
   

