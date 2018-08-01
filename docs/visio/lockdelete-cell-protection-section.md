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
ms.openlocfilehash: 00229dcabf45d2a3435039ffe05fd7eb4de75808
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780620"
---
# <a name="lockdelete-cell-protection-section"></a><span data-ttu-id="2c6ac-103">LockDelete 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="2c6ac-103">LockDelete Cell (Protection Section)</span></span>

<span data-ttu-id="2c6ac-104">锁定形状，使它不能被删除。</span><span class="sxs-lookup"><span data-stu-id="2c6ac-104">Locks the shape so that it cannot be deleted.</span></span>
  
|<span data-ttu-id="2c6ac-105">**值**</span><span class="sxs-lookup"><span data-stu-id="2c6ac-105">**Value**</span></span>|<span data-ttu-id="2c6ac-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c6ac-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2c6ac-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="2c6ac-107">TRUE</span></span>  <br/> | <span data-ttu-id="2c6ac-108">不能删除形状</span><span class="sxs-lookup"><span data-stu-id="2c6ac-108">Shape cannot be deleted</span></span>  <br/> |
| <span data-ttu-id="2c6ac-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="2c6ac-109">FALSE</span></span>  <br/> | <span data-ttu-id="2c6ac-110">能够删除形状。</span><span class="sxs-lookup"><span data-stu-id="2c6ac-110">Shape can be deleted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2c6ac-111">注释</span><span class="sxs-lookup"><span data-stu-id="2c6ac-111">Remarks</span></span>

<span data-ttu-id="2c6ac-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockDelete 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-112">To get a reference to the LockDelete cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2c6ac-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-113">Cell name:</span></span>  <br/> | <span data-ttu-id="2c6ac-114">LockDelete</span><span class="sxs-lookup"><span data-stu-id="2c6ac-114">LockDelete</span></span>  <br/> |
   
<span data-ttu-id="2c6ac-115">要从某个程序按索引获取对 LockDelete 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-115">To get a reference to the LockDelete cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2c6ac-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-116">Section index:</span></span>  <br/> |<span data-ttu-id="2c6ac-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2c6ac-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2c6ac-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-118">Row index:</span></span>  <br/> |<span data-ttu-id="2c6ac-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="2c6ac-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="2c6ac-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2c6ac-120">Cell index:</span></span>  <br/> |<span data-ttu-id="2c6ac-121">**visLockDelete**</span><span class="sxs-lookup"><span data-stu-id="2c6ac-121">**visLockDelete**</span></span> <br/> |
   

