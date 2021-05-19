---
title: 'LockThemeFonts Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1ce8b52c-b6c1-4764-b4ec-00c7efb8929d
description: 通过应用新主题防止更改"主题属性"行中的 FontIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: b3bd21c1dcd8c8c13d843c50cb29edcc5b8c4999
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421226"
---
# <a name="lockthemefonts-cell-protection-section"></a><span data-ttu-id="84844-104">LockThemeFonts Cell (Protection Section) </span><span class="sxs-lookup"><span data-stu-id="84844-104">LockThemeFonts Cell (Protection Section)</span></span>

<span data-ttu-id="84844-105">通过应用新主题防止更改"**主题** 属性"行中的 **FontIndex** 单元格。</span><span class="sxs-lookup"><span data-stu-id="84844-105">Prevents the **FontIndex** cell in the **Theme Properties** row from being altered by applying a new theme.</span></span> <span data-ttu-id="84844-106">不会阻止用户在 ShapeSheet 中手动编辑此值。</span><span class="sxs-lookup"><span data-stu-id="84844-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="84844-107">**值**</span><span class="sxs-lookup"><span data-stu-id="84844-107">**Value**</span></span>|<span data-ttu-id="84844-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="84844-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84844-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="84844-109">TRUE</span></span>  <br/> |<span data-ttu-id="84844-110">**FontIndex** 单元格不能更改其当前值，除非直接在 ShapeSheet 中进行更改。</span><span class="sxs-lookup"><span data-stu-id="84844-110">The **FontIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="84844-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="84844-111">FALSE</span></span>  <br/> |<span data-ttu-id="84844-112">更改 **主题时，FontIndex** 单元格可以从其当前值更改。</span><span class="sxs-lookup"><span data-stu-id="84844-112">The **FontIndex** cell can be changed from its current value when the theme is changed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="84844-113">备注</span><span class="sxs-lookup"><span data-stu-id="84844-113">Remarks</span></span>

<span data-ttu-id="84844-114">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockThemeFonts** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="84844-114">To get a reference to the **LockThemeFonts** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="84844-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="84844-115">Cell name:</span></span>  <br/> | <span data-ttu-id="84844-116">LockThemeFonts</span><span class="sxs-lookup"><span data-stu-id="84844-116">LockThemeFonts</span></span>  <br/> |
   
<span data-ttu-id="84844-117">若要从程序按索引获取对 **LockThemeFonts** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="84844-117">To get a reference to the **LockThemeFonts** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="84844-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="84844-118">Section index:</span></span>  <br/> |<span data-ttu-id="84844-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="84844-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="84844-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="84844-120">Row index:</span></span>  <br/> |<span data-ttu-id="84844-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="84844-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="84844-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="84844-122">Cell index:</span></span>  <br/> |<span data-ttu-id="84844-123">**visLockThemeFonts**</span><span class="sxs-lookup"><span data-stu-id="84844-123">**visLockThemeFonts**</span></span> <br/> |
   

