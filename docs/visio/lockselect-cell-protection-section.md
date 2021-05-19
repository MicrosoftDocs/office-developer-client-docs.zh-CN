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
ms.openlocfilehash: c9f762f390dbea1e4ff2bd5bcf9566b8c67df11f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409753"
---
# <a name="lockselect-cell-protection-section"></a><span data-ttu-id="f44c8-103">LockSelect 单元格（“Protection”内容）</span><span class="sxs-lookup"><span data-stu-id="f44c8-103">LockSelect Cell (Protection Section)</span></span>

<span data-ttu-id="f44c8-104">防止选取某个形状。</span><span class="sxs-lookup"><span data-stu-id="f44c8-104">Prevents a shape from being selected.</span></span>
  
|<span data-ttu-id="f44c8-105">**值**</span><span class="sxs-lookup"><span data-stu-id="f44c8-105">**Value**</span></span>|<span data-ttu-id="f44c8-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f44c8-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f44c8-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f44c8-107">TRUE</span></span>  <br/> | <span data-ttu-id="f44c8-108">不能选取形状。</span><span class="sxs-lookup"><span data-stu-id="f44c8-108">Shape cannot be selected.</span></span>  <br/> |
| <span data-ttu-id="f44c8-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="f44c8-109">FALSE</span></span>  <br/> | <span data-ttu-id="f44c8-110">能够选取形状。</span><span class="sxs-lookup"><span data-stu-id="f44c8-110">Shape can be selected.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f44c8-111">备注</span><span class="sxs-lookup"><span data-stu-id="f44c8-111">Remarks</span></span>

<span data-ttu-id="f44c8-112">要使 LockSelect 生效，必须在 **“保护文档”** 对话框中选取 **“形状”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="f44c8-112">In order for LockSelect to take effect, the **Shapes** check box must be selected in the **Protect Document** dialog box.</span></span> 
  
<span data-ttu-id="f44c8-113">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockSelect 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f44c8-113">To get a reference to the LockSelect cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f44c8-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f44c8-114">Cell name:</span></span>  <br/> | <span data-ttu-id="f44c8-115">LockSelect</span><span class="sxs-lookup"><span data-stu-id="f44c8-115">LockSelect</span></span>  <br/> |
   
<span data-ttu-id="f44c8-116">要从某个程序按索引获取对 LockSelect 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f44c8-116">To get a reference to the LockSelect cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f44c8-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f44c8-117">Section index:</span></span>  <br/> |<span data-ttu-id="f44c8-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f44c8-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f44c8-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="f44c8-119">Row index:</span></span>  <br/> |<span data-ttu-id="f44c8-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="f44c8-120">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="f44c8-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f44c8-121">Cell index:</span></span>  <br/> |<span data-ttu-id="f44c8-122">**visLockSelect**</span><span class="sxs-lookup"><span data-stu-id="f44c8-122">**visLockSelect**</span></span> <br/> |
   

