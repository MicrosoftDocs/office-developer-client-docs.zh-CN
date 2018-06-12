---
title: LockRotate 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm655
localization_priority: Normal
ms.assetid: 2d97b31d-9008-307d-273a-1726007eeb34
description: 锁定二维形状，以免它随旋转手柄或者向左旋转 90 ° 或向右旋转 90 ° 命令。
ms.openlocfilehash: 450fe4786594472d018b705df4678fe636390ac3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780638"
---
# <a name="lockrotate-cell-protection-section"></a><span data-ttu-id="1564a-103">LockRotate 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="1564a-103">LockRotate Cell (Protection Section)</span></span>

<span data-ttu-id="1564a-104">锁定二维形状，以免它随旋转手柄或者**左侧的旋转 90 °**或**右旋转 90 °**命令。</span><span class="sxs-lookup"><span data-stu-id="1564a-104">Locks 2-D shapes against being rotated with the rotation handle or the **Rotate Left 90°** or **Rotate Right 90°** command.</span></span> 
  
|<span data-ttu-id="1564a-105">**值**</span><span class="sxs-lookup"><span data-stu-id="1564a-105">**Value**</span></span>|<span data-ttu-id="1564a-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="1564a-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1564a-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="1564a-107">TRUE</span></span>  <br/> | <span data-ttu-id="1564a-108">不能旋转形状。</span><span class="sxs-lookup"><span data-stu-id="1564a-108">Shape cannot be rotated.</span></span>  <br/> |
| <span data-ttu-id="1564a-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="1564a-109">FALSE</span></span>  <br/> | <span data-ttu-id="1564a-110">可以旋转形状（默认值）。</span><span class="sxs-lookup"><span data-stu-id="1564a-110">Shape can be rotated (the default).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1564a-111">注解</span><span class="sxs-lookup"><span data-stu-id="1564a-111">Remarks</span></span>

<span data-ttu-id="1564a-p101">当拖动一维形状的某个端点时，LockRotate 单元格不能阻止该形状旋转。要锁定一维形状以免其旋转，请将 LockWidth 单元格设置为非零值 (TRUE)。</span><span class="sxs-lookup"><span data-stu-id="1564a-p101">The LockRotate cell does not prevent a 1-D shape from being rotated when an endpoint is dragged. To lock a 1-D shape against rotation, set the LockWidth cell to a non-zero value (TRUE).</span></span>
  
<span data-ttu-id="1564a-114">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockRotate 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1564a-114">To get a reference to the LockRotate cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1564a-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1564a-115">Cell name:</span></span>  <br/> | <span data-ttu-id="1564a-116">LockRotate</span><span class="sxs-lookup"><span data-stu-id="1564a-116">LockRotate</span></span>  <br/> |
   
<span data-ttu-id="1564a-117">若要从某个程序按索引获取对 LockRotate 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="1564a-117">To get a reference to the LockRotate cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1564a-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1564a-118">Section index:</span></span>  <br/> |<span data-ttu-id="1564a-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="1564a-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="1564a-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="1564a-120">Row index:</span></span>  <br/> |<span data-ttu-id="1564a-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="1564a-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="1564a-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1564a-122">Cell index:</span></span>  <br/> |<span data-ttu-id="1564a-123">**visLockRotate**</span><span class="sxs-lookup"><span data-stu-id="1564a-123">**visLockRotate**</span></span> <br/> |
   

