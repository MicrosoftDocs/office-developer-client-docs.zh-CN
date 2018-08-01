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
ms.openlocfilehash: b6728d44c71f6403e772a6a7e730ba3c18d9eb48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779893"
---
# <a name="color-cell-layers-section"></a><span data-ttu-id="72834-103">Color 单元格（“Layers”部分）</span><span class="sxs-lookup"><span data-stu-id="72834-103">Color Cell (Layers Section)</span></span>

<span data-ttu-id="72834-104">指定用于显示图层的颜色。</span><span class="sxs-lookup"><span data-stu-id="72834-104">Specifies the color used to display the layer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="72834-105">注解</span><span class="sxs-lookup"><span data-stu-id="72834-105">Remarks</span></span>

<span data-ttu-id="72834-106">若要设置该颜色，请输入一个介于 0 和 23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="72834-106">To set the color, enter a number from 0 to 23.</span></span>
  
<span data-ttu-id="72834-107">此单元格的值对应于**图层属性**对话框中的**图层颜色**设置 （在**主页**选项卡上的**编辑**组中，单击**图层**，然后单击**图层属性**）。</span><span class="sxs-lookup"><span data-stu-id="72834-107">This cell value corresponds to the **Layer color** setting in the **Layer Properties** dialog box (in the **Editing** group on the **Home** tab, click **Layers** and then click **Layer Properties**).</span></span>
  
<span data-ttu-id="72834-108">若要输入自定义颜色，使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="72834-108">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="72834-109">自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="72834-109">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="72834-110">当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="72834-110">When used in numeric operations, custom colors have values of 24 and above.</span></span> <span data-ttu-id="72834-111">255 之间的值表示层都有无颜色。</span><span class="sxs-lookup"><span data-stu-id="72834-111">A value of 255 indicates that the layer has no color.</span></span> 
  
<span data-ttu-id="72834-112">您可以在 Transparency 单元格中设置图层颜色的透明度。</span><span class="sxs-lookup"><span data-stu-id="72834-112">You can set the transparency of the layer color in the Transparency cell.</span></span>
  
<span data-ttu-id="72834-113">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="72834-113">To get a reference to the Color cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="72834-114">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="72834-114">Cell name:</span></span>  <br/> |<span data-ttu-id="72834-115">Layers.Color [ *i* ] 其中*i* = < 1 >，2，3，...</span><span class="sxs-lookup"><span data-stu-id="72834-115">Layers.Color[ *i*  ]           where  *i*  = <1>, 2, 3, ...</span></span>  <br/> |
   
<span data-ttu-id="72834-116">若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="72834-116">To get a reference to the Color cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="72834-117">内容索引：</span><span class="sxs-lookup"><span data-stu-id="72834-117">Section index:</span></span>  <br/> |<span data-ttu-id="72834-118">**visSectionLayer**</span><span class="sxs-lookup"><span data-stu-id="72834-118">**visSectionLayer**</span></span> <br/> |
|<span data-ttu-id="72834-119">行索引：</span><span class="sxs-lookup"><span data-stu-id="72834-119">Row index:</span></span>  <br/> |<span data-ttu-id="72834-120">**visRowLayer** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="72834-120">**visRowLayer** +  *i*           where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="72834-121">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="72834-121">Cell index:</span></span>  <br/> |<span data-ttu-id="72834-122">**visLayerColor**</span><span class="sxs-lookup"><span data-stu-id="72834-122">**visLayerColor**</span></span> <br/> |
   

