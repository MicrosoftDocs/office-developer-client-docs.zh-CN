---
title: LockThemeIndex 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b781727-267b-4589-ab40-cfc79bb96c2d
description: 通过应用新主题或选择新的连接器方案, 防止主题属性行中的 ThemeIndex 单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: 519c17f6e00c9aad2b5522bc66b41c0ceb75911b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411237"
---
# <a name="lockthemeindex-cell-protection-section"></a><span data-ttu-id="744ce-104">LockThemeIndex 单元格 ("Protection" 部分)</span><span class="sxs-lookup"><span data-stu-id="744ce-104">LockThemeIndex Cell (Protection Section)</span></span>

<span data-ttu-id="744ce-105">通过应用新主题或选择新的连接器方案, 防止**主题属性**行中的**ThemeIndex**单元格被更改。</span><span class="sxs-lookup"><span data-stu-id="744ce-105">Prevents **ThemeIndex** cell in **Theme Properties** row from being altered by applying a new theme or selecting a new connector scheme.</span></span> <span data-ttu-id="744ce-106">不会阻止用户在 ShapeSheet 中手动编辑此值。</span><span class="sxs-lookup"><span data-stu-id="744ce-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="744ce-107">**值**</span><span class="sxs-lookup"><span data-stu-id="744ce-107">**Value**</span></span>|<span data-ttu-id="744ce-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="744ce-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="744ce-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="744ce-109">TRUE</span></span>  <br/> |<span data-ttu-id="744ce-110">除非直接在 ShapeSheet 中进行更改, 否则无法更改**ThemeIndex**单元格的当前值。</span><span class="sxs-lookup"><span data-stu-id="744ce-110">The **ThemeIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="744ce-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="744ce-111">FALSE</span></span>  <br/> |<span data-ttu-id="744ce-112">当主题发生更改时, **ThemeIndex**单元格可以从其当前值更改。</span><span class="sxs-lookup"><span data-stu-id="744ce-112">The **ThemeIndex** cell can be changed from its current value when the theme is changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="744ce-113">说明</span><span class="sxs-lookup"><span data-stu-id="744ce-113">Remarks</span></span>

<span data-ttu-id="744ce-114">若要从另一个公式按名称获取对**LockThemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="744ce-114">To get a reference to the **LockThemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="744ce-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="744ce-115">Cell name:</span></span>  <br/> | <span data-ttu-id="744ce-116">LockThemeIndex</span><span class="sxs-lookup"><span data-stu-id="744ce-116">LockThemeIndex</span></span>  <br/> |
   
<span data-ttu-id="744ce-117">若要从某个程序按索引获取对**LockThemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="744ce-117">To get a reference to the **LockThemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="744ce-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="744ce-118">Section index:</span></span>  <br/> |<span data-ttu-id="744ce-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="744ce-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="744ce-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="744ce-120">Row index:</span></span>  <br/> |<span data-ttu-id="744ce-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="744ce-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="744ce-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="744ce-122">Cell index:</span></span>  <br/> |<span data-ttu-id="744ce-123">**visLockThemeIndex**</span><span class="sxs-lookup"><span data-stu-id="744ce-123">**visLockThemeIndex**</span></span> <br/> |
   

