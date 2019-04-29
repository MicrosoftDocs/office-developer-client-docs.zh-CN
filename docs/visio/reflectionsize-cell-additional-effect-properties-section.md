---
title: ReflectionSize 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dfeb78e-a0fa-4492-b35f-70b1e2975d38
description: 确定相对于形状的反射的大小, 以0.0 到 100.0% 的百分比。 ReflectionSize 单元格中值为 0% 的形状没有反射;100% 的值显示形状的完整镜像。
ms.openlocfilehash: 60fcb315ec1b6187082bdcdbbdcfaa4b80bbcfb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409074"
---
# <a name="reflectionsize-cell-additional-effect-properties-section"></a><span data-ttu-id="15e47-104">ReflectionSize 单元格 ("其他效果属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="15e47-104">ReflectionSize Cell (Additional Effect Properties Section)</span></span>

<span data-ttu-id="15e47-105">确定相对于形状的反射的大小, 以0.0 到 100.0% 的百分比。</span><span class="sxs-lookup"><span data-stu-id="15e47-105">Determines the size of the reflection relative to the shape, as a percentage from 0.0 to 100.0%.</span></span> <span data-ttu-id="15e47-106">**ReflectionSize**单元格中值为 0% 的形状没有反射;100% 的值显示形状的完整镜像。</span><span class="sxs-lookup"><span data-stu-id="15e47-106">A shape with a value of 0% in the **ReflectionSize** cell does not have a reflection; a value of 100% displays a complete mirror image of the shape.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="15e47-107">说明</span><span class="sxs-lookup"><span data-stu-id="15e47-107">Remarks</span></span>

<span data-ttu-id="15e47-108">若要从另一个公式按名称获取对**ReflectionSize**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="15e47-108">To get a reference to the **ReflectionSize** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="15e47-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="15e47-109">Cell name:</span></span>  <br/> | <span data-ttu-id="15e47-110">ReflectionSize</span><span class="sxs-lookup"><span data-stu-id="15e47-110">ReflectionSize</span></span>  <br/> |
   
<span data-ttu-id="15e47-111">若要从某个程序按索引获取对**ReflectionSize**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="15e47-111">To get a reference to the **ReflectionSize** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="15e47-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="15e47-112">Section index:</span></span>  <br/> |<span data-ttu-id="15e47-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="15e47-113">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="15e47-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="15e47-114">Row index:</span></span>  <br/> |<span data-ttu-id="15e47-115">**visRowOtherEffectProperties**</span><span class="sxs-lookup"><span data-stu-id="15e47-115">**visRowOtherEffectProperties**</span></span> <br/> |
| <span data-ttu-id="15e47-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="15e47-116">Cell index:</span></span>  <br/> |<span data-ttu-id="15e47-117">**visReflectionSize**</span><span class="sxs-lookup"><span data-stu-id="15e47-117">**visReflectionSize**</span></span> <br/> |
   

