---
title: EnableLineProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251696
localization_priority: Normal
ms.assetid: 9f619416-36ff-1479-6232-225c11827e01
description: 确定样式是否包括线条属性。
ms.openlocfilehash: 38964194626be052b2a168fa929b69ebe4b28e01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409998"
---
# <a name="enablelineprops-cell-style-properties-section"></a><span data-ttu-id="81a72-103">EnableLineProps 单元格（“Style Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="81a72-103">EnableLineProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="81a72-104">确定样式是否包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="81a72-104">Determines whether a style includes line properties.</span></span>
  
|<span data-ttu-id="81a72-105">**值**</span><span class="sxs-lookup"><span data-stu-id="81a72-105">**Value**</span></span>|<span data-ttu-id="81a72-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="81a72-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="81a72-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="81a72-107">TRUE</span></span>  <br/> |<span data-ttu-id="81a72-108">包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="81a72-108">Include line properties.</span></span>  <br/> |
|<span data-ttu-id="81a72-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="81a72-109">FALSE</span></span>  <br/> |<span data-ttu-id="81a72-110">不包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="81a72-110">Exclude line properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81a72-111">说明</span><span class="sxs-lookup"><span data-stu-id="81a72-111">Remarks</span></span>

<span data-ttu-id="81a72-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableLineProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="81a72-112">To get a reference to the EnableLineProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="81a72-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="81a72-113">Cell name:</span></span>  <br/> |<span data-ttu-id="81a72-114">EnableLineProps</span><span class="sxs-lookup"><span data-stu-id="81a72-114">EnableLineProps</span></span>  <br/> |
   
<span data-ttu-id="81a72-115">要从某个程序按索引获取对 EnableLineProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="81a72-115">To get a reference to the EnableLineProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="81a72-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="81a72-116">Section index:</span></span>  <br/> |<span data-ttu-id="81a72-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="81a72-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="81a72-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="81a72-118">Row index:</span></span>  <br/> |<span data-ttu-id="81a72-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="81a72-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="81a72-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="81a72-120">Cell index:</span></span>  <br/> |<span data-ttu-id="81a72-121">**visStyleIncludesLine**</span><span class="sxs-lookup"><span data-stu-id="81a72-121">**visStyleIncludesLine**</span></span> <br/> |
   

