---
title: DocLockReplace 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74eae5e5-80ab-4e10-b292-e58a6d7607d2
description: 确定是否应为此文档禁用用户界面的替换形状。
ms.openlocfilehash: 41552ddad4e48680960c45869ded5cf4f80d760f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780140"
---
# <a name="doclockreplace-cell-document-properties-section"></a><span data-ttu-id="6c5fe-103">DocLockReplace 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="6c5fe-103">DocLockReplace Cell (Document Properties Section)</span></span>

<span data-ttu-id="6c5fe-104">确定是否应为此文档禁用用户界面的替换形状。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-104">Determines whether the replace shape UI should be disabled for this document.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6c5fe-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="6c5fe-105">TRUE</span></span>  <br/> |<span data-ttu-id="6c5fe-106">为灰显状态**替换形状**按钮，在 UI 中。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-106">The **Replace Shape** button is grayed out in the UI.</span></span>  <br/> |
|<span data-ttu-id="6c5fe-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="6c5fe-107">FALSE</span></span>  <br/> |<span data-ttu-id="6c5fe-108">**替换形状**按钮处于活动状态的用户界面中。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-108">The **Replace Shape** button is active in the UI.</span></span> <span data-ttu-id="6c5fe-109">用户可以使用本文档中的替换形状功能。</span><span class="sxs-lookup"><span data-stu-id="6c5fe-109">Users can use the Replace Shape feature in this document.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c5fe-110">说明</span><span class="sxs-lookup"><span data-stu-id="6c5fe-110">Remarks</span></span>

<span data-ttu-id="6c5fe-111">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**DocLockReplace**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-111">To get a reference to the **DocLockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c5fe-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-112">Cell name:</span></span>  <br/> | <span data-ttu-id="6c5fe-113">DocLocReplace</span><span class="sxs-lookup"><span data-stu-id="6c5fe-113">DocLocReplace</span></span>  <br/> |
   
<span data-ttu-id="6c5fe-114">若要从某个程序按索引获取对**DocLocReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-114">To get a reference to the **DocLocReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c5fe-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-115">Section index:</span></span>  <br/> |<span data-ttu-id="6c5fe-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6c5fe-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6c5fe-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-117">Row index:</span></span>  <br/> |<span data-ttu-id="6c5fe-118">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="6c5fe-118">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="6c5fe-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6c5fe-119">Cell index:</span></span>  <br/> |<span data-ttu-id="6c5fe-120">* * visDocLockReplace * *</span><span class="sxs-lookup"><span data-stu-id="6c5fe-120">**visDocLockReplace **</span></span> <br/> |
   

