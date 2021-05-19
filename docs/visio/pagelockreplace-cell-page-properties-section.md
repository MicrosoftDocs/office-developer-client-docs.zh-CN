---
title: 'PageLockReplace Cell (Page Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应该为此页禁用"替换形状"按钮。
ms.openlocfilehash: c0495d47a81ed7a23e758c531f7d754291c47852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433099"
---
# <a name="pagelockreplace-cell-page-properties-section"></a><span data-ttu-id="bffa9-103">PageLockReplace Cell (Page Properties Section) </span><span class="sxs-lookup"><span data-stu-id="bffa9-103">PageLockReplace Cell (Page Properties Section)</span></span>

<span data-ttu-id="bffa9-104">指示是否应该 **为此页** 禁用"替换形状"按钮。</span><span class="sxs-lookup"><span data-stu-id="bffa9-104">Indicates whether the **Replace Shape** button should be disabled for this page.</span></span> 
  
|<span data-ttu-id="bffa9-105">**值**</span><span class="sxs-lookup"><span data-stu-id="bffa9-105">**Value**</span></span>|<span data-ttu-id="bffa9-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="bffa9-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bffa9-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="bffa9-107">TRUE</span></span>  <br/> |<span data-ttu-id="bffa9-108">此页面 **处于活动状态** 时，"更改形状"按钮灰显。</span><span class="sxs-lookup"><span data-stu-id="bffa9-108">The **Change Shape** button is grayed out when this page is active.</span></span>  <br/> |
|<span data-ttu-id="bffa9-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="bffa9-109">FALSE</span></span>  <br/> |<span data-ttu-id="bffa9-110">此页面 **不会** 禁用"更改形状"按钮。</span><span class="sxs-lookup"><span data-stu-id="bffa9-110">The **Change Shape** button is not disabled by this page.</span></span> <span data-ttu-id="bffa9-111">如果 **DocumentSheet** 上的 **DocLockReplace** 设置为 **TRUE，** 该按钮可能仍显示为灰色;所选 **形状的 LockReplace** 单元格设置为 **TRUE**。</span><span class="sxs-lookup"><span data-stu-id="bffa9-111">The button may still be grayed out if: the **DocLockReplace** on the **DocumentSheet** is set to **TRUE**; the **LockReplace** cell for the selected shape is set to **TRUE**.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bffa9-112">备注</span><span class="sxs-lookup"><span data-stu-id="bffa9-112">Remarks</span></span>

<span data-ttu-id="bffa9-113">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **PageLockReplace** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="bffa9-113">To get a reference to the **PageLockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bffa9-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="bffa9-114">Cell name:</span></span>  <br/> | <span data-ttu-id="bffa9-115">PageLockReplace</span><span class="sxs-lookup"><span data-stu-id="bffa9-115">PageLockReplace</span></span>  <br/> |
   
<span data-ttu-id="bffa9-116">若要从程序按索引获取对 **PageLockReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="bffa9-116">To get a reference to the **PageLockReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="bffa9-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="bffa9-117">Section index:</span></span>  <br/> |<span data-ttu-id="bffa9-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="bffa9-118">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="bffa9-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="bffa9-119">Row index:</span></span>  <br/> |<span data-ttu-id="bffa9-120">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="bffa9-120">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="bffa9-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="bffa9-121">Cell index:</span></span>  <br/> |<span data-ttu-id="bffa9-122">**visPageLockReplace**</span><span class="sxs-lookup"><span data-stu-id="bffa9-122">**visPageLockReplace**</span></span> <br/> |
   

