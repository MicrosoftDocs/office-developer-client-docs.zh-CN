---
title: TxtPinY 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1045
localization_priority: Normal
ms.assetid: 88ddf4b5-8248-8c1a-c387-09a607639d26
description: 确定文本块的旋转中心相对于形状原点的 y 轴坐标值。 默认公式为：
ms.openlocfilehash: fc62ac76aa24a698d956690df6e5d1e7cff3fb5f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316420"
---
# <a name="txtpiny-cell-text-transform-section"></a><span data-ttu-id="e4e3e-104">TxtPinY 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="e4e3e-104">TxtPinY Cell (Text Transform Section)</span></span>

<span data-ttu-id="e4e3e-105">确定文本块的旋转中心相对于形状原点的*y*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="e4e3e-105">Determines the  *y*  -coordinate of the text block's center of rotation in relation to the origin of the shape.</span></span> <span data-ttu-id="e4e3e-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-106">The default formula is:</span></span> 
  
<span data-ttu-id="e4e3e-107">= 高度\* 0。5</span><span class="sxs-lookup"><span data-stu-id="e4e3e-107">= Height \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e4e3e-108">注解</span><span class="sxs-lookup"><span data-stu-id="e4e3e-108">Remarks</span></span>

<span data-ttu-id="e4e3e-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtPinY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-109">To get a reference to the TxtPinY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4e3e-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-110">Cell name:</span></span>  <br/> | <span data-ttu-id="e4e3e-111">TxtPinY</span><span class="sxs-lookup"><span data-stu-id="e4e3e-111">TxtPinY</span></span>  <br/> |
   
<span data-ttu-id="e4e3e-112">要从某个程序按索引获取对 TxtPinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-112">To get a reference to the TxtPinY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e4e3e-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-113">Section index:</span></span>  <br/> |<span data-ttu-id="e4e3e-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="e4e3e-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="e4e3e-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-115">Row index:</span></span>  <br/> |<span data-ttu-id="e4e3e-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="e4e3e-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="e4e3e-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e4e3e-117">Cell index:</span></span>  <br/> |<span data-ttu-id="e4e3e-118">**visXFormPinY**</span><span class="sxs-lookup"><span data-stu-id="e4e3e-118">**visXFormPinY**</span></span> <br/> |
   

