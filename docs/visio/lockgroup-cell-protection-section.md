---
title: LockGroup 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251227
localization_priority: Normal
ms.assetid: 04b0fa5b-1680-cfe2-6aaf-0502ad196027
description: 锁定某组，使该组不能被取消组合。
ms.openlocfilehash: 0cb2c0653780dcb653e5903faaaa0ebf30ea9d69
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404307"
---
# <a name="lockgroup-cell-protection-section"></a><span data-ttu-id="04ecd-103">LockGroup 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="04ecd-103">LockGroup Cell (Protection Section)</span></span>

<span data-ttu-id="04ecd-104">锁定某组，使该组不能被取消组合。</span><span class="sxs-lookup"><span data-stu-id="04ecd-104">Locks a group so that it cannot be ungrouped.</span></span>
  
|<span data-ttu-id="04ecd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="04ecd-105">**Value**</span></span>|<span data-ttu-id="04ecd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="04ecd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04ecd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="04ecd-107">TRUE</span></span>  <br/> |<span data-ttu-id="04ecd-108">不能取消组合。</span><span class="sxs-lookup"><span data-stu-id="04ecd-108">Group cannot be ungrouped.</span></span>  <br/> |
|<span data-ttu-id="04ecd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="04ecd-109">FALSE</span></span>  <br/> |<span data-ttu-id="04ecd-110">能够取消组合。</span><span class="sxs-lookup"><span data-stu-id="04ecd-110">Group can be ungrouped.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="04ecd-111">说明</span><span class="sxs-lookup"><span data-stu-id="04ecd-111">Remarks</span></span>

<span data-ttu-id="04ecd-112">将 LockGroupCell 值设置为 TRUE 还可防止删除作为组合成员的任何形状。</span><span class="sxs-lookup"><span data-stu-id="04ecd-112">Setting the LockGroupCell value to TRUE also prevents deletion of any shapes that are members of the group.</span></span>
  
<span data-ttu-id="04ecd-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockGroup 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="04ecd-113">To get a reference to the LockGroup cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="04ecd-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="04ecd-114">Cell name:</span></span>  <br/> |<span data-ttu-id="04ecd-115">LockGroup</span><span class="sxs-lookup"><span data-stu-id="04ecd-115">LockGroup</span></span>  <br/> |
   
<span data-ttu-id="04ecd-116">若要从某个程序按索引获取对 LockGroup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="04ecd-116">To get a reference to the LockGroup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="04ecd-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="04ecd-117">Section index:</span></span>  <br/> |<span data-ttu-id="04ecd-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="04ecd-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="04ecd-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="04ecd-119">Row index:</span></span>  <br/> |<span data-ttu-id="04ecd-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="04ecd-120">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="04ecd-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="04ecd-121">Cell index:</span></span>  <br/> |<span data-ttu-id="04ecd-122">**visLockGroup**</span><span class="sxs-lookup"><span data-stu-id="04ecd-122">**visLockGroup**</span></span> <br/> |
   

