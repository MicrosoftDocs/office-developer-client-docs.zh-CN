---
title: LockMoveY 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm645
localization_priority: Normal
ms.assetid: 4ed8cab4-112a-e96a-f4e3-02490a6f87fa
description: 锁定形状的垂直位置，使它不能垂直移动。
ms.openlocfilehash: 6666d47555f8175b4950f95e1fb15abb8b11bfd5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434044"
---
# <a name="lockmovey-cell-protection-section"></a><span data-ttu-id="37081-103">LockMoveY 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="37081-103">LockMoveY Cell (Protection Section)</span></span>

<span data-ttu-id="37081-104">锁定形状的垂直位置，使它不能垂直移动。</span><span class="sxs-lookup"><span data-stu-id="37081-104">Locks the vertical position of the shape so it cannot be moved vertically.</span></span>
  
|<span data-ttu-id="37081-105">**值**</span><span class="sxs-lookup"><span data-stu-id="37081-105">**Value**</span></span>|<span data-ttu-id="37081-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="37081-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="37081-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="37081-107">TRUE</span></span>  <br/> | <span data-ttu-id="37081-108">已锁定垂直位置。</span><span class="sxs-lookup"><span data-stu-id="37081-108">Vertical position is locked.</span></span>  <br/> |
| <span data-ttu-id="37081-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="37081-109">FALSE</span></span>  <br/> | <span data-ttu-id="37081-110">未锁定垂直位置。</span><span class="sxs-lookup"><span data-stu-id="37081-110">Vertical position is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="37081-111">备注</span><span class="sxs-lookup"><span data-stu-id="37081-111">Remarks</span></span>

<span data-ttu-id="37081-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockMoveY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="37081-112">To get a reference to the LockMoveY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="37081-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="37081-113">Cell name:</span></span>  <br/> | <span data-ttu-id="37081-114">LockMoveY</span><span class="sxs-lookup"><span data-stu-id="37081-114">LockMoveY</span></span>  <br/> |
   
<span data-ttu-id="37081-115">要从某个程序按索引获取对 LockMoveY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="37081-115">To get a reference to the LockMoveY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="37081-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="37081-116">Section index:</span></span>  <br/> |<span data-ttu-id="37081-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="37081-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="37081-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="37081-118">Row index:</span></span>  <br/> |<span data-ttu-id="37081-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="37081-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="37081-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="37081-120">Cell index:</span></span>  <br/> |<span data-ttu-id="37081-121">**visLockMoveY**</span><span class="sxs-lookup"><span data-stu-id="37081-121">**visLockMoveY**</span></span> <br/> |
   

