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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418860"
---
# <a name="lockpreview-cell-document-properties-section"></a><span data-ttu-id="03bf4-103">LockPreview 单元格（“Document Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="03bf4-103">LockPreview Cell (Document Properties Section)</span></span>

<span data-ttu-id="03bf4-104">确定每次保存绘图时是否保存预览。</span><span class="sxs-lookup"><span data-stu-id="03bf4-104">Determines whether a preview is saved each time you save a drawing.</span></span>
  
|<span data-ttu-id="03bf4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="03bf4-105">**Value**</span></span>|<span data-ttu-id="03bf4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="03bf4-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="03bf4-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="03bf4-107">TRUE</span></span>  <br/> | <span data-ttu-id="03bf4-108">每次保存绘图时不保存预览。</span><span class="sxs-lookup"><span data-stu-id="03bf4-108">Do not save a preview each time a drawing is saved.</span></span>  <br/> |
| <span data-ttu-id="03bf4-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="03bf4-109">FALSE</span></span>  <br/> | <span data-ttu-id="03bf4-110">每次保存绘图时保存预览。</span><span class="sxs-lookup"><span data-stu-id="03bf4-110">Save a preview each time a drawing is saved.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03bf4-111">说明</span><span class="sxs-lookup"><span data-stu-id="03bf4-111">Remarks</span></span>

<span data-ttu-id="03bf4-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockPreview 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="03bf4-112">To get a reference to the LockPreview cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="03bf4-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="03bf4-113">Cell name:</span></span>  <br/> | <span data-ttu-id="03bf4-114">LockPreview</span><span class="sxs-lookup"><span data-stu-id="03bf4-114">LockPreview</span></span>  <br/> |
   
<span data-ttu-id="03bf4-115">要从某个程序按索引获取对 LockPreview 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="03bf4-115">To get a reference to the LockPreview cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="03bf4-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="03bf4-116">Section index:</span></span>  <br/> |<span data-ttu-id="03bf4-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="03bf4-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="03bf4-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="03bf4-118">Row index:</span></span>  <br/> |<span data-ttu-id="03bf4-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="03bf4-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="03bf4-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="03bf4-120">Cell index:</span></span>  <br/> |<span data-ttu-id="03bf4-121">**visDocLockPreview**</span><span class="sxs-lookup"><span data-stu-id="03bf4-121">**visDocLockPreview**</span></span> <br/> |
   

