---
title: 'RotateGradientWithShape Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定填充渐变是否随形状在 2D 旋转中作为布尔值旋转。
ms.openlocfilehash: 76a76a4a97128c81710269f75e9e17db90827377
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412217"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a><span data-ttu-id="55e42-103">RotateGradientWithShape Cell (Gradient Properties Section) </span><span class="sxs-lookup"><span data-stu-id="55e42-103">RotateGradientWithShape Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="55e42-104">确定填充渐变是否随形状在 2D 旋转中作为布尔值旋转。</span><span class="sxs-lookup"><span data-stu-id="55e42-104">Determines whether a fill gradient rotates with a shape in 2D rotation, as a boolean.</span></span>
  
|<span data-ttu-id="55e42-105">**值**</span><span class="sxs-lookup"><span data-stu-id="55e42-105">**Value**</span></span>|<span data-ttu-id="55e42-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="55e42-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55e42-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="55e42-107">TRUE</span></span>  <br/> |<span data-ttu-id="55e42-108">当形状围绕旋转中心点旋转时，渐变随形状一起旋转。</span><span class="sxs-lookup"><span data-stu-id="55e42-108">The gradient rotates with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="55e42-109">渐变的"顶部"与旋转手柄平行。</span><span class="sxs-lookup"><span data-stu-id="55e42-109">The "top" of the gradient is parallel to the rotation handle.</span></span>  <br/> |
|<span data-ttu-id="55e42-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="55e42-110">FALSE</span></span>  <br/> |<span data-ttu-id="55e42-111">当形状围绕旋转中心点旋转时，该渐变不会随形状一起旋转。</span><span class="sxs-lookup"><span data-stu-id="55e42-111">The gradient does not rotate with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="55e42-112">渐变的"顶部"与绘图画布平行。</span><span class="sxs-lookup"><span data-stu-id="55e42-112">The "top" of the gradient is parallel to the drawing canvas.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="55e42-113">备注</span><span class="sxs-lookup"><span data-stu-id="55e42-113">Remarks</span></span>

<span data-ttu-id="55e42-114">若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **RotateGradientWithShape** 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="55e42-114">To get a reference to the **RotateGradientWithShape** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55e42-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="55e42-115">Cell name:</span></span>  <br/> | <span data-ttu-id="55e42-116">RotateGradientWithShape</span><span class="sxs-lookup"><span data-stu-id="55e42-116">RotateGradientWithShape</span></span>  <br/> |
   
<span data-ttu-id="55e42-117">若要从程序按索引获取对 **RotateGradientWithShape** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="55e42-117">To get a reference to the **RotateGradientWithShape** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="55e42-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="55e42-118">Section index:</span></span>  <br/> |<span data-ttu-id="55e42-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="55e42-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="55e42-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="55e42-120">Row index:</span></span>  <br/> |<span data-ttu-id="55e42-121">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="55e42-121">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="55e42-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="55e42-122">Cell index:</span></span>  <br/> |<span data-ttu-id="55e42-123">**visRotateGradientWithShape**</span><span class="sxs-lookup"><span data-stu-id="55e42-123">**visRotateGradientWithShape**</span></span> <br/> |
   

