---
title: SoftEdgesSize 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5cde2ca-f343-4a6e-b5d9-a1b78b3cd240
description: 确定柔化边缘效果的大小, 以磅为单位, 以0.00 到100.00。 如果 SoftEdgesSize 单元格的值为 0, 则该形状没有柔化边缘。
ms.openlocfilehash: e749fefde8e0358cbf4ab8388a61ad703c7d52ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334536"
---
# <a name="softedgessize-cell-additional-effect-properties-section"></a><span data-ttu-id="3713d-104">SoftEdgesSize 单元格 ("其他效果属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="3713d-104">SoftEdgesSize Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="3713d-105">确定柔化边缘效果的大小, 以磅为单位, 以0.00 到100.00。</span><span class="sxs-lookup"><span data-stu-id="3713d-105">Determines the size of a soft edge effect, in points from 0.00 to 100.00.</span></span> <span data-ttu-id="3713d-106">如果**SoftEdgesSize**单元格的值为 0, 则该形状没有柔化边缘。</span><span class="sxs-lookup"><span data-stu-id="3713d-106">If the **SoftEdgesSize** cell has a value of 0, the shape does not have soft edges.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="3713d-107">注解</span><span class="sxs-lookup"><span data-stu-id="3713d-107">Remarks</span></span>

<span data-ttu-id="3713d-108">若要从另一个公式按名称获取对**SoftEdgesSize**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="3713d-108">To get a reference to the **SoftEdgesSize** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3713d-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="3713d-109">Cell name:</span></span>  <br/> | <span data-ttu-id="3713d-110">SoftEdgesSize</span><span class="sxs-lookup"><span data-stu-id="3713d-110">SoftEdgesSize</span></span>  <br/> |
   
<span data-ttu-id="3713d-111">若要从某个程序按索引获取对**SoftEdgesSize**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="3713d-111">To get a reference to the **SoftEdgesSize** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="3713d-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="3713d-112">Section index:</span></span>  <br/> |<span data-ttu-id="3713d-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="3713d-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="3713d-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="3713d-114">Row index:</span></span>  <br/> |<span data-ttu-id="3713d-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="3713d-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="3713d-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="3713d-116">Cell index:</span></span>  <br/> |<span data-ttu-id="3713d-117">**visSoftEdgesSize**</span><span class="sxs-lookup"><span data-stu-id="3713d-117">**visSoftEdgesSize**</span></span> <br/> |
   

