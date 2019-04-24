---
title: PageLockDuplicate 单元格 ("Page Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fbaa7d64-06ef-46d6-81d5-9d7af1c14b65
description: 确定是否可以将页面复制为布尔值。
ms.openlocfilehash: 8ce730fcdc2dff5deac44d8c053b84e82a82d4cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283662"
---
# <a name="pagelockduplicate-cell-page-properties-section"></a><span data-ttu-id="c1323-103">PageLockDuplicate 单元格 ("Page Properties" 内容)</span><span class="sxs-lookup"><span data-stu-id="c1323-103">PageLockDuplicate Cell (Page Properties Section)</span></span>

<span data-ttu-id="c1323-104">确定是否可以将页面复制为布尔值。</span><span class="sxs-lookup"><span data-stu-id="c1323-104">Determines whether the page can be duplicated, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c1323-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="c1323-105">TRUE</span></span>  <br/> |<span data-ttu-id="c1323-106">\*\*\*\* 在页面快捷菜单和页面中重复 **。** 已对页面禁用重复的自动化方法。</span><span class="sxs-lookup"><span data-stu-id="c1323-106">**Duplicate** in the page shortcut menu and the **Page.Duplicate** automation method are both disabled for the page.</span></span>  <br/> |
|<span data-ttu-id="c1323-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="c1323-107">FALSE</span></span>  <br/> |<span data-ttu-id="c1323-108">可以复制页面。</span><span class="sxs-lookup"><span data-stu-id="c1323-108">The page can be duplicated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c1323-109">注解</span><span class="sxs-lookup"><span data-stu-id="c1323-109">Remarks</span></span>

<span data-ttu-id="c1323-110">若要从另一个公式按名称获取对**PageLockDuplicate**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="c1323-110">To get a reference to the **PageLockDuplicate** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c1323-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c1323-111">Cell name:</span></span>  <br/> | <span data-ttu-id="c1323-112">PageLockDuplicate</span><span class="sxs-lookup"><span data-stu-id="c1323-112">PageLockDuplicate</span></span>  <br/> |
   
<span data-ttu-id="c1323-113">若要从某个程序按索引获取对**PageLockDuplicate**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="c1323-113">To get a reference to the **PageLockDuplicate** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c1323-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c1323-114">Section index:</span></span>  <br/> |<span data-ttu-id="c1323-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c1323-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c1323-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="c1323-116">Row index:</span></span>  <br/> |<span data-ttu-id="c1323-117">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="c1323-117">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="c1323-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c1323-118">Cell index:</span></span>  <br/> |<span data-ttu-id="c1323-119">**visPageLockDuplicate**</span><span class="sxs-lookup"><span data-stu-id="c1323-119">**visPageLockDuplicate**</span></span> <br/> |
   

