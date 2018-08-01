---
title: Can Glue 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251287
localization_priority: Normal
ms.assetid: 1c4c4ae2-b3fa-ed45-c6e5-22bedb2523db
description: 确定控制手柄能否粘附到其他形状上。
ms.openlocfilehash: c7b6764e25deab3345b7b3cecd6cf12dde74a84c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779799"
---
# <a name="can-glue-cell-controls-section"></a><span data-ttu-id="77147-103">Can Glue 单元格（“Controls”部分）</span><span class="sxs-lookup"><span data-stu-id="77147-103">Can Glue Cell (Controls Section)</span></span>

<span data-ttu-id="77147-104">确定控制手柄能否粘附到其他形状上。</span><span class="sxs-lookup"><span data-stu-id="77147-104">Determines whether a control handle can be glued to other shapes.</span></span>
  
|<span data-ttu-id="77147-105">**值**</span><span class="sxs-lookup"><span data-stu-id="77147-105">**Value**</span></span>|<span data-ttu-id="77147-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="77147-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="77147-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="77147-107">TRUE</span></span>  <br/> | <span data-ttu-id="77147-108">控制手柄能够粘附。</span><span class="sxs-lookup"><span data-stu-id="77147-108">Control handle can be glued.</span></span>  <br/> |
| <span data-ttu-id="77147-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="77147-109">FALSE</span></span>  <br/> | <span data-ttu-id="77147-110">控制手柄不能粘附。</span><span class="sxs-lookup"><span data-stu-id="77147-110">Control handle cannot be glued.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="77147-111">注释</span><span class="sxs-lookup"><span data-stu-id="77147-111">Remarks</span></span>

<span data-ttu-id="77147-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Can Glue 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="77147-112">To get a reference to the Can Glue cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="77147-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="77147-113">Cell name:</span></span>  <br/> | <span data-ttu-id="77147-114">控件。</span><span class="sxs-lookup"><span data-stu-id="77147-114">Controls.</span></span>  <span data-ttu-id="77147-115">*名称*。CanGluewhere 控件。</span><span class="sxs-lookup"><span data-stu-id="77147-115">*name*  .CanGluewhere Controls.</span></span>  <span data-ttu-id="77147-116">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="77147-116">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="77147-117">要从某个程序按索引获取对 Can Glue 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="77147-117">To get a reference to the Can Glue cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="77147-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="77147-118">Section index:</span></span>  <br/> |<span data-ttu-id="77147-119">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="77147-119">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="77147-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="77147-120">Row index:</span></span>  <br/> |<span data-ttu-id="77147-121">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="77147-121">**visRowControl** +  *i*            where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
| <span data-ttu-id="77147-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="77147-122">Cell index:</span></span>  <br/> |<span data-ttu-id="77147-123">**visCtlGlue**</span><span class="sxs-lookup"><span data-stu-id="77147-123">**visCtlGlue**</span></span> <br/> |
   

