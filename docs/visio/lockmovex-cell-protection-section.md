---
title: LockMoveX 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm640
localization_priority: Normal
ms.assetid: 48ceeeed-66ae-a81f-2aee-f0010102dfb7
description: 锁定形状的水平位置，使它不能水平移动。
ms.openlocfilehash: 981f4f417e48f70d0693e30683c4351d0e53a758
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780646"
---
# <a name="lockmovex-cell-protection-section"></a><span data-ttu-id="12f75-103">LockMoveX 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="12f75-103">LockMoveX Cell (Protection Section)</span></span>

<span data-ttu-id="12f75-104">锁定形状的水平位置，使它不能水平移动。</span><span class="sxs-lookup"><span data-stu-id="12f75-104">Locks the horizontal position of the shape so it cannot be moved horizontally.</span></span>
  
|<span data-ttu-id="12f75-105">**值**</span><span class="sxs-lookup"><span data-stu-id="12f75-105">**Value**</span></span>|<span data-ttu-id="12f75-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="12f75-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="12f75-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="12f75-107">TRUE</span></span>  <br/> | <span data-ttu-id="12f75-108">已锁定水平位置。</span><span class="sxs-lookup"><span data-stu-id="12f75-108">Horizontal position is locked.</span></span>  <br/> |
| <span data-ttu-id="12f75-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="12f75-109">FALSE</span></span>  <br/> | <span data-ttu-id="12f75-110">未锁定水平位置。</span><span class="sxs-lookup"><span data-stu-id="12f75-110">Horizontal position is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12f75-111">注释</span><span class="sxs-lookup"><span data-stu-id="12f75-111">Remarks</span></span>

<span data-ttu-id="12f75-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockMoveX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="12f75-112">To get a reference to the LockMoveX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="12f75-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="12f75-113">Cell name:</span></span>  <br/> | <span data-ttu-id="12f75-114">LockMoveX</span><span class="sxs-lookup"><span data-stu-id="12f75-114">LockMoveX</span></span>  <br/> |
   
<span data-ttu-id="12f75-115">若要从某个程序按索引获取对 LockMoveX 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="12f75-115">To get a reference to the LockMoveX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="12f75-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="12f75-116">Section index:</span></span>  <br/> |<span data-ttu-id="12f75-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="12f75-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="12f75-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="12f75-118">Row index:</span></span>  <br/> |<span data-ttu-id="12f75-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="12f75-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="12f75-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="12f75-120">Cell index:</span></span>  <br/> |<span data-ttu-id="12f75-121">**visLockMoveX**</span><span class="sxs-lookup"><span data-stu-id="12f75-121">**visLockMoveX**</span></span> <br/> |
   

