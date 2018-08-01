---
title: ReplaceLockShapeData 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 ReplaceLockShapeData 确定是否主控形状的形状数据将覆盖所有要替换的形状的形状数据。
ms.openlocfilehash: 07547140c7c96e49663270e51a90fd559afedf29
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781093"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a><span data-ttu-id="4145c-104">ReplaceLockShapeData 单元格（“Change Shape Behavior”部分）</span><span class="sxs-lookup"><span data-stu-id="4145c-104">ReplaceLockShapeData Cell (Change Shape Behavior Section)</span></span>

<span data-ttu-id="4145c-105">指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。</span><span class="sxs-lookup"><span data-stu-id="4145c-105">Indicates whether the values of specified cells in a master shape overwrite the values (including local values) of a shape being replaced during a shape replacement operation.</span></span> <span data-ttu-id="4145c-106">**ReplaceLockShapeData**确定是否主控形状的形状数据将覆盖所有要替换的形状的形状数据。</span><span class="sxs-lookup"><span data-stu-id="4145c-106">The **ReplaceLockShapeData** determines whether the shape data of the master shape overwrites all of the shape data of the shape being replaced.</span></span> 
  
|<span data-ttu-id="4145c-107">**值**</span><span class="sxs-lookup"><span data-stu-id="4145c-107">**Value**</span></span>|<span data-ttu-id="4145c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="4145c-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4145c-109">1 (TRUE)</span><span class="sxs-lookup"><span data-stu-id="4145c-109">1 (TRUE)</span></span>  <br/> |<span data-ttu-id="4145c-110">所有的行和主控形状的**形状数据**部分的值复制到的替换形状，要替换的旧形状中的所有本地值将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="4145c-110">All rows and values of the **Shape Data** section of the master shape are copied onto the replacement shape and any local values from the old shape being replaced are discarded.</span></span>  <br/> |
|<span data-ttu-id="4145c-111">0 (FALSE)</span><span class="sxs-lookup"><span data-stu-id="4145c-111">0 (FALSE)</span></span>  <br/> |<span data-ttu-id="4145c-112">行和值**形状数据**部分中的主控形状复制到的替换形状。</span><span class="sxs-lookup"><span data-stu-id="4145c-112">The rows and values of the **Shape Data** section of the master shape are copied to the replacement shape.</span></span> <span data-ttu-id="4145c-113">**形状数据**部分中的旧形状本地值与任何行被转接到的替换形状。</span><span class="sxs-lookup"><span data-stu-id="4145c-113">Any rows in the **Shape Data** section of the old shape with local values are transferred to the replacement shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4145c-114">说明</span><span class="sxs-lookup"><span data-stu-id="4145c-114">Remarks</span></span>

<span data-ttu-id="4145c-115">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockShapeData**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4145c-115">To get a reference to the **ReplaceLockShapeData** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4145c-116">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4145c-116">Cell name:</span></span>  <br/> | <span data-ttu-id="4145c-117">ReplaceLockShapeData</span><span class="sxs-lookup"><span data-stu-id="4145c-117">ReplaceLockShapeData</span></span>  <br/> |
   
<span data-ttu-id="4145c-118">若要从某个程序按索引获取对**ReplaceLockShapeData**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4145c-118">To get a reference to the **ReplaceLockShapeData** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4145c-119">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4145c-119">Section index:</span></span>  <br/> |<span data-ttu-id="4145c-120">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4145c-120">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4145c-121">行索引：</span><span class="sxs-lookup"><span data-stu-id="4145c-121">Row index:</span></span>  <br/> |<span data-ttu-id="4145c-122">**visRowReplaceBehaviors**</span><span class="sxs-lookup"><span data-stu-id="4145c-122">**visRowReplaceBehaviors**</span></span> <br/> |
| <span data-ttu-id="4145c-123">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4145c-123">Cell index:</span></span>  <br/> |<span data-ttu-id="4145c-124">**visReplaceLockShapeData**</span><span class="sxs-lookup"><span data-stu-id="4145c-124">**visReplaceLockShapeData**</span></span> <br/> |
   

