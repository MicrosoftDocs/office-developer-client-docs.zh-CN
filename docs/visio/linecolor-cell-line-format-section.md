---
title: LineColor 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm535
localization_priority: Normal
ms.assetid: d857b48b-9a3d-a1e1-5ad2-6816a492c8ab
description: 确定形状的线条颜色。
ms.openlocfilehash: d0b4ebee6d96bc67c9ca45e8a6194cb91ed6c7f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416935"
---
# <a name="linecolor-cell-line-format-section"></a><span data-ttu-id="9844a-103">LineColor 单元格（“Line Format”内容）</span><span class="sxs-lookup"><span data-stu-id="9844a-103">LineColor Cell (Line Format Section)</span></span>

<span data-ttu-id="9844a-104">确定形状的线条颜色。</span><span class="sxs-lookup"><span data-stu-id="9844a-104">Determines the line color of the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9844a-105">说明</span><span class="sxs-lookup"><span data-stu-id="9844a-105">Remarks</span></span>

<span data-ttu-id="9844a-p101">若要设置线条颜色，请输入一个介于 0 和 23 之间的数字，该数字是线条颜色集合中的索引。可以在 **“线条”** 对话框中查看线条颜色集合（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“粗细”**，然后单击 **“其他线条”**）。还可以在 **“线条”** 对话框中设置 LineColor 的值。</span><span class="sxs-lookup"><span data-stu-id="9844a-p101">To set the line color, enter a number from 0 to 23, which is an index into a collection of line colors. You can view the line color collection in the **Line** dialog box (on the **Home** tab, in the **Shape** group, click **Line**, point to **Weight**, and then click **More Lines**). You can also set the value of LineColor in the **Line** dialog box.</span></span> 
  
<span data-ttu-id="9844a-109">若要输入自定义颜色，请使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="9844a-109">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="9844a-110">自定义颜色的值是其 RGB 颜色, 而 rgb ( *r, g, b*), 而不是数字, 将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="9844a-110">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="9844a-111">在数值运算中使用自定义颜色时，其值将大于或等于 24。</span><span class="sxs-lookup"><span data-stu-id="9844a-111">When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="9844a-112">您可以在 LineColorTrans 单元格中设置线条颜色的透明度。</span><span class="sxs-lookup"><span data-stu-id="9844a-112">You can set the transparency of the line color in the LineColorTrans cell.</span></span>
  
<span data-ttu-id="9844a-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineColor 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9844a-113">To get a reference to the LineColor cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9844a-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9844a-114">Cell name:</span></span>  <br/> |<span data-ttu-id="9844a-115">LineColor</span><span class="sxs-lookup"><span data-stu-id="9844a-115">LineColor</span></span>  <br/> |
   
<span data-ttu-id="9844a-116">若要从某个程序按索引获取对 LineColor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9844a-116">To get a reference to the LineColor cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9844a-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9844a-117">Section index:</span></span>  <br/> |<span data-ttu-id="9844a-118">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9844a-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="9844a-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="9844a-119">Row index:</span></span>  <br/> |<span data-ttu-id="9844a-120">**visRowLine**</span><span class="sxs-lookup"><span data-stu-id="9844a-120">**visRowLine**</span></span> <br/> |
|<span data-ttu-id="9844a-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9844a-121">Cell index:</span></span>  <br/> |<span data-ttu-id="9844a-122">**visLineColor**</span><span class="sxs-lookup"><span data-stu-id="9844a-122">**visLineColor**</span></span> <br/> |
   

