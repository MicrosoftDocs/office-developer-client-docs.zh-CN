---
title: LocPinY 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm685
localization_priority: Normal
ms.assetid: a29c5d4e-d3d6-d984-495a-4b0b130352ef
description: 表示形状的旋转中心点 (旋转中心) 相对于形状原点的 y 轴坐标值。 确定 LocPinY 的默认公式为：
ms.openlocfilehash: e65bfec8fdcf2be1ee92c23b7afcb183c95ea9fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358042"
---
# <a name="locpiny-cell-shape-transform-section"></a><span data-ttu-id="ec71b-104">LocPinY 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="ec71b-104">LocPinY Cell (Shape Transform Section)</span></span>

<span data-ttu-id="ec71b-105">表示形状的旋转中心点 (旋转中心) 相对于形状原点的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="ec71b-105">Represents the  *y*  -coordinate of the shape's pin (center of rotation) in relation to the origin of the shape.</span></span> <span data-ttu-id="ec71b-106">确定 LocPinY 的默认公式为：</span><span class="sxs-lookup"><span data-stu-id="ec71b-106">The default formula for determining LocPinY is:</span></span> 
  
<span data-ttu-id="ec71b-107">= 高度\* 0。5</span><span class="sxs-lookup"><span data-stu-id="ec71b-107">= Height \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec71b-108">注解</span><span class="sxs-lookup"><span data-stu-id="ec71b-108">Remarks</span></span>

<span data-ttu-id="ec71b-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocPinY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ec71b-109">To get a reference to the LocPinY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec71b-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ec71b-110">Cell name:</span></span>  <br/> | <span data-ttu-id="ec71b-111">LocPinY</span><span class="sxs-lookup"><span data-stu-id="ec71b-111">LocPinY</span></span>  <br/> |
   
<span data-ttu-id="ec71b-112">要从某个程序按索引获取对 LocPinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ec71b-112">To get a reference to the LocPinY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ec71b-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ec71b-113">Section index:</span></span>  <br/> |<span data-ttu-id="ec71b-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ec71b-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ec71b-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="ec71b-115">Row index:</span></span>  <br/> |<span data-ttu-id="ec71b-116">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="ec71b-116">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="ec71b-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ec71b-117">Cell index:</span></span>  <br/> |<span data-ttu-id="ec71b-118">**visXFormLocPinY**</span><span class="sxs-lookup"><span data-stu-id="ec71b-118">**visXFormLocPinY**</span></span> <br/> |
   

