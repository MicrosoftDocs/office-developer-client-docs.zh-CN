---
title: EnableFillProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm300
localization_priority: Normal
ms.assetid: 2b3334de-588c-6cf3-bc88-be03ae71b1a6
description: 确定样式是否包括填充属性。
ms.openlocfilehash: 55191cb28d5777f7fb65a3a1e4be890e6dda4e8b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406008"
---
# <a name="enablefillprops-cell-style-properties-section"></a><span data-ttu-id="60ffd-103">EnableFillProps 单元格（“Style Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="60ffd-103">EnableFillProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="60ffd-104">确定样式是否包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="60ffd-104">Determines whether a style includes fill properties.</span></span>
  
|<span data-ttu-id="60ffd-105">**值**</span><span class="sxs-lookup"><span data-stu-id="60ffd-105">**Value**</span></span>|<span data-ttu-id="60ffd-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="60ffd-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60ffd-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="60ffd-107">TRUE</span></span>  <br/> |<span data-ttu-id="60ffd-108">包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="60ffd-108">Include fill properties.</span></span>  <br/> |
|<span data-ttu-id="60ffd-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="60ffd-109">FALSE</span></span>  <br/> |<span data-ttu-id="60ffd-110">不包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="60ffd-110">Exclude fill properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="60ffd-111">说明</span><span class="sxs-lookup"><span data-stu-id="60ffd-111">Remarks</span></span>

<span data-ttu-id="60ffd-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableFillProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="60ffd-112">To get a reference to the EnableFillProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="60ffd-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="60ffd-113">Cell name:</span></span>  <br/> |<span data-ttu-id="60ffd-114">EnableFillProps</span><span class="sxs-lookup"><span data-stu-id="60ffd-114">EnableFillProps</span></span>  <br/> |
   
<span data-ttu-id="60ffd-115">要从某个程序按索引获取对 EnableFillProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="60ffd-115">To get a reference to the EnableFillProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="60ffd-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="60ffd-116">Section index:</span></span>  <br/> |<span data-ttu-id="60ffd-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="60ffd-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="60ffd-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="60ffd-118">Row index:</span></span>  <br/> |<span data-ttu-id="60ffd-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="60ffd-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="60ffd-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="60ffd-120">Cell index:</span></span>  <br/> |<span data-ttu-id="60ffd-121">**visStyleIncludesFill**</span><span class="sxs-lookup"><span data-stu-id="60ffd-121">**visStyleIncludesFill**</span></span> <br/> |
   

