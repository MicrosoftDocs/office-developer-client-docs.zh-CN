---
title: LockThemeIndex 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b781727-267b-4589-ab40-cfc79bb96c2d
description: 防止被更改通过应用新主题，或选择新连接器方案 ThemeIndex 主题属性行中的单元格。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: 4bef3eb799c943ff89027e69ae8580c9c0e51243
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780650"
---
# <a name="lockthemeindex-cell-protection-section"></a><span data-ttu-id="e995a-104">LockThemeIndex 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="e995a-104">LockThemeIndex Cell (Protection Section)</span></span>

<span data-ttu-id="e995a-105">防止被更改通过应用新主题，或选择新连接器方案**ThemeIndex** **主题属性**行中的单元格。</span><span class="sxs-lookup"><span data-stu-id="e995a-105">Prevents **ThemeIndex** cell in **Theme Properties** row from being altered by applying a new theme or selecting a new connector scheme.</span></span> <span data-ttu-id="e995a-106">不阻止用户手动编辑 ShapeSheet 中的此值。</span><span class="sxs-lookup"><span data-stu-id="e995a-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="e995a-107">**值**</span><span class="sxs-lookup"><span data-stu-id="e995a-107">**Value**</span></span>|<span data-ttu-id="e995a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e995a-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e995a-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="e995a-109">TRUE</span></span>  <br/> |<span data-ttu-id="e995a-110">无法从其当前值更改**ThemeIndex**单元格，除非直接 ShapeSheet 中的更改。</span><span class="sxs-lookup"><span data-stu-id="e995a-110">The **ThemeIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="e995a-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="e995a-111">FALSE</span></span>  <br/> |<span data-ttu-id="e995a-112">主题发生更改时，可以从其当前值更改**ThemeIndex**单元格。</span><span class="sxs-lookup"><span data-stu-id="e995a-112">The **ThemeIndex** cell can be changed from its current value when the theme is changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e995a-113">说明</span><span class="sxs-lookup"><span data-stu-id="e995a-113">Remarks</span></span>

<span data-ttu-id="e995a-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeIndex**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e995a-114">To get a reference to the **LockThemeIndex** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e995a-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e995a-115">Cell name:</span></span>  <br/> | <span data-ttu-id="e995a-116">LockThemeIndex</span><span class="sxs-lookup"><span data-stu-id="e995a-116">LockThemeIndex</span></span>  <br/> |
   
<span data-ttu-id="e995a-117">若要从某个程序按索引获取对**LockThemeIndex**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="e995a-117">To get a reference to the **LockThemeIndex** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e995a-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e995a-118">Section index:</span></span>  <br/> |<span data-ttu-id="e995a-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e995a-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e995a-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="e995a-120">Row index:</span></span>  <br/> |<span data-ttu-id="e995a-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="e995a-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="e995a-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e995a-122">Cell index:</span></span>  <br/> |<span data-ttu-id="e995a-123">**visLockThemeIndex**</span><span class="sxs-lookup"><span data-stu-id="e995a-123">**visLockThemeIndex**</span></span> <br/> |
   

