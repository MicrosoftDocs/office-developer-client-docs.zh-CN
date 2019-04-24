---
title: RotateGradientWithShape 单元格 ("渐变属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定是否以布尔值的形式在2d 旋转中将填充渐变旋转。
ms.openlocfilehash: 76a76a4a97128c81710269f75e9e17db90827377
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315657"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a><span data-ttu-id="f2405-103">RotateGradientWithShape 单元格 ("渐变属性" 部分)</span><span class="sxs-lookup"><span data-stu-id="f2405-103">RotateGradientWithShape Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="f2405-104">确定是否以布尔值的形式在2d 旋转中将填充渐变旋转。</span><span class="sxs-lookup"><span data-stu-id="f2405-104">Determines whether a fill gradient rotates with a shape in 2D rotation, as a boolean.</span></span>
  
|<span data-ttu-id="f2405-105">**Value**</span><span class="sxs-lookup"><span data-stu-id="f2405-105">**Value**</span></span>|<span data-ttu-id="f2405-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="f2405-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2405-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="f2405-107">TRUE</span></span>  <br/> |<span data-ttu-id="f2405-108">当形状围绕旋转针旋转时, 渐变将随形状旋转。</span><span class="sxs-lookup"><span data-stu-id="f2405-108">The gradient rotates with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="f2405-109">渐变的 "顶部" 平行于旋转控点。</span><span class="sxs-lookup"><span data-stu-id="f2405-109">The "top" of the gradient is parallel to the rotation handle.</span></span>  <br/> |
|<span data-ttu-id="f2405-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="f2405-110">FALSE</span></span>  <br/> |<span data-ttu-id="f2405-111">当形状围绕旋转针旋转时, 渐变不随形状旋转。</span><span class="sxs-lookup"><span data-stu-id="f2405-111">The gradient does not rotate with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="f2405-112">渐变的 "顶部" 平行于绘图画布。</span><span class="sxs-lookup"><span data-stu-id="f2405-112">The "top" of the gradient is parallel to the drawing canvas.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f2405-113">注解</span><span class="sxs-lookup"><span data-stu-id="f2405-113">Remarks</span></span>

<span data-ttu-id="f2405-114">若要从另一个公式按名称获取对**RotateGradientWithShape**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="f2405-114">To get a reference to the **RotateGradientWithShape** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f2405-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f2405-115">Cell name:</span></span>  <br/> | <span data-ttu-id="f2405-116">RotateGradientWithShape</span><span class="sxs-lookup"><span data-stu-id="f2405-116">RotateGradientWithShape</span></span>  <br/> |
   
<span data-ttu-id="f2405-117">若要从某个程序按索引获取对**RotateGradientWithShape**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="f2405-117">To get a reference to the **RotateGradientWithShape** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f2405-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f2405-118">Section index:</span></span>  <br/> |<span data-ttu-id="f2405-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="f2405-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="f2405-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="f2405-120">Row index:</span></span>  <br/> |<span data-ttu-id="f2405-121">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="f2405-121">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="f2405-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f2405-122">Cell index:</span></span>  <br/> |<span data-ttu-id="f2405-123">**visRotateGradientWithShape**</span><span class="sxs-lookup"><span data-stu-id="f2405-123">**visRotateGradientWithShape**</span></span> <br/> |
   

