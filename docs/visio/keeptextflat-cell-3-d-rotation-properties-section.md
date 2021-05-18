---
title: 'KeepTextFlat Cell (3-D Rotation Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3537de44-8d6f-4bd9-bf8c-fa851fc007b9
description: 指示形状的文本是否忽略该形状在三维中的旋转。 不适用于二维旋转。
ms.openlocfilehash: fc8cf2fac431645876c7f81ed9864cb6c2036169
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422038"
---
# <a name="keeptextflat-cell-3-d-rotation-properties-section"></a><span data-ttu-id="ae263-104">KeepTextFlat Cell (3-D Rotation Properties Section) </span><span class="sxs-lookup"><span data-stu-id="ae263-104">KeepTextFlat Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="ae263-105">指示形状的文本是否忽略该形状在三维中的旋转。</span><span class="sxs-lookup"><span data-stu-id="ae263-105">Indicates whether a shape's text will ignore the shape's rotation in 3-D.</span></span> <span data-ttu-id="ae263-106">不适用于二维旋转。</span><span class="sxs-lookup"><span data-stu-id="ae263-106">Does not apply to 2-D rotation.</span></span> 
  
****

|<span data-ttu-id="ae263-107">**值**</span><span class="sxs-lookup"><span data-stu-id="ae263-107">**Value**</span></span>|<span data-ttu-id="ae263-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae263-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae263-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="ae263-109">TRUE</span></span>  <br/> |<span data-ttu-id="ae263-110">形状文本不随形状的几何图形一起旋转。</span><span class="sxs-lookup"><span data-stu-id="ae263-110">Shape text does not rotate with the shape's geometry.</span></span>  <br/> |
|<span data-ttu-id="ae263-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="ae263-111">FALSE</span></span>  <br/> |<span data-ttu-id="ae263-112">形状文本会进行转换，以与形状的几何图形一起旋转。</span><span class="sxs-lookup"><span data-stu-id="ae263-112">Shape text is transformed to rotate with the shape's geometry.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ae263-113">备注</span><span class="sxs-lookup"><span data-stu-id="ae263-113">Remarks</span></span>

<span data-ttu-id="ae263-114">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **KeepTextFlat** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ae263-114">To get a reference to the **KeepTextFlat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ae263-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ae263-115">Cell name:</span></span>  <br/> |<span data-ttu-id="ae263-116">KeepTextFlat</span><span class="sxs-lookup"><span data-stu-id="ae263-116">KeepTextFlat</span></span>  <br/> |
   
<span data-ttu-id="ae263-117">若要从程序按索引获取对 **KeepTextFlat** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ae263-117">To get a reference to the **KeepTextFlat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ae263-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ae263-118">Section index:</span></span>  <br/> |<span data-ttu-id="ae263-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ae263-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ae263-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="ae263-120">Row index:</span></span>  <br/> |<span data-ttu-id="ae263-121">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="ae263-121">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="ae263-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ae263-122">Cell index:</span></span>  <br/> |<span data-ttu-id="ae263-123">**visKeepTextFlat**</span><span class="sxs-lookup"><span data-stu-id="ae263-123">**visKeepTextFlat**</span></span> <br/> |
   

