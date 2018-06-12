---
title: LockWidth 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm675
localization_priority: Normal
ms.assetid: fef022ea-38ab-2b66-60c8-b94a6b0bdfbf
description: 锁定形状的宽度，以便在调整该形状的大小时使其宽度保持不变。
ms.openlocfilehash: abdcc0d5285e98e5856524925a41c4f72ee7f6ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780654"
---
# <a name="lockwidth-cell-protection-section"></a><span data-ttu-id="8cf92-103">LockWidth 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="8cf92-103">LockWidth Cell (Protection Section)</span></span>

<span data-ttu-id="8cf92-104">锁定形状的宽度，以便在调整该形状的大小时使其宽度保持不变。</span><span class="sxs-lookup"><span data-stu-id="8cf92-104">Locks the width of the shape so that its width remains unchanged when the shape is sized.</span></span>
  
|<span data-ttu-id="8cf92-105">**值**</span><span class="sxs-lookup"><span data-stu-id="8cf92-105">**Value**</span></span>|<span data-ttu-id="8cf92-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cf92-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="8cf92-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="8cf92-107">TRUE</span></span>  <br/> | <span data-ttu-id="8cf92-108">已锁定宽度。</span><span class="sxs-lookup"><span data-stu-id="8cf92-108">Width is locked.</span></span>  <br/> |
| <span data-ttu-id="8cf92-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="8cf92-109">FALSE</span></span>  <br/> | <span data-ttu-id="8cf92-110">未锁定宽度。</span><span class="sxs-lookup"><span data-stu-id="8cf92-110">Width is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8cf92-111">注释</span><span class="sxs-lookup"><span data-stu-id="8cf92-111">Remarks</span></span>

<span data-ttu-id="8cf92-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockWidth 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8cf92-112">To get a reference to the LockWidth cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8cf92-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8cf92-113">Cell name:</span></span>  <br/> | <span data-ttu-id="8cf92-114">LockWidth</span><span class="sxs-lookup"><span data-stu-id="8cf92-114">LockWidth</span></span>  <br/> |
   
<span data-ttu-id="8cf92-115">若要从某个程序按索引获取对 LockWidth 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="8cf92-115">To get a reference to the LockWidth cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="8cf92-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8cf92-116">Section index:</span></span>  <br/> |<span data-ttu-id="8cf92-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8cf92-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="8cf92-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="8cf92-118">Row index:</span></span>  <br/> |<span data-ttu-id="8cf92-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="8cf92-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="8cf92-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8cf92-120">Cell index:</span></span>  <br/> |<span data-ttu-id="8cf92-121">**visLockWidth**</span><span class="sxs-lookup"><span data-stu-id="8cf92-121">**visLockWidth**</span></span> <br/> |
   

