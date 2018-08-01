---
title: LockThemeFonts 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1ce8b52c-b6c1-4764-b4ec-00c7efb8929d
description: 防止 FontIndex 行的单元格中主题属性被更改通过应用新主题。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: b90ffe4c5555df017bb0506a78351514c954ec39
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780668"
---
# <a name="lockthemefonts-cell-protection-section"></a><span data-ttu-id="3bc46-104">LockThemeFonts 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="3bc46-104">LockThemeFonts Cell (Protection Section)</span></span>

<span data-ttu-id="3bc46-105">防止**FontIndex**行的单元格中**主题属性**被更改通过应用新主题。</span><span class="sxs-lookup"><span data-stu-id="3bc46-105">Prevents the **FontIndex** cell in the **Theme Properties** row from being altered by applying a new theme.</span></span> <span data-ttu-id="3bc46-106">不阻止用户手动编辑 ShapeSheet 中的此值。</span><span class="sxs-lookup"><span data-stu-id="3bc46-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="3bc46-107">**值**</span><span class="sxs-lookup"><span data-stu-id="3bc46-107">**Value**</span></span>|<span data-ttu-id="3bc46-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="3bc46-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3bc46-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="3bc46-109">TRUE</span></span>  <br/> |<span data-ttu-id="3bc46-110">无法从其当前值更改**FontIndex**单元格，除非直接 ShapeSheet 中的更改。</span><span class="sxs-lookup"><span data-stu-id="3bc46-110">The **FontIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="3bc46-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="3bc46-111">FALSE</span></span>  <br/> |<span data-ttu-id="3bc46-112">主题发生更改时，可以从其当前值更改**FontIndex**单元格。</span><span class="sxs-lookup"><span data-stu-id="3bc46-112">The **FontIndex** cell can be changed from its current value when the theme is changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3bc46-113">说明</span><span class="sxs-lookup"><span data-stu-id="3bc46-113">Remarks</span></span>

<span data-ttu-id="3bc46-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeFonts**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3bc46-114">To get a reference to the **LockThemeFonts** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3bc46-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3bc46-115">Cell name:</span></span>  <br/> | <span data-ttu-id="3bc46-116">LockThemeFonts</span><span class="sxs-lookup"><span data-stu-id="3bc46-116">LockThemeFonts</span></span>  <br/> |
   
<span data-ttu-id="3bc46-117">若要从某个程序按索引获取对**LockThemeFonts**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="3bc46-117">To get a reference to the **LockThemeFonts** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3bc46-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3bc46-118">Section index:</span></span>  <br/> |<span data-ttu-id="3bc46-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3bc46-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3bc46-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="3bc46-120">Row index:</span></span>  <br/> |<span data-ttu-id="3bc46-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="3bc46-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="3bc46-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3bc46-122">Cell index:</span></span>  <br/> |<span data-ttu-id="3bc46-123">**visLockThemeFonts**</span><span class="sxs-lookup"><span data-stu-id="3bc46-123">**visLockThemeFonts**</span></span> <br/> |
   

