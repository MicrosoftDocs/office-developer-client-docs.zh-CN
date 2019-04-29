---
title: DocLockDuplicatePage 单元格 ("Document Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b08a6558-519f-44e0-aeff-9919544d515e
description: 确定是否可以将文档中的页面复制为布尔值。
ms.openlocfilehash: 3f3274c6cfadb81ef514a179279bdaed3543b654
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439658"
---
# <a name="doclockduplicatepage-cell-document-properties-section"></a><span data-ttu-id="d81bb-103">DocLockDuplicatePage 单元格 ("Document Properties" 内容)</span><span class="sxs-lookup"><span data-stu-id="d81bb-103">DocLockDuplicatePage Cell (Document Properties Section)</span></span>

<span data-ttu-id="d81bb-104">确定是否可以将文档中的页面复制为布尔值。</span><span class="sxs-lookup"><span data-stu-id="d81bb-104">Determines whether pages in the document can be duplicated, as a Boolean.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d81bb-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="d81bb-105">TRUE</span></span>  <br/> |<span data-ttu-id="d81bb-106">\*\*\*\* 在页面快捷菜单和页面中重复 **。重复**的自动化方法均被禁用。</span><span class="sxs-lookup"><span data-stu-id="d81bb-106">**Duplicate** in the page shortcut menu and the **Page.Duplicate** automation method are both disabled.</span></span>  <br/> |
|<span data-ttu-id="d81bb-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="d81bb-107">FALSE</span></span>  <br/> |<span data-ttu-id="d81bb-108">可以复制页面。</span><span class="sxs-lookup"><span data-stu-id="d81bb-108">The page can be duplicated.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d81bb-109">说明</span><span class="sxs-lookup"><span data-stu-id="d81bb-109">Remarks</span></span>

<span data-ttu-id="d81bb-110">若要从另一个公式按名称获取对**DocLockDuplicatePage**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="d81bb-110">To get a reference to the **DocLockDuplicatePage** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d81bb-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d81bb-111">Cell name:</span></span>  <br/> | <span data-ttu-id="d81bb-112">DocLockDuplicatePage</span><span class="sxs-lookup"><span data-stu-id="d81bb-112">DocLockDuplicatePage</span></span>  <br/> |
   
<span data-ttu-id="d81bb-113">若要从某个程序按索引获取对**DocLockDuplicatePage**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="d81bb-113">To get a reference to the **DocLockDuplicatePage** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d81bb-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d81bb-114">Section index:</span></span>  <br/> |<span data-ttu-id="d81bb-115">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d81bb-115">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="d81bb-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="d81bb-116">Row index:</span></span>  <br/> |<span data-ttu-id="d81bb-117">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="d81bb-117">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="d81bb-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d81bb-118">Cell index:</span></span>  <br/> |<span data-ttu-id="d81bb-119">**visDocLockDuplicatePage**</span><span class="sxs-lookup"><span data-stu-id="d81bb-119">**visDocLockDuplicatePage**</span></span> <br/> |
   

