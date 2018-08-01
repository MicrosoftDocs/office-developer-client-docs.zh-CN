---
title: EnableTextProps 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251697
localization_priority: Normal
ms.assetid: 8c59abaf-d2cc-94c9-08ba-004bc40efd9e
description: 确定样式是否包括文本属性。
ms.openlocfilehash: a51f83624192615e84292129d4788ae1e2779c6a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780175"
---
# <a name="enabletextprops-cell-style-properties-section"></a><span data-ttu-id="36e22-103">EnableTextProps 单元格（“Style Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="36e22-103">EnableTextProps Cell (Style Properties Section)</span></span>

<span data-ttu-id="36e22-104">确定样式是否包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="36e22-104">Determines whether a style includes text properties.</span></span>
  
|<span data-ttu-id="36e22-105">**值**</span><span class="sxs-lookup"><span data-stu-id="36e22-105">**Value**</span></span>|<span data-ttu-id="36e22-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="36e22-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36e22-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="36e22-107">TRUE</span></span>  <br/> |<span data-ttu-id="36e22-108">包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="36e22-108">Include text properties.</span></span>  <br/> |
|<span data-ttu-id="36e22-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="36e22-109">FALSE</span></span>  <br/> |<span data-ttu-id="36e22-110">不包括文本属性。</span><span class="sxs-lookup"><span data-stu-id="36e22-110">Exclude text properties.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="36e22-111">注解</span><span class="sxs-lookup"><span data-stu-id="36e22-111">Remarks</span></span>

<span data-ttu-id="36e22-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EnableTextProps 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="36e22-112">To get a reference to the EnableTextProps cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="36e22-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="36e22-113">Cell name:</span></span>  <br/> |<span data-ttu-id="36e22-114">EnableTextProps</span><span class="sxs-lookup"><span data-stu-id="36e22-114">EnableTextProps</span></span>  <br/> |
   
<span data-ttu-id="36e22-115">要从某个程序按索引获取对 EnableTextProps 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="36e22-115">To get a reference to the EnableTextProps cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="36e22-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="36e22-116">Section index:</span></span>  <br/> |<span data-ttu-id="36e22-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="36e22-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="36e22-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="36e22-118">Row index:</span></span>  <br/> |<span data-ttu-id="36e22-119">**visRowStyle**</span><span class="sxs-lookup"><span data-stu-id="36e22-119">**visRowStyle**</span></span> <br/> |
|<span data-ttu-id="36e22-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="36e22-120">Cell index:</span></span>  <br/> |<span data-ttu-id="36e22-121">**visStyleIncludesText**</span><span class="sxs-lookup"><span data-stu-id="36e22-121">**visStyleIncludesText**</span></span> <br/> |
   

