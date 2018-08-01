---
title: PageLockDuplicate 单元格（“Page Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fbaa7d64-06ef-46d6-81d5-9d7af1c14b65
description: 确定是否页面可以进行复制，作为一个布尔值。
ms.openlocfilehash: 6cfe8f7a33942f51130ef103b8aba70a5c38b37d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780827"
---
# <a name="pagelockduplicate-cell-page-properties-section"></a><span data-ttu-id="6c6c6-103">PageLockDuplicate 单元格（“Page Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="6c6c6-103">PageLockDuplicate Cell (Page Properties Section)</span></span>

<span data-ttu-id="6c6c6-104">确定是否页面可以进行复制，作为一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-104">Determines whether the page can be duplicated, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6c6c6-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="6c6c6-105">TRUE</span></span>  <br/> |<span data-ttu-id="6c6c6-106">页面的快捷菜单和**Page.Duplicate**自动化方法中的**重复**会同时禁用页面。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-106">**Duplicate** in the page shortcut menu and the **Page.Duplicate** automation method are both disabled for the page.</span></span>  <br/> |
|<span data-ttu-id="6c6c6-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="6c6c6-107">FALSE</span></span>  <br/> |<span data-ttu-id="6c6c6-108">可以复制页面。</span><span class="sxs-lookup"><span data-stu-id="6c6c6-108">The page can be duplicated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c6c6-109">说明</span><span class="sxs-lookup"><span data-stu-id="6c6c6-109">Remarks</span></span>

<span data-ttu-id="6c6c6-110">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**PageLockDuplicate**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-110">To get a reference to the **PageLockDuplicate** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c6c6-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-111">Cell name:</span></span>  <br/> | <span data-ttu-id="6c6c6-112">PageLockDuplicate</span><span class="sxs-lookup"><span data-stu-id="6c6c6-112">PageLockDuplicate</span></span>  <br/> |
   
<span data-ttu-id="6c6c6-113">若要从某个程序按索引获取对**PageLockDuplicate**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-113">To get a reference to the **PageLockDuplicate** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c6c6-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-114">Section index:</span></span>  <br/> |<span data-ttu-id="6c6c6-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6c6c6-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6c6c6-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-116">Row index:</span></span>  <br/> |<span data-ttu-id="6c6c6-117">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="6c6c6-117">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="6c6c6-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6c6c6-118">Cell index:</span></span>  <br/> |<span data-ttu-id="6c6c6-119">**visPageLockDuplicate**</span><span class="sxs-lookup"><span data-stu-id="6c6c6-119">**visPageLockDuplicate**</span></span> <br/> |
   

