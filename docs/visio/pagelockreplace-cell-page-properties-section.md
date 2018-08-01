---
title: PageLockReplace 单元格（“Page Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应为该页禁用替换形状按钮。
ms.openlocfilehash: b3956b3e2f2fcd5c4f82089e08a6e32200374778
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780833"
---
# <a name="pagelockreplace-cell-page-properties-section"></a><span data-ttu-id="dc7bc-103">PageLockReplace 单元格（“Page Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="dc7bc-103">PageLockReplace Cell (Page Properties Section)</span></span>

<span data-ttu-id="dc7bc-104">指示是否应为该页禁用**替换形状**按钮。</span><span class="sxs-lookup"><span data-stu-id="dc7bc-104">Indicates whether the **Replace Shape** button should be disabled for this page.</span></span> 
  
|<span data-ttu-id="dc7bc-105">**值**</span><span class="sxs-lookup"><span data-stu-id="dc7bc-105">**Value**</span></span>|<span data-ttu-id="dc7bc-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="dc7bc-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dc7bc-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="dc7bc-107">TRUE</span></span>  <br/> |<span data-ttu-id="dc7bc-108">此页处于活动状态时，**更改形状**按钮为灰显状态。</span><span class="sxs-lookup"><span data-stu-id="dc7bc-108">The **Change Shape** button is grayed out when this page is active.</span></span>  <br/> |
|<span data-ttu-id="dc7bc-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="dc7bc-109">FALSE</span></span>  <br/> |<span data-ttu-id="dc7bc-110">此页不禁用**更改形状**按钮。</span><span class="sxs-lookup"><span data-stu-id="dc7bc-110">The **Change Shape** button is not disabled by this page.</span></span> <span data-ttu-id="dc7bc-111">该按钮仍可能灰色如果： **DocLockReplace** **DocumentSheet**上设置为**TRUE**;选中形状的**LockReplace**单元格设置为**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="dc7bc-111">The button may still be grayed out if: the **DocLockReplace** on the **DocumentSheet** is set to **TRUE**; the **LockReplace** cell for the selected shape is set to **TRUE**.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc7bc-112">说明</span><span class="sxs-lookup"><span data-stu-id="dc7bc-112">Remarks</span></span>

<span data-ttu-id="dc7bc-113">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**PageLockReplace**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-113">To get a reference to the **PageLockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc7bc-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-114">Cell name:</span></span>  <br/> | <span data-ttu-id="dc7bc-115">PageLockReplace</span><span class="sxs-lookup"><span data-stu-id="dc7bc-115">PageLockReplace</span></span>  <br/> |
   
<span data-ttu-id="dc7bc-116">若要从某个程序按索引获取对**PageLockReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-116">To get a reference to the **PageLockReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc7bc-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-117">Section index:</span></span>  <br/> |<span data-ttu-id="dc7bc-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="dc7bc-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="dc7bc-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-119">Row index:</span></span>  <br/> |<span data-ttu-id="dc7bc-120">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="dc7bc-120">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="dc7bc-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dc7bc-121">Cell index:</span></span>  <br/> |<span data-ttu-id="dc7bc-122">**visPageLockReplace**</span><span class="sxs-lookup"><span data-stu-id="dc7bc-122">**visPageLockReplace**</span></span> <br/> |
   

