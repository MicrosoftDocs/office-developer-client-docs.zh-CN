---
title: LockThemeConnectors 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae7ddd55-7bcc-4bb6-bab7-97806122f166
description: 防止 ConnectorsSchemeIndex 行的单元格中主题属性被更改通过应用新主题，或选择新连接器方案。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: c74bcf554f0f14de47480397a96680469826d2c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780647"
---
# <a name="lockthemeconnectors-cell-protection-section"></a><span data-ttu-id="caefe-104">LockThemeConnectors 单元格（“Protection”部分）</span><span class="sxs-lookup"><span data-stu-id="caefe-104">LockThemeConnectors Cell (Protection Section)</span></span>

<span data-ttu-id="caefe-105">防止**ConnectorsSchemeIndex**行的单元格中**主题属性**被更改通过应用新主题，或选择新连接器方案。</span><span class="sxs-lookup"><span data-stu-id="caefe-105">Prevents the **ConnectorsSchemeIndex** cell in the **Theme Properties** row from being altered by applying a new theme or selecting a new connector scheme.</span></span> <span data-ttu-id="caefe-106">不阻止用户手动编辑 ShapeSheet 中的此值。</span><span class="sxs-lookup"><span data-stu-id="caefe-106">Does not prevent users from manually editing this value in the ShapeSheet.</span></span> 
  
|<span data-ttu-id="caefe-107">**值**</span><span class="sxs-lookup"><span data-stu-id="caefe-107">**Value**</span></span>|<span data-ttu-id="caefe-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="caefe-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="caefe-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="caefe-109">TRUE</span></span>  <br/> |<span data-ttu-id="caefe-110">无法从其当前值更改**ConnectorsSchemeIndex**单元格，除非直接 ShapeSheet 中的更改。</span><span class="sxs-lookup"><span data-stu-id="caefe-110">The **ConnectorsSchemeIndex** cell cannot be changed from its current value unless changed in the ShapeSheet directly.</span></span>  <br/> |
|<span data-ttu-id="caefe-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="caefe-111">FALSE</span></span>  <br/> |<span data-ttu-id="caefe-112">可以从其当前值通过 UI 更改**ConnectorsSchemeIndex**单元格。</span><span class="sxs-lookup"><span data-stu-id="caefe-112">The **ConnectorsSchemeIndex** cell can be changed from its current value through the UI.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="caefe-113">说明</span><span class="sxs-lookup"><span data-stu-id="caefe-113">Remarks</span></span>

<span data-ttu-id="caefe-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeConnectors**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="caefe-114">To get a reference to the **LockThemeConnectors** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="caefe-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="caefe-115">Cell name:</span></span>  <br/> | <span data-ttu-id="caefe-116">LockThemeConnectors</span><span class="sxs-lookup"><span data-stu-id="caefe-116">LockThemeConnectors</span></span>  <br/> |
   
<span data-ttu-id="caefe-117">若要从某个程序按索引获取对**LockThemeConnectors**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="caefe-117">To get a reference to the **LockThemeConnectors** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="caefe-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="caefe-118">Section index:</span></span>  <br/> |<span data-ttu-id="caefe-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="caefe-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="caefe-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="caefe-120">Row index:</span></span>  <br/> |<span data-ttu-id="caefe-121">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="caefe-121">**visRowLock**</span></span> <br/> |
| <span data-ttu-id="caefe-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="caefe-122">Cell index:</span></span>  <br/> |<span data-ttu-id="caefe-123">**visLockThemeConnectors**</span><span class="sxs-lookup"><span data-stu-id="caefe-123">**visLockThemeConnectors**</span></span> <br/> |
   

