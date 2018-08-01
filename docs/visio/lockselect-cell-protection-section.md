---
title: LockSelect 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm660
localization_priority: Normal
ms.assetid: c96b45a5-719e-8c4b-71b9-cb2224d83e21
description: 防止选取某个形状。
ms.openlocfilehash: 082e993f7773640f59022c46458563d491197908
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780649"
---
# <a name="lockselect-cell-protection-section"></a><span data-ttu-id="4dbca-103">LockSelect 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="4dbca-103">LockSelect Cell (Protection Section)</span></span>

<span data-ttu-id="4dbca-104">防止选取某个形状。</span><span class="sxs-lookup"><span data-stu-id="4dbca-104">Prevents a shape from being selected.</span></span>
  
|<span data-ttu-id="4dbca-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4dbca-105">**Value**</span></span>|<span data-ttu-id="4dbca-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4dbca-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="4dbca-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="4dbca-107">TRUE</span></span>  <br/> | <span data-ttu-id="4dbca-108">不能选取形状。</span><span class="sxs-lookup"><span data-stu-id="4dbca-108">Shape cannot be selected.</span></span>  <br/> |
| <span data-ttu-id="4dbca-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="4dbca-109">FALSE</span></span>  <br/> | <span data-ttu-id="4dbca-110">能够选取形状。</span><span class="sxs-lookup"><span data-stu-id="4dbca-110">Shape can be selected.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4dbca-111">注释</span><span class="sxs-lookup"><span data-stu-id="4dbca-111">Remarks</span></span>

<span data-ttu-id="4dbca-112">要使 LockSelect 生效，必须在 **“保护文档”** 对话框中选取 **“形状”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="4dbca-112">In order for LockSelect to take effect, the **Shapes** check box must be selected in the **Protect Document** dialog box.</span></span> 
  
<span data-ttu-id="4dbca-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockSelect 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4dbca-113">To get a reference to the LockSelect cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4dbca-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4dbca-114">Cell name:</span></span>  <br/> | <span data-ttu-id="4dbca-115">LockSelect</span><span class="sxs-lookup"><span data-stu-id="4dbca-115">LockSelect</span></span>  <br/> |
   
<span data-ttu-id="4dbca-116">要从某个程序按索引获取对 LockSelect 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4dbca-116">To get a reference to the LockSelect cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4dbca-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4dbca-117">Section index:</span></span>  <br/> |<span data-ttu-id="4dbca-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4dbca-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4dbca-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="4dbca-119">Row index:</span></span>  <br/> |<span data-ttu-id="4dbca-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="4dbca-120">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="4dbca-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4dbca-121">Cell index:</span></span>  <br/> |<span data-ttu-id="4dbca-122">**visLockSelect**</span><span class="sxs-lookup"><span data-stu-id="4dbca-122">**visLockSelect**</span></span> <br/> |
   

