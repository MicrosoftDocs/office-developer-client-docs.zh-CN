---
title: RotateGradientWithShape 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定是否填充渐变旋转 2D 旋转，作为一个布尔值中的形状。
ms.openlocfilehash: d752f870fd08c1a47dfc7ce193b6976a1bdb2a1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781111"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a><span data-ttu-id="2863f-103">RotateGradientWithShape 单元格（“Gradient Properties”部分）</span><span class="sxs-lookup"><span data-stu-id="2863f-103">RotateGradientWithShape Cell (Gradient Properties Section)</span></span>

<span data-ttu-id="2863f-104">确定是否填充渐变旋转 2D 旋转，作为一个布尔值中的形状。</span><span class="sxs-lookup"><span data-stu-id="2863f-104">Determines whether a fill gradient rotates with a shape in 2D rotation, as a boolean.</span></span>
  
|<span data-ttu-id="2863f-105">**值**</span><span class="sxs-lookup"><span data-stu-id="2863f-105">**Value**</span></span>|<span data-ttu-id="2863f-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="2863f-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2863f-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="2863f-107">TRUE</span></span>  <br/> |<span data-ttu-id="2863f-108">围绕旋转 pin 旋转该形状时，与形状旋转渐变。</span><span class="sxs-lookup"><span data-stu-id="2863f-108">The gradient rotates with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="2863f-109">平行旋转手柄"顶部"的渐变。</span><span class="sxs-lookup"><span data-stu-id="2863f-109">The "top" of the gradient is parallel to the rotation handle.</span></span>  <br/> |
|<span data-ttu-id="2863f-110">FALSE</span><span class="sxs-lookup"><span data-stu-id="2863f-110">FALSE</span></span>  <br/> |<span data-ttu-id="2863f-111">围绕旋转 pin 旋转该形状时将渐变不与形状旋转。</span><span class="sxs-lookup"><span data-stu-id="2863f-111">The gradient does not rotate with the shape when the shape is rotated around the rotation pin.</span></span> <span data-ttu-id="2863f-112">平行于绘图画布"顶部"的渐变。</span><span class="sxs-lookup"><span data-stu-id="2863f-112">The "top" of the gradient is parallel to the drawing canvas.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2863f-113">说明</span><span class="sxs-lookup"><span data-stu-id="2863f-113">Remarks</span></span>

<span data-ttu-id="2863f-114">要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**RotateGradientWithShape**单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2863f-114">To get a reference to the **RotateGradientWithShape** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2863f-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2863f-115">Cell name:</span></span>  <br/> | <span data-ttu-id="2863f-116">RotateGradientWithShape</span><span class="sxs-lookup"><span data-stu-id="2863f-116">RotateGradientWithShape</span></span>  <br/> |
   
<span data-ttu-id="2863f-117">若要从某个程序按索引获取对**RotateGradientWithShape**单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="2863f-117">To get a reference to the **RotateGradientWithShape** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2863f-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2863f-118">Section index:</span></span>  <br/> |<span data-ttu-id="2863f-119">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2863f-119">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="2863f-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="2863f-120">Row index:</span></span>  <br/> |<span data-ttu-id="2863f-121">**visRowGradientProperties**</span><span class="sxs-lookup"><span data-stu-id="2863f-121">**visRowGradientProperties**</span></span> <br/> |
| <span data-ttu-id="2863f-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2863f-122">Cell index:</span></span>  <br/> |<span data-ttu-id="2863f-123">**visRotateGradientWithShape**</span><span class="sxs-lookup"><span data-stu-id="2863f-123">**visRotateGradientWithShape**</span></span> <br/> |
   

