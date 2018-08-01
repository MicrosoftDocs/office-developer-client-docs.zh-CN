---
title: NoLine 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm715
localization_priority: Normal
ms.assetid: f9624af2-c087-3dde-9140-339c438b3652
description: 确定是否围绕路径的边界来绘制线条。
ms.openlocfilehash: 1e43072363461e6b8fcd511c70512f3bfef4504f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780787"
---
# <a name="noline-cell-geometry-section"></a><span data-ttu-id="5cea3-103">NoLine 单元格（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="5cea3-103">NoLine Cell (Geometry Section)</span></span>

<span data-ttu-id="5cea3-104">确定是否围绕路径的边界来绘制线条。</span><span class="sxs-lookup"><span data-stu-id="5cea3-104">Determines whether a line is drawn around the boundary of the path.</span></span>
  
|<span data-ttu-id="5cea3-105">**值**</span><span class="sxs-lookup"><span data-stu-id="5cea3-105">**Value**</span></span>|<span data-ttu-id="5cea3-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="5cea3-106">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5cea3-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="5cea3-107">TRUE</span></span>  <br/> | <span data-ttu-id="5cea3-108">不围绕路径的边界绘制线条，该路径是填充区域的边界。</span><span class="sxs-lookup"><span data-stu-id="5cea3-108">A line is not drawn around the boundary of the path that is the boundary of a filled region.</span></span>  <br/> |
| <span data-ttu-id="5cea3-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="5cea3-109">FALSE</span></span>  <br/> | <span data-ttu-id="5cea3-110">围绕路径的边界绘制线条。</span><span class="sxs-lookup"><span data-stu-id="5cea3-110">A line is drawn around the boundary of a path.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5cea3-111">注释</span><span class="sxs-lookup"><span data-stu-id="5cea3-111">Remarks</span></span>

<span data-ttu-id="5cea3-p101">在您将线条的颜色改为白色后，尽管在白色的背景下看不到它，但该线条仍然是存在的。如果将此单元格的值设置为 TRUE，则不绘制任何线条。</span><span class="sxs-lookup"><span data-stu-id="5cea3-p101">When you change the color of a line to white, the line still exists even though you can't see it on a white background. When you set the value of this cell to TRUE, no line is drawn.</span></span>
  
<span data-ttu-id="5cea3-114">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoLine 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5cea3-114">To get a reference to the NoLine cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5cea3-115">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5cea3-115">Cell name:</span></span>  <br/> | <span data-ttu-id="5cea3-116">Geometry *i* 。NoLine 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="5cea3-116">Geometry  *i*  .NoLine            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="5cea3-117">要从某个程序按索引获取对 NoLine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="5cea3-117">To get a reference to the NoLine cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5cea3-118">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5cea3-118">Section index:</span></span>  <br/> |<span data-ttu-id="5cea3-119">**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="5cea3-119">**visSectionFirstComponent** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5cea3-120">行索引：</span><span class="sxs-lookup"><span data-stu-id="5cea3-120">Row index:</span></span>  <br/> |<span data-ttu-id="5cea3-121">**visRowComponent**</span><span class="sxs-lookup"><span data-stu-id="5cea3-121">**visRowComponent**</span></span> <br/> |
| <span data-ttu-id="5cea3-122">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5cea3-122">Cell index:</span></span>  <br/> |<span data-ttu-id="5cea3-123">**visCompNoLine**</span><span class="sxs-lookup"><span data-stu-id="5cea3-123">**visCompNoLine**</span></span> <br/> |
   

