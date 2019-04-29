---
title: TxtPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1040
localization_priority: Normal
ms.assetid: d0c0fe52-6a9e-e40e-394e-83a851db55a4
description: 确定文本块的旋转中心相对于形状原点的 x 轴坐标值。 默认公式为：
ms.openlocfilehash: 836f5c807d0c0e53efc825f62f60429274282165
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423494"
---
# <a name="txtpinx-cell-text-transform-section"></a><span data-ttu-id="dc1fa-104">TxtPinX 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="dc1fa-104">TxtPinX Cell (Text Transform Section)</span></span>

<span data-ttu-id="dc1fa-105">确定文本块的旋转中心相对于形状原点的*x*轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="dc1fa-105">Determines the  *x*  -coordinate of the text block's center of rotation in relation to the origin of the shape.</span></span> <span data-ttu-id="dc1fa-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-106">The default formula is:</span></span> 
  
<span data-ttu-id="dc1fa-107">= 宽度\* 0。5</span><span class="sxs-lookup"><span data-stu-id="dc1fa-107">= Width \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="dc1fa-108">说明</span><span class="sxs-lookup"><span data-stu-id="dc1fa-108">Remarks</span></span>

<span data-ttu-id="dc1fa-109">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtPinX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-109">To get a reference to the TxtPinX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc1fa-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-110">Cell name:</span></span>  <br/> | <span data-ttu-id="dc1fa-111">TxtPinX</span><span class="sxs-lookup"><span data-stu-id="dc1fa-111">TxtPinX</span></span>  <br/> |
   
<span data-ttu-id="dc1fa-112">要从某个程序按索引获取对 TxtPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-112">To get a reference to the TxtPinX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc1fa-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-113">Section index:</span></span>  <br/> |<span data-ttu-id="dc1fa-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="dc1fa-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="dc1fa-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-115">Row index:</span></span>  <br/> |<span data-ttu-id="dc1fa-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="dc1fa-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="dc1fa-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dc1fa-117">Cell index:</span></span>  <br/> |<span data-ttu-id="dc1fa-118">**visXFormPinX**</span><span class="sxs-lookup"><span data-stu-id="dc1fa-118">**visXFormPinX**</span></span> <br/> |
   

