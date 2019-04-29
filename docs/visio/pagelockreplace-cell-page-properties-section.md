---
title: PageLockReplace 单元格 ("Page Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应对此页面禁用 "替换形状" 按钮。
ms.openlocfilehash: c0495d47a81ed7a23e758c531f7d754291c47852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433099"
---
# <a name="pagelockreplace-cell-page-properties-section"></a><span data-ttu-id="7faee-103">PageLockReplace 单元格 ("Page Properties" 内容)</span><span class="sxs-lookup"><span data-stu-id="7faee-103">PageLockReplace Cell (Page Properties Section)</span></span>

<span data-ttu-id="7faee-104">指示是否应对此页面禁用 "**替换形状**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7faee-104">Indicates whether the **Replace Shape** button should be disabled for this page.</span></span> 
  
|<span data-ttu-id="7faee-105">**值**</span><span class="sxs-lookup"><span data-stu-id="7faee-105">**Value**</span></span>|<span data-ttu-id="7faee-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="7faee-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7faee-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="7faee-107">TRUE</span></span>  <br/> |<span data-ttu-id="7faee-108">当此页面处于活动状态时, "**更改形状**" 按钮将变灰。</span><span class="sxs-lookup"><span data-stu-id="7faee-108">The **Change Shape** button is grayed out when this page is active.</span></span>  <br/> |
|<span data-ttu-id="7faee-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="7faee-109">FALSE</span></span>  <br/> |<span data-ttu-id="7faee-110">此页面未禁用 "**更改形状**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7faee-110">The **Change Shape** button is not disabled by this page.</span></span> <span data-ttu-id="7faee-111">如果: **DocumentSheet**上的**DocLockReplace**设置为**TRUE**, 则该按钮可能仍为灰色;选定形状的**LockReplace**单元格设置为**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="7faee-111">The button may still be grayed out if: the **DocLockReplace** on the **DocumentSheet** is set to **TRUE**; the **LockReplace** cell for the selected shape is set to **TRUE**.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7faee-112">说明</span><span class="sxs-lookup"><span data-stu-id="7faee-112">Remarks</span></span>

<span data-ttu-id="7faee-113">若要从另一个公式按名称获取对**PageLockReplace**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="7faee-113">To get a reference to the **PageLockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7faee-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7faee-114">Cell name:</span></span>  <br/> | <span data-ttu-id="7faee-115">PageLockReplace</span><span class="sxs-lookup"><span data-stu-id="7faee-115">PageLockReplace</span></span>  <br/> |
   
<span data-ttu-id="7faee-116">若要从某个程序按索引获取对**PageLockReplace**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="7faee-116">To get a reference to the **PageLockReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7faee-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7faee-117">Section index:</span></span>  <br/> |<span data-ttu-id="7faee-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7faee-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7faee-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="7faee-119">Row index:</span></span>  <br/> |<span data-ttu-id="7faee-120">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="7faee-120">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="7faee-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7faee-121">Cell index:</span></span>  <br/> |<span data-ttu-id="7faee-122">**visPageLockReplace**</span><span class="sxs-lookup"><span data-stu-id="7faee-122">**visPageLockReplace**</span></span> <br/> |
   

