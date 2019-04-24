---
title: KeepTextFlat 单元格 ("三维旋转属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3537de44-8d6f-4bd9-bf8c-fa851fc007b9
description: 指示形状的文本是否将忽略三维中形状的旋转。 不应用于二维旋转。
ms.openlocfilehash: fc8cf2fac431645876c7f81ed9864cb6c2036169
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360436"
---
# <a name="keeptextflat-cell-3-d-rotation-properties-section"></a><span data-ttu-id="de827-104">KeepTextFlat 单元格 ("三维旋转属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="de827-104">KeepTextFlat Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="de827-105">指示形状的文本是否将忽略三维中形状的旋转。</span><span class="sxs-lookup"><span data-stu-id="de827-105">Indicates whether a shape's text will ignore the shape's rotation in 3-D.</span></span> <span data-ttu-id="de827-106">不应用于二维旋转。</span><span class="sxs-lookup"><span data-stu-id="de827-106">Does not apply to 2-D rotation.</span></span> 
  
****

|<span data-ttu-id="de827-107">**Value**</span><span class="sxs-lookup"><span data-stu-id="de827-107">**Value**</span></span>|<span data-ttu-id="de827-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="de827-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="de827-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="de827-109">TRUE</span></span>  <br/> |<span data-ttu-id="de827-110">形状文本不随形状的几何图形旋转。</span><span class="sxs-lookup"><span data-stu-id="de827-110">Shape text does not rotate with the shape's geometry.</span></span>  <br/> |
|<span data-ttu-id="de827-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="de827-111">FALSE</span></span>  <br/> |<span data-ttu-id="de827-112">形状文本将转换为旋转形状的几何图形。</span><span class="sxs-lookup"><span data-stu-id="de827-112">Shape text is transformed to rotate with the shape's geometry.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="de827-113">注解</span><span class="sxs-lookup"><span data-stu-id="de827-113">Remarks</span></span>

<span data-ttu-id="de827-114">若要从另一个公式按名称获取对**KeepTextFlat**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="de827-114">To get a reference to the **KeepTextFlat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="de827-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="de827-115">Cell name:</span></span>  <br/> |<span data-ttu-id="de827-116">KeepTextFlat</span><span class="sxs-lookup"><span data-stu-id="de827-116">KeepTextFlat</span></span>  <br/> |
   
<span data-ttu-id="de827-117">若要从某个程序按索引获取对**KeepTextFlat**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="de827-117">To get a reference to the **KeepTextFlat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="de827-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="de827-118">Section index:</span></span>  <br/> |<span data-ttu-id="de827-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="de827-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="de827-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="de827-120">Row index:</span></span>  <br/> |<span data-ttu-id="de827-121">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="de827-121">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="de827-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="de827-122">Cell index:</span></span>  <br/> |<span data-ttu-id="de827-123">**visKeepTextFlat**</span><span class="sxs-lookup"><span data-stu-id="de827-123">**visKeepTextFlat**</span></span> <br/> |
   

