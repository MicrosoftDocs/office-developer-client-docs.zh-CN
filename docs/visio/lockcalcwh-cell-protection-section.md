---
title: LockCalcWH 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm605
localization_priority: Normal
ms.assetid: 6eb51e5a-03d8-3daa-b4e1-6107d540aed9
description: 锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。
ms.openlocfilehash: 2b1d907f480a22a56f5847035da8d1cbde5fdcc5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359631"
---
# <a name="lockcalcwh-cell-protection-section"></a><span data-ttu-id="26d30-103">LockCalcWH 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="26d30-103">LockCalcWH Cell (Protection Section)</span></span>

<span data-ttu-id="26d30-104">锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。</span><span class="sxs-lookup"><span data-stu-id="26d30-104">Locks a shape's selection rectangle so it cannot be recalculated when a vertex is edited or a row type is changed in the Geometry section.</span></span>
  
|<span data-ttu-id="26d30-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="26d30-105">**Value**</span></span>|<span data-ttu-id="26d30-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="26d30-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="26d30-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="26d30-107">TRUE</span></span>  <br/> | <span data-ttu-id="26d30-108">不能重新计算宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="26d30-108">Width and height cannot be recalculated.</span></span>  <br/> |
| <span data-ttu-id="26d30-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="26d30-109">FALSE</span></span>  <br/> | <span data-ttu-id="26d30-110">能够重新计算宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="26d30-110">Width and height can be recalculated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="26d30-111">注解</span><span class="sxs-lookup"><span data-stu-id="26d30-111">Remarks</span></span>

<span data-ttu-id="26d30-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockCalcWH 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="26d30-112">To get a reference to the LockCalcWH cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="26d30-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="26d30-113">Cell name:</span></span>  <br/> | <span data-ttu-id="26d30-114">LockCalcWH</span><span class="sxs-lookup"><span data-stu-id="26d30-114">LockCalcWH</span></span>  <br/> |
   
<span data-ttu-id="26d30-115">要从某个程序按索引获取对 LockCalcWH 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="26d30-115">To get a reference to the LockCalcWH cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="26d30-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="26d30-116">Section index:</span></span>  <br/> |<span data-ttu-id="26d30-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="26d30-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="26d30-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="26d30-118">Row index:</span></span>  <br/> |<span data-ttu-id="26d30-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="26d30-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="26d30-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="26d30-120">Cell index:</span></span>  <br/> |<span data-ttu-id="26d30-121">**visLockCalcWH**</span><span class="sxs-lookup"><span data-stu-id="26d30-121">**visLockCalcWH**</span></span> <br/> |
   

