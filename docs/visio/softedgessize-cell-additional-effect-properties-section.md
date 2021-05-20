---
title: 'SoftEdgesSize Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果的大小，以 0.00 到 100.00 的点表示。 如果 SoftEdgesSize 单元格的值为 0，则形状没有柔化边缘。
ms.openlocfilehash: e749fefde8e0358cbf4ab8388a61ad703c7d52ff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435913"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a><span data-ttu-id="23122-104">SoftEdgesSize Cell (Additional Effect Properties Section) </span><span class="sxs-lookup"><span data-stu-id="23122-104">SoftEdgesSize Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="23122-105">确定柔化边缘效果的大小，以 0.00 到 100.00 的点表示。</span><span class="sxs-lookup"><span data-stu-id="23122-105">Determines the size of a soft edge effect, in points from 0.00 to 100.00.</span></span> <span data-ttu-id="23122-106">如果 **SoftEdgesSize** 单元格的值为 0，则形状没有柔化边缘。</span><span class="sxs-lookup"><span data-stu-id="23122-106">If the **SoftEdgesSize** cell has a value of 0, the shape does not have soft edges.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="23122-107">备注</span><span class="sxs-lookup"><span data-stu-id="23122-107">Remarks</span></span>

<span data-ttu-id="23122-108">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **SoftEdgesSize** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="23122-108">To get a reference to the **SoftEdgesSize** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="23122-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="23122-109">Cell name:</span></span>  <br/> | <span data-ttu-id="23122-110">SoftEdgesSize</span><span class="sxs-lookup"><span data-stu-id="23122-110">SoftEdgesSize</span></span>  <br/> |
   
<span data-ttu-id="23122-111">若要从程序按索引获取对 **SoftEdgesSize** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="23122-111">To get a reference to the **SoftEdgesSize** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="23122-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="23122-112">Section index:</span></span>  <br/> |<span data-ttu-id="23122-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="23122-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="23122-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="23122-114">Row index:</span></span>  <br/> |<span data-ttu-id="23122-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="23122-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="23122-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="23122-116">Cell index:</span></span>  <br/> |<span data-ttu-id="23122-117">**visSoftEdgesSize**</span><span class="sxs-lookup"><span data-stu-id="23122-117">**visSoftEdgesSize**</span></span> <br/> |
   

