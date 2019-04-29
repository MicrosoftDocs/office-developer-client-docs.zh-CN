---
title: LockCrop 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm610
localization_priority: Normal
ms.assetid: ae05de63-b527-66e6-2c79-056c9c92ec95
description: 锁定来自其他程序的对象，防止它被“剪裁”工具剪裁。
ms.openlocfilehash: bfb8bebd50908387fa3f94a8ca228935ef709133
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411853"
---
# <a name="lockcrop-cell-protection-section"></a><span data-ttu-id="7bb6b-103">LockCrop 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="7bb6b-103">LockCrop Cell (Protection Section)</span></span>

<span data-ttu-id="7bb6b-104">锁定来自其他程序的对象，防止它被 **“剪裁”** 工具剪裁。</span><span class="sxs-lookup"><span data-stu-id="7bb6b-104">Locks an object from another program against being cropped with the **Crop** tool.</span></span> 
  
|<span data-ttu-id="7bb6b-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7bb6b-105">**Value**</span></span>|<span data-ttu-id="7bb6b-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7bb6b-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="7bb6b-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7bb6b-107">TRUE</span></span>  <br/> | <span data-ttu-id="7bb6b-108">不能剪裁形状</span><span class="sxs-lookup"><span data-stu-id="7bb6b-108">Shape cannot be cropped</span></span>  <br/> |
| <span data-ttu-id="7bb6b-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7bb6b-109">FALSE</span></span>  <br/> | <span data-ttu-id="7bb6b-110">能够剪裁形状。</span><span class="sxs-lookup"><span data-stu-id="7bb6b-110">Shape can be cropped.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7bb6b-111">说明</span><span class="sxs-lookup"><span data-stu-id="7bb6b-111">Remarks</span></span>

<span data-ttu-id="7bb6b-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockCrop 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-112">To get a reference to the LockCrop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7bb6b-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-113">Cell name:</span></span>  <br/> | <span data-ttu-id="7bb6b-114">LockCrop</span><span class="sxs-lookup"><span data-stu-id="7bb6b-114">LockCrop</span></span>  <br/> |
   
<span data-ttu-id="7bb6b-115">要从某个程序按索引获取对 LockCrop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-115">To get a reference to the LockCrop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7bb6b-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-116">Section index:</span></span>  <br/> |<span data-ttu-id="7bb6b-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7bb6b-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7bb6b-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-118">Row index:</span></span>  <br/> |<span data-ttu-id="7bb6b-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="7bb6b-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="7bb6b-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7bb6b-120">Cell index:</span></span>  <br/> |<span data-ttu-id="7bb6b-121">**visLockCrop**</span><span class="sxs-lookup"><span data-stu-id="7bb6b-121">**visLockCrop**</span></span> <br/> |
   

