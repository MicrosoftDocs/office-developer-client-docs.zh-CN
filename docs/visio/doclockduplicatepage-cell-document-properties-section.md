---
title: 'DocLockDuplicatePage Cell (Document Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b08a6558-519f-44e0-aeff-9919544d515e
description: 确定文档中的页面是否可复制，作为布尔值。
ms.openlocfilehash: 3f3274c6cfadb81ef514a179279bdaed3543b654
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439658"
---
# <a name="doclockduplicatepage-cell-document-properties-section"></a><span data-ttu-id="86e67-103">DocLockDuplicatePage Cell (Document Properties Section) </span><span class="sxs-lookup"><span data-stu-id="86e67-103">DocLockDuplicatePage Cell (Document Properties Section)</span></span>

<span data-ttu-id="86e67-104">确定文档中的页面是否可复制，作为布尔值。</span><span class="sxs-lookup"><span data-stu-id="86e67-104">Determines whether pages in the document can be duplicated, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86e67-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="86e67-105">TRUE</span></span>  <br/> |<span data-ttu-id="86e67-106">**页面** 快捷菜单和 **Page.Duplicate** 自动化方法中的重复项均被禁用。</span><span class="sxs-lookup"><span data-stu-id="86e67-106">**Duplicate** in the page shortcut menu and the **Page.Duplicate** automation method are both disabled.</span></span>  <br/> |
|<span data-ttu-id="86e67-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="86e67-107">FALSE</span></span>  <br/> |<span data-ttu-id="86e67-108">可以复制页面。</span><span class="sxs-lookup"><span data-stu-id="86e67-108">The page can be duplicated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="86e67-109">备注</span><span class="sxs-lookup"><span data-stu-id="86e67-109">Remarks</span></span>

<span data-ttu-id="86e67-110">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **DocLockDuplicatePage** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="86e67-110">To get a reference to the **DocLockDuplicatePage** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="86e67-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="86e67-111">Cell name:</span></span>  <br/> | <span data-ttu-id="86e67-112">DocLockDuplicatePage</span><span class="sxs-lookup"><span data-stu-id="86e67-112">DocLockDuplicatePage</span></span>  <br/> |
   
<span data-ttu-id="86e67-113">若要从程序按索引获取对 **DocLockDuplicatePage** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="86e67-113">To get a reference to the **DocLockDuplicatePage** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="86e67-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="86e67-114">Section index:</span></span>  <br/> |<span data-ttu-id="86e67-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="86e67-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="86e67-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="86e67-116">Row index:</span></span>  <br/> |<span data-ttu-id="86e67-117">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="86e67-117">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="86e67-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="86e67-118">Cell index:</span></span>  <br/> |<span data-ttu-id="86e67-119">**visDocLockDuplicatePage**</span><span class="sxs-lookup"><span data-stu-id="86e67-119">**visDocLockDuplicatePage**</span></span> <br/> |
   

