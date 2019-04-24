---
title: Color 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm165
localization_priority: Normal
ms.assetid: 61c19342-46fb-48d4-6375-c9ea8306286d
description: 指定用于显示图层的颜色。
ms.openlocfilehash: a2eef24187165cabfdfc8dee49747a2381562d3e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341823"
---
# <a name="color-cell-layers-section"></a><span data-ttu-id="7409a-103">Color 单元格（“Layers”内容）</span><span class="sxs-lookup"><span data-stu-id="7409a-103">Color Cell (Layers Section)</span></span>

<span data-ttu-id="7409a-104">指定用于显示图层的颜色。</span><span class="sxs-lookup"><span data-stu-id="7409a-104">Specifies the color used to display the layer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7409a-105">注解</span><span class="sxs-lookup"><span data-stu-id="7409a-105">Remarks</span></span>

<span data-ttu-id="7409a-106">若要设置该颜色，请输入一个介于 0 和 23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="7409a-106">To set the color, enter a number from 0 to 23.</span></span>
  
<span data-ttu-id="7409a-107">此单元格值对应于 "**图层属性**" 对话框 (在 "**开始**" 选项卡上的 "**编辑**" 组中, 依次单击 "**层**" 和 "**图层属性**") 中的 "**图层颜色**" 设置</span><span class="sxs-lookup"><span data-stu-id="7409a-107">This cell value corresponds to the **Layer color** setting in the **Layer Properties** dialog box (in the **Editing** group on the **Home** tab, click **Layers** and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="7409a-108">若要输入自定义颜色，请使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="7409a-108">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="7409a-109">自定义颜色的值是其 RGB 颜色, 而 rgb ( *r, g, b*), 而不是数字, 将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="7409a-109">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="7409a-110">在数值运算中使用自定义颜色时，其值将大于或等于 24。</span><span class="sxs-lookup"><span data-stu-id="7409a-110">When used in numeric operations, custom colors have values of 24 and above.</span></span> <span data-ttu-id="7409a-111">如果值是 255，则指示图层没有颜色。</span><span class="sxs-lookup"><span data-stu-id="7409a-111">A value of 255 indicates that the layer has no color.</span></span> 
  
<span data-ttu-id="7409a-112">您可以在 Transparency 单元格中设置图层颜色的透明度。</span><span class="sxs-lookup"><span data-stu-id="7409a-112">You can set the transparency of the layer color in the Transparency cell.</span></span>
  
<span data-ttu-id="7409a-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7409a-113">To get a reference to the Color cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7409a-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7409a-114">Cell name:</span></span>  <br/> |<span data-ttu-id="7409a-115">图层。颜色 [ *i* ] 其中*i* = <1>, 2, 3, .。。</span><span class="sxs-lookup"><span data-stu-id="7409a-115">Layers.Color[ *i*  ]           where  *i*  = <1>, 2, 3, ...</span></span>  <br/> |
   
<span data-ttu-id="7409a-116">若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7409a-116">To get a reference to the Color cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7409a-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7409a-117">Section index:</span></span>  <br/> |<span data-ttu-id="7409a-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="7409a-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="7409a-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="7409a-119">Row index:</span></span>  <br/> |<span data-ttu-id="7409a-120">**visRowLayer** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="7409a-120">**visRowLayer** +  *i*           where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="7409a-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7409a-121">Cell index:</span></span>  <br/> |<span data-ttu-id="7409a-122">**visLayerColor**</span><span class="sxs-lookup"><span data-stu-id="7409a-122">**visLayerColor**</span></span> <br/> |
   

