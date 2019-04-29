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
ms.openlocfilehash: af0cee32370a540cd8d7aaf960cc0cbc27cc8f97
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435857"
---
# <a name="lockmovex-cell-protection-section"></a><span data-ttu-id="8ae70-103">LockMoveX 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="8ae70-103">LockMoveX Cell (Protection Section)</span></span>

<span data-ttu-id="8ae70-104">锁定形状的水平位置，使它不能水平移动。</span><span class="sxs-lookup"><span data-stu-id="8ae70-104">Locks the horizontal position of the shape so it cannot be moved horizontally.</span></span>
  
|<span data-ttu-id="8ae70-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8ae70-105">**Value**</span></span>|<span data-ttu-id="8ae70-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ae70-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8ae70-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="8ae70-107">TRUE</span></span>  <br/> | <span data-ttu-id="8ae70-108">已锁定水平位置。</span><span class="sxs-lookup"><span data-stu-id="8ae70-108">Horizontal position is locked.</span></span>  <br/> |
| <span data-ttu-id="8ae70-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="8ae70-109">FALSE</span></span>  <br/> | <span data-ttu-id="8ae70-110">未锁定水平位置。</span><span class="sxs-lookup"><span data-stu-id="8ae70-110">Horizontal position is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ae70-111">说明</span><span class="sxs-lookup"><span data-stu-id="8ae70-111">Remarks</span></span>

<span data-ttu-id="8ae70-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockMoveX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8ae70-112">To get a reference to the LockMoveX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ae70-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8ae70-113">Cell name:</span></span>  <br/> | <span data-ttu-id="8ae70-114">LockMoveX</span><span class="sxs-lookup"><span data-stu-id="8ae70-114">LockMoveX</span></span>  <br/> |
   
<span data-ttu-id="8ae70-115">要从某个程序按索引获取对 LockMoveX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8ae70-115">To get a reference to the LockMoveX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8ae70-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8ae70-116">Section index:</span></span>  <br/> |<span data-ttu-id="8ae70-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8ae70-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8ae70-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="8ae70-118">Row index:</span></span>  <br/> |<span data-ttu-id="8ae70-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="8ae70-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="8ae70-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8ae70-120">Cell index:</span></span>  <br/> |<span data-ttu-id="8ae70-121">**visLockMoveX**</span><span class="sxs-lookup"><span data-stu-id="8ae70-121">**visLockMoveX**</span></span> <br/> |
   

