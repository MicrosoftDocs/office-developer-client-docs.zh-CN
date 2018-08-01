---
title: LockBegin 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm600
localization_priority: Normal
ms.assetid: cce34aba-caae-51ee-992e-92a490b68ea5
description: 将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。
ms.openlocfilehash: c9b9a0e9b69de9b76d78ca7cebfb69116bd2fb72
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780605"
---
# <a name="lockbegin-cell-protection-section"></a><span data-ttu-id="2146f-103">LockBegin 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="2146f-103">LockBegin Cell (Protection Section)</span></span>

<span data-ttu-id="2146f-104">将一维形状的起点 (BeginX, BeginY) 锁定在特定位置上。</span><span class="sxs-lookup"><span data-stu-id="2146f-104">Locks the begin point (BeginX, BeginY) of a 1-D shape to a specific location.</span></span>
  
|<span data-ttu-id="2146f-105">**值**</span><span class="sxs-lookup"><span data-stu-id="2146f-105">**Value**</span></span>|<span data-ttu-id="2146f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2146f-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2146f-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="2146f-107">TRUE</span></span>  <br/> | <span data-ttu-id="2146f-108">已锁定起点。</span><span class="sxs-lookup"><span data-stu-id="2146f-108">Begin point is locked.</span></span>  <br/> |
| <span data-ttu-id="2146f-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="2146f-109">FALSE</span></span>  <br/> | <span data-ttu-id="2146f-110">未锁定起点。</span><span class="sxs-lookup"><span data-stu-id="2146f-110">Begin is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2146f-111">注释</span><span class="sxs-lookup"><span data-stu-id="2146f-111">Remarks</span></span>

<span data-ttu-id="2146f-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockBegin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2146f-112">To get a reference to the LockBegin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2146f-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2146f-113">Cell name:</span></span>  <br/> | <span data-ttu-id="2146f-114">LockBegin</span><span class="sxs-lookup"><span data-stu-id="2146f-114">LockBegin</span></span>  <br/> |
   
<span data-ttu-id="2146f-115">要从某个程序按索引获取对 LockBegin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2146f-115">To get a reference to the LockBegin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2146f-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2146f-116">Section index:</span></span>  <br/> |<span data-ttu-id="2146f-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2146f-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2146f-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="2146f-118">Row index:</span></span>  <br/> |<span data-ttu-id="2146f-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="2146f-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="2146f-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2146f-120">Cell index:</span></span>  <br/> |<span data-ttu-id="2146f-121">**visLockBegin**</span><span class="sxs-lookup"><span data-stu-id="2146f-121">**visLockBegin**</span></span> <br/> |
   

