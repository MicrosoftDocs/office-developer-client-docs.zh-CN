---
title: NoQuickDrag 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80004
localization_priority: Normal
ms.assetid: 8491f459-9de2-8e75-5532-7d3bd0986734
description: 确定当用户单击由 "Geometry" 内容定义的填充区域时, 是否可以选择或拖动形状。
ms.openlocfilehash: d60268685d93ae88abb2840f62b093db1e688c2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341060"
---
# <a name="noquickdrag-cell-geometry-section"></a><span data-ttu-id="26840-103">NoQuickDrag 单元格（“Geometry”内容）</span><span class="sxs-lookup"><span data-stu-id="26840-103">NoQuickDrag Cell (Geometry Section)</span></span>

<span data-ttu-id="26840-104">确定当用户单击由 "Geometry" 内容定义的填充区域时, 是否可以选择或拖动形状。</span><span class="sxs-lookup"><span data-stu-id="26840-104">Determines whether a shape can be selected or dragged when the user clicks the filled area defined by the Geometry section.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="26840-105">注解</span><span class="sxs-lookup"><span data-stu-id="26840-105">Remarks</span></span>

<span data-ttu-id="26840-106">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 NoQuickDrag 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="26840-106">To get a reference to the NoQuickDrag cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26840-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="26840-107">Cell name:</span></span>  <br/> |<span data-ttu-id="26840-108">几何图形*i* 。NoQuickDrag, 其中 \* i \*-<1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="26840-108">Geometry  *i*  .NoQuickDrag, where  \* i \*  - <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="26840-109">若要从某个程序按索引获取对 NoQuickDrag 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="26840-109">To get a reference to the NoQuickDrag cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26840-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="26840-110">Section index:</span></span>  <br/> |<span data-ttu-id="26840-111">**visSectionFirstComponent** +  *i* , 其中*i* = 0, 1, 2 .。。</span><span class="sxs-lookup"><span data-stu-id="26840-111">**visSectionFirstComponent** +  *i*  , where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="26840-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="26840-112">Row index:</span></span>  <br/> |<span data-ttu-id="26840-113">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="26840-113">**visRowComponent**</span></span> <br/> |
|<span data-ttu-id="26840-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="26840-114">Cell index:</span></span>  <br/> |<span data-ttu-id="26840-115">**visCompNoQuickDrag**</span><span class="sxs-lookup"><span data-stu-id="26840-115">**visCompNoQuickDrag**</span></span> <br/> |
   

