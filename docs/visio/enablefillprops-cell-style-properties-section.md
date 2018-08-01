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
ms.openlocfilehash: 399af4b9d1a2245ea7a9b91ebbf036eb122f15bd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780181"
---
# <a name="enablefillprops-cell-style-properties-section"></a><span data-ttu-id="82fb6-103">EnableFillProps 单元格（“Style Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="82fb6-103">EnableFillProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="82fb6-104">确定样式是否包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="82fb6-104">Determines whether a style includes fill properties.</span></span>
  
|<span data-ttu-id="82fb6-105">**值**</span><span class="sxs-lookup"><span data-stu-id="82fb6-105">**Value**</span></span>|<span data-ttu-id="82fb6-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="82fb6-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="82fb6-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="82fb6-107">TRUE</span></span>  <br/> |<span data-ttu-id="82fb6-108">包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="82fb6-108">Include fill properties.</span></span>  <br/> |
|<span data-ttu-id="82fb6-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="82fb6-109">FALSE</span></span>  <br/> |<span data-ttu-id="82fb6-110">不包括填充属性。</span><span class="sxs-lookup"><span data-stu-id="82fb6-110">Exclude fill properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="82fb6-111">注解</span><span class="sxs-lookup"><span data-stu-id="82fb6-111">Remarks</span></span>

<span data-ttu-id="82fb6-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableFillProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="82fb6-112">To get a reference to the EnableFillProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="82fb6-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="82fb6-113">Cell name:</span></span>  <br/> |<span data-ttu-id="82fb6-114">EnableFillProps</span><span class="sxs-lookup"><span data-stu-id="82fb6-114">EnableFillProps</span></span>  <br/> |
   
<span data-ttu-id="82fb6-115">要从某个程序按索引获取对 EnableFillProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="82fb6-115">To get a reference to the EnableFillProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="82fb6-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="82fb6-116">Section index:</span></span>  <br/> |<span data-ttu-id="82fb6-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="82fb6-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="82fb6-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="82fb6-118">Row index:</span></span>  <br/> |<span data-ttu-id="82fb6-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="82fb6-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="82fb6-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="82fb6-120">Cell index:</span></span>  <br/> |<span data-ttu-id="82fb6-121">**visStyleIncludesFill**</span><span class="sxs-lookup"><span data-stu-id="82fb6-121">**visStyleIncludesFill**</span></span> <br/> |
   

