---
title: 'LockThemeConnectors Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae7ddd55-7bcc-4bb6-bab7-97806122f166
description: 通过应用新主题或选择新的连接器方案，防止更改"主题属性"行中的 ConnectorsSchemeIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: 8097e50646fd59f4ac0212cbe9ca2ecfaadab7a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438405"
---
# <a name="lockthemeconnectors-cell-protection-section"></a><span data-ttu-id="5aab8-104">LockThemeConnectors Cell (Protection Section) </span><span class="sxs-lookup"><span data-stu-id="5aab8-104">LockThemeConnectors Cell (Protection Section)</span></span>

<span data-ttu-id="5aab8-105">通过应用新主题或选择新的连接器方案，防止更改"主题属性"行中的 **ConnectorsSchemeIndex** 单元格。</span><span class="sxs-lookup"><span data-stu-id="5aab8-105">Prevents the **ConnectorsSchemeIndex** cell in the **Theme Properties** row from being altered by applying a new theme or selecting a new connector scheme.</span></span> <span data-ttu-id="5aab8-106">不会阻止用户在 ShapeSheet 中手动编辑此值。</span><span class="sxs-lookup"><span data-stu-id="5aab8-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="5aab8-107">**值**</span><span class="sxs-lookup"><span data-stu-id="5aab8-107">**Value**</span></span>|<span data-ttu-id="5aab8-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5aab8-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5aab8-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="5aab8-109">TRUE</span></span>  <br/> |<span data-ttu-id="5aab8-110">除非在 ShapeSheet 中直接更改，否则 **ConnectorsSchemeIndex** 单元格不能更改其当前值。</span><span class="sxs-lookup"><span data-stu-id="5aab8-110">The **ConnectorsSchemeIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="5aab8-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="5aab8-111">FALSE</span></span>  <br/> |<span data-ttu-id="5aab8-112">**通过 UI，ConnectorsSchemeIndex** 单元格可以从其当前值更改。</span><span class="sxs-lookup"><span data-stu-id="5aab8-112">The **ConnectorsSchemeIndex** cell can be changed from its current value through the UI.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5aab8-113">备注</span><span class="sxs-lookup"><span data-stu-id="5aab8-113">Remarks</span></span>

<span data-ttu-id="5aab8-114">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockThemeConnectors** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5aab8-114">To get a reference to the **LockThemeConnectors** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5aab8-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5aab8-115">Cell name:</span></span>  <br/> | <span data-ttu-id="5aab8-116">LockThemeConnectors</span><span class="sxs-lookup"><span data-stu-id="5aab8-116">LockThemeConnectors</span></span>  <br/> |
   
<span data-ttu-id="5aab8-117">若要从程序按索引获取对 **LockThemeConnectors** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5aab8-117">To get a reference to the **LockThemeConnectors** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5aab8-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5aab8-118">Section index:</span></span>  <br/> |<span data-ttu-id="5aab8-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5aab8-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="5aab8-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="5aab8-120">Row index:</span></span>  <br/> |<span data-ttu-id="5aab8-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="5aab8-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="5aab8-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5aab8-122">Cell index:</span></span>  <br/> |<span data-ttu-id="5aab8-123">**visLockThemeConnectors**</span><span class="sxs-lookup"><span data-stu-id="5aab8-123">**visLockThemeConnectors**</span></span> <br/> |
   

