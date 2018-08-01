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
ms.openlocfilehash: 4d09d514a3fff8ada40c67eb9cd9537539a1039a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780642"
---
# <a name="lockgroup-cell-protection-section"></a><span data-ttu-id="6909a-103">LockGroup 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="6909a-103">LockGroup Cell (Protection Section)</span></span>

<span data-ttu-id="6909a-104">锁定某组，使该组不能被取消组合。</span><span class="sxs-lookup"><span data-stu-id="6909a-104">Locks a group so that it cannot be ungrouped.</span></span>
  
|<span data-ttu-id="6909a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="6909a-105">**Value**</span></span>|<span data-ttu-id="6909a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="6909a-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6909a-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="6909a-107">TRUE</span></span>  <br/> |<span data-ttu-id="6909a-108">不能取消组合。</span><span class="sxs-lookup"><span data-stu-id="6909a-108">Group cannot be ungrouped.</span></span>  <br/> |
|<span data-ttu-id="6909a-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="6909a-109">FALSE</span></span>  <br/> |<span data-ttu-id="6909a-110">能够取消组合。</span><span class="sxs-lookup"><span data-stu-id="6909a-110">Group can be ungrouped.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6909a-111">注解</span><span class="sxs-lookup"><span data-stu-id="6909a-111">Remarks</span></span>

<span data-ttu-id="6909a-112">将 LockGroupCell 值设置为 TRUE 还可防止删除作为组合成员的任何形状。</span><span class="sxs-lookup"><span data-stu-id="6909a-112">Setting the LockGroupCell value to TRUE also prevents deletion of any shapes that are members of the group.</span></span>
  
<span data-ttu-id="6909a-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockGroup 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6909a-113">To get a reference to the LockGroup cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6909a-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6909a-114">Cell name:</span></span>  <br/> |<span data-ttu-id="6909a-115">LockGroup</span><span class="sxs-lookup"><span data-stu-id="6909a-115">LockGroup</span></span>  <br/> |
   
<span data-ttu-id="6909a-116">若要从某个程序按索引获取对 LockGroup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6909a-116">To get a reference to the LockGroup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6909a-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6909a-117">Section index:</span></span>  <br/> |<span data-ttu-id="6909a-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6909a-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="6909a-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="6909a-119">Row index:</span></span>  <br/> |<span data-ttu-id="6909a-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="6909a-120">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="6909a-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6909a-121">Cell index:</span></span>  <br/> |<span data-ttu-id="6909a-122">**visLockGroup**</span><span class="sxs-lookup"><span data-stu-id="6909a-122">**visLockGroup**</span></span> <br/> |
   

