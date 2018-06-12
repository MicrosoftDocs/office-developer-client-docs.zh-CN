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
ms.openlocfilehash: f7f9c99eb4978e9b32968d3076b0341efe42faa6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780611"
---
# <a name="lockcalcwh-cell-protection-section"></a><span data-ttu-id="eacd2-103">LockCalcWH 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="eacd2-103">LockCalcWH Cell (Protection Section)</span></span>

<span data-ttu-id="eacd2-104">锁定形状的选择矩形，使得在“Geometry”内容中编辑顶点或更改行类型时，不会重新计算选择矩形。</span><span class="sxs-lookup"><span data-stu-id="eacd2-104">Locks a shape's selection rectangle so it cannot be recalculated when a vertex is edited or a row type is changed in the Geometry section.</span></span>
  
|<span data-ttu-id="eacd2-105">**值**</span><span class="sxs-lookup"><span data-stu-id="eacd2-105">**Value**</span></span>|<span data-ttu-id="eacd2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="eacd2-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="eacd2-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="eacd2-107">TRUE</span></span>  <br/> | <span data-ttu-id="eacd2-108">不能重新计算宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="eacd2-108">Width and height cannot be recalculated.</span></span>  <br/> |
| <span data-ttu-id="eacd2-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="eacd2-109">FALSE</span></span>  <br/> | <span data-ttu-id="eacd2-110">能够重新计算宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="eacd2-110">Width and height can be recalculated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eacd2-111">注释</span><span class="sxs-lookup"><span data-stu-id="eacd2-111">Remarks</span></span>

<span data-ttu-id="eacd2-112">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockCalcWH 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="eacd2-112">To get a reference to the LockCalcWH cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eacd2-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="eacd2-113">Cell name:</span></span>  <br/> | <span data-ttu-id="eacd2-114">LockCalcWH</span><span class="sxs-lookup"><span data-stu-id="eacd2-114">LockCalcWH</span></span>  <br/> |
   
<span data-ttu-id="eacd2-115">若要从某个程序按索引获取对 LockCalcWH 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="eacd2-115">To get a reference to the LockCalcWH cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="eacd2-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="eacd2-116">Section index:</span></span>  <br/> |<span data-ttu-id="eacd2-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="eacd2-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="eacd2-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="eacd2-118">Row index:</span></span>  <br/> |<span data-ttu-id="eacd2-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="eacd2-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="eacd2-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="eacd2-120">Cell index:</span></span>  <br/> |<span data-ttu-id="eacd2-121">**visLockCalcWH**</span><span class="sxs-lookup"><span data-stu-id="eacd2-121">**visLockCalcWH**</span></span> <br/> |
   

