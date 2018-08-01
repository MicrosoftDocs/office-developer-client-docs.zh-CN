---
title: FillBkgnd 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm365
localization_priority: Normal
ms.assetid: 603d698f-a025-538c-8767-18e7716a9a5f
description: 确定用于形状的填充图案的背景（填充）颜色。
ms.openlocfilehash: d1222026887313d7737a3a0ded9e798e9bf5ea30
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780240"
---
# <a name="fillbkgnd-cell-fill-format-section"></a><span data-ttu-id="ef148-103">FillBkgnd 单元格（“Fill Format”部分）</span><span class="sxs-lookup"><span data-stu-id="ef148-103">FillBkgnd Cell (Fill Format Section)</span></span>

<span data-ttu-id="ef148-104">确定用于形状的填充图案的背景（填充）颜色。</span><span class="sxs-lookup"><span data-stu-id="ef148-104">Determines the color used for the background (fill) of the shape's fill pattern.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ef148-105">注解</span><span class="sxs-lookup"><span data-stu-id="ef148-105">Remarks</span></span>

<span data-ttu-id="ef148-106">若要设置该颜色，请输入一个介于 0 和 23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="ef148-106">To set the color, enter a number from 0 to 23.</span></span>
  
<span data-ttu-id="ef148-p101">若要输入自定义颜色，请使用 RGB 或 HSL 函数。自定义颜色的值是其 RGB 颜色，因而将在 ShapeSheet 窗口中显示的是 RGB(*r, g, b*)，而不是一个数字。在数值运算中使用自定义颜色时，其值将大于或等于 24。</span><span class="sxs-lookup"><span data-stu-id="ef148-p101">To enter a custom color, use the RGB or HSL function. The value of a custom color is its RGB color, and RGB(*r, g, b*), rather than a number, will be shown in the ShapeSheet window. When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="ef148-110">您可以在 FillBkgndTrans 单元格中设置背景填充的透明度。</span><span class="sxs-lookup"><span data-stu-id="ef148-110">You can set the transparency of the background fill in the FillBkgndTrans cell.</span></span> 
  
<span data-ttu-id="ef148-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FillBkgnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ef148-111">To get a reference to the FillBkgnd cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ef148-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ef148-112">Cell name:</span></span>  <br/> | <span data-ttu-id="ef148-113">FillBkgnd</span><span class="sxs-lookup"><span data-stu-id="ef148-113">FillBkgnd</span></span>  <br/> |
   
<span data-ttu-id="ef148-114">若要从某个程序按索引获取对 FillBkgnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ef148-114">To get a reference to the FillBkgnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="ef148-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ef148-115">Section index:</span></span>  <br/> |<span data-ttu-id="ef148-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ef148-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="ef148-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="ef148-117">Row index:</span></span>  <br/> |<span data-ttu-id="ef148-118">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="ef148-118">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="ef148-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ef148-119">Cell index:</span></span>  <br/> |<span data-ttu-id="ef148-120">**visFillBkgnd**</span><span class="sxs-lookup"><span data-stu-id="ef148-120">**visFillBkgnd**</span></span> <br/> |
   

