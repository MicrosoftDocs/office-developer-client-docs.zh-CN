---
title: LockEnd 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm620
localization_priority: Normal
ms.assetid: e9742142-4d34-1ba9-480e-d1ecff4fc7cd
description: 将一维形状的终点 (EndX, EndY) 锁定在特定位置上。
ms.openlocfilehash: d9fe0372c44fe3b029a4d06056c8d3871c3f91e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425580"
---
# <a name="lockend-cell-protection-section"></a><span data-ttu-id="f0ab4-103">LockEnd 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="f0ab4-103">LockEnd Cell (Protection Section)</span></span>

<span data-ttu-id="f0ab4-104">将一维形状的终点 (EndX, EndY) 锁定在特定位置上。</span><span class="sxs-lookup"><span data-stu-id="f0ab4-104">Locks the endpoint (EndX, EndY) of a 1-D shape to a specific location.</span></span>
  
|<span data-ttu-id="f0ab4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-105">**Value**</span></span>|<span data-ttu-id="f0ab4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f0ab4-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f0ab4-107">TRUE</span></span>  <br/> | <span data-ttu-id="f0ab4-108">已锁定终点。</span><span class="sxs-lookup"><span data-stu-id="f0ab4-108">Endpoint is locked.</span></span>  <br/> |
| <span data-ttu-id="f0ab4-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f0ab4-109">FALSE</span></span>  <br/> | <span data-ttu-id="f0ab4-110">未锁定终点。</span><span class="sxs-lookup"><span data-stu-id="f0ab4-110">Endpoint is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f0ab4-111">备注</span><span class="sxs-lookup"><span data-stu-id="f0ab4-111">Remarks</span></span>

<span data-ttu-id="f0ab4-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockEnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-112">To get a reference to the LockEnd cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f0ab4-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-113">Cell name:</span></span>  <br/> | <span data-ttu-id="f0ab4-114">LockEnd</span><span class="sxs-lookup"><span data-stu-id="f0ab4-114">LockEnd</span></span>  <br/> |
   
<span data-ttu-id="f0ab4-115">要从某个程序按索引获取对 LockEnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-115">To get a reference to the LockEnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f0ab4-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-116">Section index:</span></span>  <br/> |<span data-ttu-id="f0ab4-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f0ab4-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-118">Row index:</span></span>  <br/> |<span data-ttu-id="f0ab4-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="f0ab4-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f0ab4-120">Cell index:</span></span>  <br/> |<span data-ttu-id="f0ab4-121">**visLockEnd**</span><span class="sxs-lookup"><span data-stu-id="f0ab4-121">**visLockEnd**</span></span> <br/> |
   

