---
title: ReplaceLockShapeData 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockShapeData 确定主控形状的形状数据是否覆盖正在替换的形状的所有形状数据。
ms.openlocfilehash: d2349da96bde7d141aada9066d56a4379f425fee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348340"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a><span data-ttu-id="e4187-104">ReplaceLockShapeData 单元格 ("更改形状行为" 部分)</span><span class="sxs-lookup"><span data-stu-id="e4187-104">ReplaceLockShapeData Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="e4187-105">指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。</span><span class="sxs-lookup"><span data-stu-id="e4187-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="e4187-106">**ReplaceLockShapeData**确定主控形状的形状数据是否覆盖正在替换的形状的所有形状数据。</span><span class="sxs-lookup"><span data-stu-id="e4187-106">The **ReplaceLockShapeData** determines whether the shape data of the master shape overwrites all of the shape data of the shape being replaced.</span></span> 
  
|<span data-ttu-id="e4187-107">**Value**</span><span class="sxs-lookup"><span data-stu-id="e4187-107">**Value**</span></span>|<span data-ttu-id="e4187-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e4187-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e4187-109">1 (TRUE)</span><span class="sxs-lookup"><span data-stu-id="e4187-109">1 (TRUE)</span></span>  <br/> |<span data-ttu-id="e4187-110">将主控形状的 "**形状数据**" 部分的所有行和值复制到替换形状上, 并丢弃替换旧形状中的任何本地值。</span><span class="sxs-lookup"><span data-stu-id="e4187-110">All rows and values of the **Shape Data** section of the master shape are copied onto the replacement shape and any local values from the old shape being replaced are discarded.</span></span>  <br/> |
|<span data-ttu-id="e4187-111">0 (FALSE)</span><span class="sxs-lookup"><span data-stu-id="e4187-111">0 (FALSE)</span></span>  <br/> |<span data-ttu-id="e4187-112">将主控形状的 "**形状数据**" 部分的行和值复制到替换形状。</span><span class="sxs-lookup"><span data-stu-id="e4187-112">The rows and values of the **Shape Data** section of the master shape are copied to the replacement shape.</span></span> <span data-ttu-id="e4187-113">具有本地值的旧形状的 "**形状数据**" 部分中的任何行都将转换为替代形状。</span><span class="sxs-lookup"><span data-stu-id="e4187-113">Any rows in the **Shape Data** section of the old shape with local values are transferred to the replacement shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4187-114">注解</span><span class="sxs-lookup"><span data-stu-id="e4187-114">Remarks</span></span>

<span data-ttu-id="e4187-115">若要从另一个公式按名称获取对**ReplaceLockShapeData**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="e4187-115">To get a reference to the **ReplaceLockShapeData** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4187-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e4187-116">Cell name:</span></span>  <br/> | <span data-ttu-id="e4187-117">ReplaceLockShapeData</span><span class="sxs-lookup"><span data-stu-id="e4187-117">ReplaceLockShapeData</span></span>  <br/> |
   
<span data-ttu-id="e4187-118">若要从某个程序按索引获取对**ReplaceLockShapeData**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="e4187-118">To get a reference to the **ReplaceLockShapeData** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4187-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e4187-119">Section index:</span></span>  <br/> |<span data-ttu-id="e4187-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e4187-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e4187-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="e4187-121">Row index:</span></span>  <br/> |<span data-ttu-id="e4187-122">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="e4187-122">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="e4187-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e4187-123">Cell index:</span></span>  <br/> |<span data-ttu-id="e4187-124">**visReplaceLockShapeData**</span><span class="sxs-lookup"><span data-stu-id="e4187-124">**visReplaceLockShapeData**</span></span> <br/> |
   

