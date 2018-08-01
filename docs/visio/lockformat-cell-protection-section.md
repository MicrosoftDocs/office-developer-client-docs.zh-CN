---
title: LockFormat 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm625
localization_priority: Normal
ms.assetid: e9a640f4-0af0-317c-b77b-f32c651e87b4
description: 锁定形状的格式，使它无法更改。
ms.openlocfilehash: c3e4d5be848e91554406e709ce6872ae49b5f38d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780622"
---
# <a name="lockformat-cell-protection-section"></a><span data-ttu-id="f1e5c-103">LockFormat 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="f1e5c-103">LockFormat Cell (Protection Section)</span></span>

<span data-ttu-id="f1e5c-104">锁定形状的格式，使它无法更改。</span><span class="sxs-lookup"><span data-stu-id="f1e5c-104">Locks the formatting of a shape so it cannot be changed.</span></span>
  
|<span data-ttu-id="f1e5c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f1e5c-105">**Value**</span></span>|<span data-ttu-id="f1e5c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f1e5c-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f1e5c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f1e5c-107">TRUE</span></span>  <br/> | <span data-ttu-id="f1e5c-108">不能更改格式。</span><span class="sxs-lookup"><span data-stu-id="f1e5c-108">Formatting cannot be changed.</span></span>  <br/> |
| <span data-ttu-id="f1e5c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f1e5c-109">FALSE</span></span>  <br/> | <span data-ttu-id="f1e5c-110">能够更改格式。</span><span class="sxs-lookup"><span data-stu-id="f1e5c-110">Formatting can be changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f1e5c-111">注释</span><span class="sxs-lookup"><span data-stu-id="f1e5c-111">Remarks</span></span>

<span data-ttu-id="f1e5c-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockFormat 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-112">To get a reference to the LockFormat cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f1e5c-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-113">Cell name:</span></span>  <br/> | <span data-ttu-id="f1e5c-114">LockFormat</span><span class="sxs-lookup"><span data-stu-id="f1e5c-114">LockFormat</span></span>  <br/> |
   
<span data-ttu-id="f1e5c-115">要从某个程序按索引获取对 LockFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-115">To get a reference to the LockFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f1e5c-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-116">Section index:</span></span>  <br/> |<span data-ttu-id="f1e5c-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f1e5c-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f1e5c-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-118">Row index:</span></span>  <br/> |<span data-ttu-id="f1e5c-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="f1e5c-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="f1e5c-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f1e5c-120">Cell index:</span></span>  <br/> |<span data-ttu-id="f1e5c-121">**visLockFormat**</span><span class="sxs-lookup"><span data-stu-id="f1e5c-121">**visLockFormat**</span></span> <br/> |
   

