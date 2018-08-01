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
ms.openlocfilehash: 0e1eb67528b3e87bcfff5281dd1e0b2db3a0a4d5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780173"
---
# <a name="enablelineprops-cell-style-properties-section"></a><span data-ttu-id="4c0c4-103">EnableLineProps 单元格（“Style Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="4c0c4-103">EnableLineProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="4c0c4-104">确定样式是否包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="4c0c4-104">Determines whether a style includes line properties.</span></span>
  
|<span data-ttu-id="4c0c4-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4c0c4-105">**Value**</span></span>|<span data-ttu-id="4c0c4-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c0c4-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c0c4-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="4c0c4-107">TRUE</span></span>  <br/> |<span data-ttu-id="4c0c4-108">包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="4c0c4-108">Include line properties.</span></span>  <br/> |
|<span data-ttu-id="4c0c4-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="4c0c4-109">FALSE</span></span>  <br/> |<span data-ttu-id="4c0c4-110">不包括线条属性。</span><span class="sxs-lookup"><span data-stu-id="4c0c4-110">Exclude line properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c0c4-111">注解</span><span class="sxs-lookup"><span data-stu-id="4c0c4-111">Remarks</span></span>

<span data-ttu-id="4c0c4-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableLineProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-112">To get a reference to the EnableLineProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4c0c4-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-113">Cell name:</span></span>  <br/> |<span data-ttu-id="4c0c4-114">EnableLineProps</span><span class="sxs-lookup"><span data-stu-id="4c0c4-114">EnableLineProps</span></span>  <br/> |
   
<span data-ttu-id="4c0c4-115">要从某个程序按索引获取对 EnableLineProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-115">To get a reference to the EnableLineProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4c0c4-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-116">Section index:</span></span>  <br/> |<span data-ttu-id="4c0c4-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4c0c4-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4c0c4-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-118">Row index:</span></span>  <br/> |<span data-ttu-id="4c0c4-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="4c0c4-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="4c0c4-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4c0c4-120">Cell index:</span></span>  <br/> |<span data-ttu-id="4c0c4-121">**visStyleIncludesLine**</span><span class="sxs-lookup"><span data-stu-id="4c0c4-121">**visStyleIncludesLine**</span></span> <br/> |
   

