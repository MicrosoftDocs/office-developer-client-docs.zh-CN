---
title: LocPinX 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm680
localization_priority: Normal
ms.assetid: b82feade-5793-8a6e-3ff4-69a4cbdd2cf9
description: 代表 x 的形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。 用于确定 LocPinX 默认公式为：
ms.openlocfilehash: 17f7b0fde9a54f6596f2f87f866d30b908e062b5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780671"
---
# <a name="locpinx-cell-shape-transform-section"></a><span data-ttu-id="4c4f1-104">LocPinX 单元格（“Shape Transform”部分）</span><span class="sxs-lookup"><span data-stu-id="4c4f1-104">LocPinX Cell (Shape Transform Section)</span></span>

<span data-ttu-id="4c4f1-105">代表*x*的形状的旋转中心点 （旋转中心） 相对于形状的原点坐标。</span><span class="sxs-lookup"><span data-stu-id="4c4f1-105">Represents the  *x*  -coordinate of the shape's pin (center of rotation) in relation to the origin of the shape.</span></span> <span data-ttu-id="4c4f1-106">用于确定 LocPinX 默认公式为：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-106">The default formula for determining LocPinX is:</span></span> 
  
<span data-ttu-id="4c4f1-107">= 宽度\*0.5</span><span class="sxs-lookup"><span data-stu-id="4c4f1-107">= Width \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c4f1-108">说明</span><span class="sxs-lookup"><span data-stu-id="4c4f1-108">Remarks</span></span>

<span data-ttu-id="4c4f1-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocPinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-109">To get a reference to the LocPinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c4f1-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-110">Cell name:</span></span>  <br/> | <span data-ttu-id="4c4f1-111">LocPinX</span><span class="sxs-lookup"><span data-stu-id="4c4f1-111">LocPinX</span></span>  <br/> |
   
<span data-ttu-id="4c4f1-112">要从某个程序按索引获取对 LocPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-112">To get a reference to the LocPinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="4c4f1-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-113">Section index:</span></span>  <br/> |<span data-ttu-id="4c4f1-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4c4f1-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="4c4f1-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-115">Row index:</span></span>  <br/> |<span data-ttu-id="4c4f1-116">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="4c4f1-116">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="4c4f1-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4c4f1-117">Cell index:</span></span>  <br/> |<span data-ttu-id="4c4f1-118">**visXFormLocPinX**</span><span class="sxs-lookup"><span data-stu-id="4c4f1-118">**visXFormLocPinX**</span></span> <br/> |
   

