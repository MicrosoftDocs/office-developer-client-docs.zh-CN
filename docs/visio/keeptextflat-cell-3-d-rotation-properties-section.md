---
title: KeepTextFlat 单元格 （三维旋转 Properties 内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3537de44-8d6f-4bd9-bf8c-fa851fc007b9
description: 指示是否将形状的文本将忽略三维形状的旋转角度。 不应用于二维旋转。
ms.openlocfilehash: cf8b964360e602b81a2a7b7ca79961921eeeb8b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780513"
---
# <a name="keeptextflat-cell-3-d-rotation-properties-section"></a><span data-ttu-id="5b6b3-104">KeepTextFlat 单元格 （三维旋转 Properties 内容）</span><span class="sxs-lookup"><span data-stu-id="5b6b3-104">KeepTextFlat Cell (3-D Rotation Properties Section)</span></span>

<span data-ttu-id="5b6b3-105">指示是否将形状的文本将忽略三维形状的旋转角度。</span><span class="sxs-lookup"><span data-stu-id="5b6b3-105">Indicates whether a shape's text will ignore the shape's rotation in 3-D.</span></span> <span data-ttu-id="5b6b3-106">不应用于二维旋转。</span><span class="sxs-lookup"><span data-stu-id="5b6b3-106">Does not apply to 2-D rotation.</span></span> 
  
****

|<span data-ttu-id="5b6b3-107">**值**</span><span class="sxs-lookup"><span data-stu-id="5b6b3-107">**Value**</span></span>|<span data-ttu-id="5b6b3-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b6b3-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b6b3-109">TRUE</span><span class="sxs-lookup"><span data-stu-id="5b6b3-109">TRUE</span></span>  <br/> |<span data-ttu-id="5b6b3-110">与形状的几何形状文本不一起旋转。</span><span class="sxs-lookup"><span data-stu-id="5b6b3-110">Shape text does not rotate with the shape's geometry.</span></span>  <br/> |
|<span data-ttu-id="5b6b3-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="5b6b3-111">FALSE</span></span>  <br/> |<span data-ttu-id="5b6b3-112">形状文本进行转换，以与形状的几何旋转。</span><span class="sxs-lookup"><span data-stu-id="5b6b3-112">Shape text is transformed to rotate with the shape's geometry.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b6b3-113">备注</span><span class="sxs-lookup"><span data-stu-id="5b6b3-113">Remarks</span></span>

<span data-ttu-id="5b6b3-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**KeepTextFlat**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-114">To get a reference to the **KeepTextFlat** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5b6b3-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-115">Cell name:</span></span>  <br/> |<span data-ttu-id="5b6b3-116">KeepTextFlat</span><span class="sxs-lookup"><span data-stu-id="5b6b3-116">KeepTextFlat</span></span>  <br/> |
   
<span data-ttu-id="5b6b3-117">若要从某个程序按索引获取对**KeepTextFlat**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-117">To get a reference to the **KeepTextFlat** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5b6b3-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-118">Section index:</span></span>  <br/> |<span data-ttu-id="5b6b3-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="5b6b3-119">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="5b6b3-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-120">Row index:</span></span>  <br/> |<span data-ttu-id="5b6b3-121">**visRow3DRotationProperties**</span><span class="sxs-lookup"><span data-stu-id="5b6b3-121">**visRow3DRotationProperties**</span></span> <br/> |
|<span data-ttu-id="5b6b3-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5b6b3-122">Cell index:</span></span>  <br/> |<span data-ttu-id="5b6b3-123">**visKeepTextFlat**</span><span class="sxs-lookup"><span data-stu-id="5b6b3-123">**visKeepTextFlat**</span></span> <br/> |
   

