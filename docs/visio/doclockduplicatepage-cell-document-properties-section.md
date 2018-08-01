---
title: DocLockDuplicatePage 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b08a6558-519f-44e0-aeff-9919544d515e
description: 确定是否在文档中的页面可以进行复制，作为一个布尔值。
ms.openlocfilehash: 97bca23a7dc9150f66eb0c87834fca72c215448b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780116"
---
# <a name="doclockduplicatepage-cell-document-properties-section"></a><span data-ttu-id="c7ea0-103">DocLockDuplicatePage 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="c7ea0-103">DocLockDuplicatePage Cell (Document Properties Section)</span></span>

<span data-ttu-id="c7ea0-104">确定是否在文档中的页面可以进行复制，作为一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="c7ea0-104">Determines whether pages in the document can be duplicated, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c7ea0-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="c7ea0-105">TRUE</span></span>  <br/> |<span data-ttu-id="c7ea0-106">页面的快捷菜单和**Page.Duplicate**自动化方法中的**重复**将被禁用。</span><span class="sxs-lookup"><span data-stu-id="c7ea0-106">**Duplicate** in the page shortcut menu and the **Page.Duplicate** automation method are both disabled.</span></span>  <br/> |
|<span data-ttu-id="c7ea0-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="c7ea0-107">FALSE</span></span>  <br/> |<span data-ttu-id="c7ea0-108">可以复制页面。</span><span class="sxs-lookup"><span data-stu-id="c7ea0-108">The page can be duplicated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c7ea0-109">说明</span><span class="sxs-lookup"><span data-stu-id="c7ea0-109">Remarks</span></span>

<span data-ttu-id="c7ea0-110">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**DocLockDuplicatePage**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-110">To get a reference to the **DocLockDuplicatePage** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c7ea0-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-111">Cell name:</span></span>  <br/> | <span data-ttu-id="c7ea0-112">DocLockDuplicatePage</span><span class="sxs-lookup"><span data-stu-id="c7ea0-112">DocLockDuplicatePage</span></span>  <br/> |
   
<span data-ttu-id="c7ea0-113">若要从某个程序按索引获取对**DocLockDuplicatePage**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-113">To get a reference to the **DocLockDuplicatePage** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c7ea0-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-114">Section index:</span></span>  <br/> |<span data-ttu-id="c7ea0-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="c7ea0-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="c7ea0-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-116">Row index:</span></span>  <br/> |<span data-ttu-id="c7ea0-117">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="c7ea0-117">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="c7ea0-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c7ea0-118">Cell index:</span></span>  <br/> |<span data-ttu-id="c7ea0-119">**visDocLockDuplicatePage**</span><span class="sxs-lookup"><span data-stu-id="c7ea0-119">**visDocLockDuplicatePage**</span></span> <br/> |
   

