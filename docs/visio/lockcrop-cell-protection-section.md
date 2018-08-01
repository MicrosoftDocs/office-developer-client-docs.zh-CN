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
ms.openlocfilehash: d7f231d5dcb022548477e0817c9d408a8d1b86ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780617"
---
# <a name="lockcrop-cell-protection-section"></a><span data-ttu-id="84a6c-103">LockCrop 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="84a6c-103">LockCrop Cell (Protection Section)</span></span>

<span data-ttu-id="84a6c-104">锁定来自其他程序的对象，防止它被 **“剪裁”** 工具剪裁。</span><span class="sxs-lookup"><span data-stu-id="84a6c-104">Locks an object from another program against being cropped with the **Crop** tool.</span></span> 
  
|<span data-ttu-id="84a6c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="84a6c-105">**Value**</span></span>|<span data-ttu-id="84a6c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="84a6c-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="84a6c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="84a6c-107">TRUE</span></span>  <br/> | <span data-ttu-id="84a6c-108">不能剪裁形状</span><span class="sxs-lookup"><span data-stu-id="84a6c-108">Shape cannot be cropped</span></span>  <br/> |
| <span data-ttu-id="84a6c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="84a6c-109">FALSE</span></span>  <br/> | <span data-ttu-id="84a6c-110">能够剪裁形状。</span><span class="sxs-lookup"><span data-stu-id="84a6c-110">Shape can be cropped.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="84a6c-111">注释</span><span class="sxs-lookup"><span data-stu-id="84a6c-111">Remarks</span></span>

<span data-ttu-id="84a6c-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockCrop 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="84a6c-112">To get a reference to the LockCrop cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="84a6c-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="84a6c-113">Cell name:</span></span>  <br/> | <span data-ttu-id="84a6c-114">LockCrop</span><span class="sxs-lookup"><span data-stu-id="84a6c-114">LockCrop</span></span>  <br/> |
   
<span data-ttu-id="84a6c-115">要从某个程序按索引获取对 LockCrop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="84a6c-115">To get a reference to the LockCrop cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="84a6c-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="84a6c-116">Section index:</span></span>  <br/> |<span data-ttu-id="84a6c-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="84a6c-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="84a6c-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="84a6c-118">Row index:</span></span>  <br/> |<span data-ttu-id="84a6c-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="84a6c-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="84a6c-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="84a6c-120">Cell index:</span></span>  <br/> |<span data-ttu-id="84a6c-121">**visLockCrop**</span><span class="sxs-lookup"><span data-stu-id="84a6c-121">**visLockCrop**</span></span> <br/> |
   

