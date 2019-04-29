---
title: LockAspect 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251218
localization_priority: Normal
ms.assetid: e9bfced5-af29-f86c-8604-44ec9a573229
description: 锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。
ms.openlocfilehash: 83ce1aaf555cfaaa0109423e74ae930450b4c1e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411580"
---
# <a name="lockaspect-cell-protection-section"></a><span data-ttu-id="7e41c-103">LockAspect 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="7e41c-103">LockAspect Cell (Protection Section)</span></span>

<span data-ttu-id="7e41c-104">锁定形状的纵横比，使形状只能按比例调整大小，而不能单维度调整大小。</span><span class="sxs-lookup"><span data-stu-id="7e41c-104">Locks the aspect ratio of the shape so that the shape can only be sized proportionally; it cannot be sized in a single dimension.</span></span>
  
|<span data-ttu-id="7e41c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7e41c-105">**Value**</span></span>|<span data-ttu-id="7e41c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7e41c-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="7e41c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e41c-107">TRUE</span></span>  <br/> | <span data-ttu-id="7e41c-108">已锁定纵横比。</span><span class="sxs-lookup"><span data-stu-id="7e41c-108">Aspect ratio is locked.</span></span>  <br/> |
| <span data-ttu-id="7e41c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7e41c-109">FALSE</span></span>  <br/> | <span data-ttu-id="7e41c-110">未锁定纵横比。</span><span class="sxs-lookup"><span data-stu-id="7e41c-110">Aspect ratio is not locked.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e41c-111">说明</span><span class="sxs-lookup"><span data-stu-id="7e41c-111">Remarks</span></span>

<span data-ttu-id="7e41c-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockAspect 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7e41c-112">To get a reference to the LockAspect cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e41c-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7e41c-113">Cell name:</span></span>  <br/> | <span data-ttu-id="7e41c-114">LockAspect</span><span class="sxs-lookup"><span data-stu-id="7e41c-114">LockAspect</span></span>  <br/> |
   
<span data-ttu-id="7e41c-115">若要从某个程序按索引获取对 LockAspect 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7e41c-115">To get a reference to the LockAspect cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e41c-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7e41c-116">Section index:</span></span>  <br/> |<span data-ttu-id="7e41c-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7e41c-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7e41c-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="7e41c-118">Row index:</span></span>  <br/> |<span data-ttu-id="7e41c-119">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="7e41c-119">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="7e41c-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7e41c-120">Cell index:</span></span>  <br/> |<span data-ttu-id="7e41c-121">**visLockAspect**</span><span class="sxs-lookup"><span data-stu-id="7e41c-121">**visLockAspect**</span></span> <br/> |
   

