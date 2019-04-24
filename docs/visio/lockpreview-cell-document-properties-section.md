---
title: LockPreview 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251742
localization_priority: Normal
ms.assetid: 5a2bb1a7-e688-d32f-f231-ac6916d838a6
description: 确定每次保存绘图时是否保存预览。
ms.openlocfilehash: 91362d8a88cf6db2f4807c655a6d071ebbc731f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348326"
---
# <a name="lockpreview-cell-document-properties-section"></a><span data-ttu-id="13369-103">LockPreview 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="13369-103">LockPreview Cell (Document Properties Section)</span></span>

<span data-ttu-id="13369-104">确定每次保存绘图时是否保存预览。</span><span class="sxs-lookup"><span data-stu-id="13369-104">Determines whether a preview is saved each time you save a drawing.</span></span>
  
|<span data-ttu-id="13369-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="13369-105">**Value**</span></span>|<span data-ttu-id="13369-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="13369-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="13369-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="13369-107">TRUE</span></span>  <br/> | <span data-ttu-id="13369-108">每次保存绘图时不保存预览。</span><span class="sxs-lookup"><span data-stu-id="13369-108">Do not save a preview each time a drawing is saved.</span></span>  <br/> |
| <span data-ttu-id="13369-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="13369-109">FALSE</span></span>  <br/> | <span data-ttu-id="13369-110">每次保存绘图时保存预览。</span><span class="sxs-lookup"><span data-stu-id="13369-110">Save a preview each time a drawing is saved.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13369-111">注解</span><span class="sxs-lookup"><span data-stu-id="13369-111">Remarks</span></span>

<span data-ttu-id="13369-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockPreview 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="13369-112">To get a reference to the LockPreview cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="13369-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="13369-113">Cell name:</span></span>  <br/> | <span data-ttu-id="13369-114">LockPreview</span><span class="sxs-lookup"><span data-stu-id="13369-114">LockPreview</span></span>  <br/> |
   
<span data-ttu-id="13369-115">要从某个程序按索引获取对 LockPreview 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="13369-115">To get a reference to the LockPreview cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="13369-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="13369-116">Section index:</span></span>  <br/> |<span data-ttu-id="13369-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="13369-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="13369-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="13369-118">Row index:</span></span>  <br/> |<span data-ttu-id="13369-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="13369-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="13369-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="13369-120">Cell index:</span></span>  <br/> |<span data-ttu-id="13369-121">**visDocLockPreview**</span><span class="sxs-lookup"><span data-stu-id="13369-121">**visDocLockPreview**</span></span> <br/> |
   

