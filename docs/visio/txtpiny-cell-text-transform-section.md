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
description: 确定 y-文本块的相对于原点形状的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: e8101463413b177bf8ddd80ed52964d3eeae788f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781576"
---
# <a name="txtpiny-cell-text-transform-section"></a><span data-ttu-id="7baee-104">TxtPinY 单元格（“Text Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="7baee-104">TxtPinY Cell (Text Transform Section)</span></span>

<span data-ttu-id="7baee-105">确定*y* -文本块的相对于原点形状的旋转中心的坐标。</span><span class="sxs-lookup"><span data-stu-id="7baee-105">Determines the  *y*  -coordinate of the text block's center of rotation in relation to the origin of the shape.</span></span> <span data-ttu-id="7baee-106">默认公式为：</span><span class="sxs-lookup"><span data-stu-id="7baee-106">The default formula is:</span></span> 
  
<span data-ttu-id="7baee-107">= 高度\*0.5</span><span class="sxs-lookup"><span data-stu-id="7baee-107">= Height \* 0.5</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7baee-108">备注</span><span class="sxs-lookup"><span data-stu-id="7baee-108">Remarks</span></span>

<span data-ttu-id="7baee-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtPinY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7baee-109">To get a reference to the TxtPinY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7baee-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7baee-110">Cell name:</span></span>  <br/> | <span data-ttu-id="7baee-111">TxtPinY</span><span class="sxs-lookup"><span data-stu-id="7baee-111">TxtPinY</span></span>  <br/> |
   
<span data-ttu-id="7baee-112">若要从某个程序按索引获取对 TxtPinY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="7baee-112">To get a reference to the TxtPinY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7baee-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7baee-113">Section index:</span></span>  <br/> |<span data-ttu-id="7baee-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7baee-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="7baee-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="7baee-115">Row index:</span></span>  <br/> |<span data-ttu-id="7baee-116">**visRowTextXForm**</span><span class="sxs-lookup"><span data-stu-id="7baee-116">**visRowTextXForm**</span></span> <br/> |
| <span data-ttu-id="7baee-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7baee-117">Cell index:</span></span>  <br/> |<span data-ttu-id="7baee-118">**visXFormPinY**</span><span class="sxs-lookup"><span data-stu-id="7baee-118">**visXFormPinY**</span></span> <br/> |
   

