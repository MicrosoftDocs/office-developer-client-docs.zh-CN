---
title: 'ReplaceLockShapeData Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 ReplaceLockShapeData 确定主形状的形状数据是否覆盖要替换的形状的所有形状数据。
ms.openlocfilehash: d2349da96bde7d141aada9066d56a4379f425fee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408871"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a><span data-ttu-id="568be-104">ReplaceLockShapeData Cell (Change Shape Behavior Section) </span><span class="sxs-lookup"><span data-stu-id="568be-104">ReplaceLockShapeData Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="568be-105">指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。</span><span class="sxs-lookup"><span data-stu-id="568be-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="568be-106">**ReplaceLockShapeData** 确定主形状的形状数据是否覆盖要替换的形状的所有形状数据。</span><span class="sxs-lookup"><span data-stu-id="568be-106">The **ReplaceLockShapeData** determines whether the shape data of the master shape overwrites all of the shape data of the shape being replaced.</span></span> 
  
|<span data-ttu-id="568be-107">**值**</span><span class="sxs-lookup"><span data-stu-id="568be-107">**Value**</span></span>|<span data-ttu-id="568be-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="568be-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="568be-109">1 (TRUE) </span><span class="sxs-lookup"><span data-stu-id="568be-109">1 (TRUE)</span></span>  <br/> |<span data-ttu-id="568be-110">主控形状的 **"形状数据** "部分的所有行和值都复制到替换形状中，并丢弃被替换的旧形状的任何本地值。</span><span class="sxs-lookup"><span data-stu-id="568be-110">All rows and values of the **Shape Data** section of the master shape are copied onto the replacement shape and any local values from the old shape being replaced are discarded.</span></span>  <br/> |
|<span data-ttu-id="568be-111">0 (FALSE) </span><span class="sxs-lookup"><span data-stu-id="568be-111">0 (FALSE)</span></span>  <br/> |<span data-ttu-id="568be-112">主控形状的 **"形状数据** "内容中的行和值将复制到替换形状。</span><span class="sxs-lookup"><span data-stu-id="568be-112">The rows and values of the **Shape Data** section of the master shape are copied to the replacement shape.</span></span> <span data-ttu-id="568be-113">具有本地值的旧 **形状** 的"形状数据"部分的任何行都将被转移到替换形状。</span><span class="sxs-lookup"><span data-stu-id="568be-113">Any rows in the **Shape Data** section of the old shape with local values are transferred to the replacement shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="568be-114">备注</span><span class="sxs-lookup"><span data-stu-id="568be-114">Remarks</span></span>

<span data-ttu-id="568be-115">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceLockShapeData** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="568be-115">To get a reference to the **ReplaceLockShapeData** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="568be-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="568be-116">Cell name:</span></span>  <br/> | <span data-ttu-id="568be-117">ReplaceLockShapeData</span><span class="sxs-lookup"><span data-stu-id="568be-117">ReplaceLockShapeData</span></span>  <br/> |
   
<span data-ttu-id="568be-118">若要从程序按索引获取对 **ReplaceLockShapeData** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="568be-118">To get a reference to the **ReplaceLockShapeData** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="568be-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="568be-119">Section index:</span></span>  <br/> |<span data-ttu-id="568be-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="568be-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="568be-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="568be-121">Row index:</span></span>  <br/> |<span data-ttu-id="568be-122">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="568be-122">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="568be-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="568be-123">Cell index:</span></span>  <br/> |<span data-ttu-id="568be-124">**visReplaceLockShapeData**</span><span class="sxs-lookup"><span data-stu-id="568be-124">**visReplaceLockShapeData**</span></span> <br/> |
   

