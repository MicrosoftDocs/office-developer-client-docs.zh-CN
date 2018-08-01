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
ms.openlocfilehash: 2ef5ea12669a7a6a2b37d599afd24635f7509ac2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780634"
---
# <a name="lockpreview-cell-document-properties-section"></a><span data-ttu-id="3529c-103">LockPreview 单元格（“Document Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="3529c-103">LockPreview Cell (Document Properties Section)</span></span>

<span data-ttu-id="3529c-104">确定每次保存绘图时是否保存预览。</span><span class="sxs-lookup"><span data-stu-id="3529c-104">Determines whether a preview is saved each time you save a drawing.</span></span>
  
|<span data-ttu-id="3529c-105">**值**</span><span class="sxs-lookup"><span data-stu-id="3529c-105">**Value**</span></span>|<span data-ttu-id="3529c-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="3529c-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="3529c-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="3529c-107">TRUE</span></span>  <br/> | <span data-ttu-id="3529c-108">每次保存绘图时不保存预览。</span><span class="sxs-lookup"><span data-stu-id="3529c-108">Do not save a preview each time a drawing is saved.</span></span>  <br/> |
| <span data-ttu-id="3529c-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="3529c-109">FALSE</span></span>  <br/> | <span data-ttu-id="3529c-110">每次保存绘图时保存预览。</span><span class="sxs-lookup"><span data-stu-id="3529c-110">Save a preview each time a drawing is saved.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3529c-111">注释</span><span class="sxs-lookup"><span data-stu-id="3529c-111">Remarks</span></span>

<span data-ttu-id="3529c-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LockPreview 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="3529c-112">To get a reference to the LockPreview cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3529c-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3529c-113">Cell name:</span></span>  <br/> | <span data-ttu-id="3529c-114">LockPreview</span><span class="sxs-lookup"><span data-stu-id="3529c-114">LockPreview</span></span>  <br/> |
   
<span data-ttu-id="3529c-115">要从某个程序按索引获取对 LockPreview 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="3529c-115">To get a reference to the LockPreview cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3529c-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3529c-116">Section index:</span></span>  <br/> |<span data-ttu-id="3529c-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3529c-117">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3529c-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="3529c-118">Row index:</span></span>  <br/> |<span data-ttu-id="3529c-119">**visRowDoc**</span><span class="sxs-lookup"><span data-stu-id="3529c-119">**visRowDoc**</span></span> <br/> |
| <span data-ttu-id="3529c-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3529c-120">Cell index:</span></span>  <br/> |<span data-ttu-id="3529c-121">**visDocLockPreview**</span><span class="sxs-lookup"><span data-stu-id="3529c-121">**visDocLockPreview**</span></span> <br/> |
   

