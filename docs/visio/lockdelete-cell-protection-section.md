---
title: LockDelete 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251219
localization_priority: Normal
ms.assetid: 596c62b7-8d42-1854-d709-592db09a6a84
description: 锁定形状，使它不能被删除。
ms.openlocfilehash: 0819969c9ba17a52de19341b359b33ceae5b44d8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423137"
---
# <a name="lockdelete-cell-protection-section"></a><span data-ttu-id="94b80-103">LockDelete 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="94b80-103">LockDelete Cell (Protection Section)</span></span>

<span data-ttu-id="94b80-104">锁定形状，使它不能被删除。</span><span class="sxs-lookup"><span data-stu-id="94b80-104">Locks the shape so that it cannot be deleted.</span></span>
  
|<span data-ttu-id="94b80-105">**值**</span><span class="sxs-lookup"><span data-stu-id="94b80-105">**Value**</span></span>|<span data-ttu-id="94b80-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="94b80-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="94b80-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="94b80-107">TRUE</span></span>  <br/> | <span data-ttu-id="94b80-108">不能删除形状</span><span class="sxs-lookup"><span data-stu-id="94b80-108">Shape cannot be deleted</span></span>  <br/> |
| <span data-ttu-id="94b80-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="94b80-109">FALSE</span></span>  <br/> | <span data-ttu-id="94b80-110">能够删除形状。</span><span class="sxs-lookup"><span data-stu-id="94b80-110">Shape can be deleted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="94b80-111">说明</span><span class="sxs-lookup"><span data-stu-id="94b80-111">Remarks</span></span>

<span data-ttu-id="94b80-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockDelete 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="94b80-112">To get a reference to the LockDelete cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="94b80-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="94b80-113">Cell name:</span></span>  <br/> | <span data-ttu-id="94b80-114">LockDelete</span><span class="sxs-lookup"><span data-stu-id="94b80-114">LockDelete</span></span>  <br/> |
   
<span data-ttu-id="94b80-115">要从某个程序按索引获取对 LockDelete 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="94b80-115">To get a reference to the LockDelete cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="94b80-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="94b80-116">Section index:</span></span>  <br/> |<span data-ttu-id="94b80-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="94b80-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="94b80-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="94b80-118">Row index:</span></span>  <br/> |<span data-ttu-id="94b80-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="94b80-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="94b80-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="94b80-120">Cell index:</span></span>  <br/> |<span data-ttu-id="94b80-121">**visLockDelete**</span><span class="sxs-lookup"><span data-stu-id="94b80-121">**visLockDelete**</span></span> <br/> |
   

