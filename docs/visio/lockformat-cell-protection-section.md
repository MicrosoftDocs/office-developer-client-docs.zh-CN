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
ms.openlocfilehash: e0d1bb8a65b8087136e57bb46ad9f5363da30030
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409676"
---
# <a name="lockformat-cell-protection-section"></a><span data-ttu-id="7b391-103">LockFormat 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="7b391-103">LockFormat Cell (Protection Section)</span></span>

<span data-ttu-id="7b391-104">锁定形状的格式，使它无法更改。</span><span class="sxs-lookup"><span data-stu-id="7b391-104">Locks the formatting of a shape so it cannot be changed.</span></span>
  
|<span data-ttu-id="7b391-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7b391-105">**Value**</span></span>|<span data-ttu-id="7b391-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7b391-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="7b391-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7b391-107">TRUE</span></span>  <br/> | <span data-ttu-id="7b391-108">不能更改格式。</span><span class="sxs-lookup"><span data-stu-id="7b391-108">Formatting cannot be changed.</span></span>  <br/> |
| <span data-ttu-id="7b391-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b391-109">FALSE</span></span>  <br/> | <span data-ttu-id="7b391-110">能够更改格式。</span><span class="sxs-lookup"><span data-stu-id="7b391-110">Formatting can be changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b391-111">说明</span><span class="sxs-lookup"><span data-stu-id="7b391-111">Remarks</span></span>

<span data-ttu-id="7b391-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockFormat 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7b391-112">To get a reference to the LockFormat cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b391-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7b391-113">Cell name:</span></span>  <br/> | <span data-ttu-id="7b391-114">LockFormat</span><span class="sxs-lookup"><span data-stu-id="7b391-114">LockFormat</span></span>  <br/> |
   
<span data-ttu-id="7b391-115">要从某个程序按索引获取对 LockFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7b391-115">To get a reference to the LockFormat cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b391-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7b391-116">Section index:</span></span>  <br/> |<span data-ttu-id="7b391-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7b391-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7b391-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="7b391-118">Row index:</span></span>  <br/> |<span data-ttu-id="7b391-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="7b391-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="7b391-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7b391-120">Cell index:</span></span>  <br/> |<span data-ttu-id="7b391-121">**visLockFormat**</span><span class="sxs-lookup"><span data-stu-id="7b391-121">**visLockFormat**</span></span> <br/> |
   

