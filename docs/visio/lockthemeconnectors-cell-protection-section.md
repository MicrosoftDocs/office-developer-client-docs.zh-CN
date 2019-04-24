---
title: LockThemeConnectors 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae7ddd55-7bcc-4bb6-bab7-97806122f166
description: 通过应用新主题或选择新的连接器方案, 防止主题属性行中的 ConnectorsSchemeIndex 单元格被更改。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: 8097e50646fd59f4ac0212cbe9ca2ecfaadab7a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348235"
---
# <a name="lockthemeconnectors-cell-protection-section"></a><span data-ttu-id="60519-104">LockThemeConnectors 单元格 ("Protection" 部分)</span><span class="sxs-lookup"><span data-stu-id="60519-104">LockThemeConnectors Cell (Protection Section)</span></span>

<span data-ttu-id="60519-105">通过应用新主题或选择新的连接器方案, 防止**主题属性**行中的**ConnectorsSchemeIndex**单元格被更改。</span><span class="sxs-lookup"><span data-stu-id="60519-105">Prevents the **ConnectorsSchemeIndex** cell in the **Theme Properties** row from being altered by applying a new theme or selecting a new connector scheme.</span></span> <span data-ttu-id="60519-106">不会阻止用户在 ShapeSheet 中手动编辑此值。</span><span class="sxs-lookup"><span data-stu-id="60519-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="60519-107">**Value**</span><span class="sxs-lookup"><span data-stu-id="60519-107">**Value**</span></span>|<span data-ttu-id="60519-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="60519-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60519-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="60519-109">TRUE</span></span>  <br/> |<span data-ttu-id="60519-110">除非直接在 ShapeSheet 中进行更改, 否则无法更改**ConnectorsSchemeIndex**单元格的当前值。</span><span class="sxs-lookup"><span data-stu-id="60519-110">The **ConnectorsSchemeIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="60519-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="60519-111">FALSE</span></span>  <br/> |<span data-ttu-id="60519-112">可以通过 UI 更改**ConnectorsSchemeIndex**单元格的当前值。</span><span class="sxs-lookup"><span data-stu-id="60519-112">The **ConnectorsSchemeIndex** cell can be changed from its current value through the UI.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="60519-113">注解</span><span class="sxs-lookup"><span data-stu-id="60519-113">Remarks</span></span>

<span data-ttu-id="60519-114">若要从另一个公式按名称获取对**LockThemeConnectors**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="60519-114">To get a reference to the **LockThemeConnectors** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="60519-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="60519-115">Cell name:</span></span>  <br/> | <span data-ttu-id="60519-116">LockThemeConnectors</span><span class="sxs-lookup"><span data-stu-id="60519-116">LockThemeConnectors</span></span>  <br/> |
   
<span data-ttu-id="60519-117">若要从某个程序按索引获取对**LockThemeConnectors**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="60519-117">To get a reference to the **LockThemeConnectors** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="60519-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="60519-118">Section index:</span></span>  <br/> |<span data-ttu-id="60519-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="60519-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="60519-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="60519-120">Row index:</span></span>  <br/> |<span data-ttu-id="60519-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="60519-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="60519-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="60519-122">Cell index:</span></span>  <br/> |<span data-ttu-id="60519-123">**visLockThemeConnectors**</span><span class="sxs-lookup"><span data-stu-id="60519-123">**visLockThemeConnectors**</span></span> <br/> |
   

