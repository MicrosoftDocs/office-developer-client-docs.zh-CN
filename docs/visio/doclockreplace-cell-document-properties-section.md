---
title: 'DocLockReplace Cell (Document Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74eae5e5-80ab-4e10-b292-e58a6d7607d2
description: 确定是否应禁用此文档的替换形状 UI。
ms.openlocfilehash: cfec9b3c51a170c549fdd0d1b0b3597c030c410c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413421"
---
# <a name="doclockreplace-cell-document-properties-section"></a><span data-ttu-id="7e681-103">DocLockReplace Cell (Document Properties Section) </span><span class="sxs-lookup"><span data-stu-id="7e681-103">DocLockReplace Cell (Document Properties Section)</span></span>

<span data-ttu-id="7e681-104">确定是否应禁用此文档的替换形状 UI。</span><span class="sxs-lookup"><span data-stu-id="7e681-104">Determines whether the replace shape UI should be disabled for this document.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7e681-105">TRUE</span><span class="sxs-lookup"><span data-stu-id="7e681-105">TRUE</span></span>  <br/> |<span data-ttu-id="7e681-106">" **替换形状"** 按钮在 UI 中灰显。</span><span class="sxs-lookup"><span data-stu-id="7e681-106">The **Replace Shape** button is grayed out in the UI.</span></span>  <br/> |
|<span data-ttu-id="7e681-107">FALSE</span><span class="sxs-lookup"><span data-stu-id="7e681-107">FALSE</span></span>  <br/> |<span data-ttu-id="7e681-108">" **替换形状"** 按钮在 UI 中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="7e681-108">The **Replace Shape** button is active in the UI.</span></span> <span data-ttu-id="7e681-109">用户可以使用本文档中的"替换形状"功能。</span><span class="sxs-lookup"><span data-stu-id="7e681-109">Users can use the Replace Shape feature in this document.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e681-110">备注</span><span class="sxs-lookup"><span data-stu-id="7e681-110">Remarks</span></span>

<span data-ttu-id="7e681-111">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **DocLockReplace** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7e681-111">To get a reference to the **DocLockReplace** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e681-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7e681-112">Cell name:</span></span>  <br/> | <span data-ttu-id="7e681-113">DocLocReplace</span><span class="sxs-lookup"><span data-stu-id="7e681-113">DocLocReplace</span></span>  <br/> |
   
<span data-ttu-id="7e681-114">若要从程序按索引获取对 **DocLocReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7e681-114">To get a reference to the **DocLocReplace** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7e681-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7e681-115">Section index:</span></span>  <br/> |<span data-ttu-id="7e681-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7e681-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7e681-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="7e681-117">Row index:</span></span>  <br/> |<span data-ttu-id="7e681-118">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="7e681-118">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="7e681-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7e681-119">Cell index:</span></span>  <br/> |<span data-ttu-id="7e681-120">\*\*visDocLockReplace \*\*</span><span class="sxs-lookup"><span data-stu-id="7e681-120">\*\*visDocLockReplace \*\*</span></span> <br/> |
   

