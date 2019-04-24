---
title: Color 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm160
localization_priority: Normal
ms.assetid: 1c9aab2e-6c2f-0684-4e66-c35ac71883d6
description: 确定形状的文本要使用的颜色。
ms.openlocfilehash: a27d957781ca9a784e7ab9d5c1ce4f533b9a55ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341837"
---
# <a name="color-cell-character-section"></a><span data-ttu-id="c85a1-103">Color 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="c85a1-103">Color Cell (Character Section)</span></span>

<span data-ttu-id="c85a1-104">确定形状的文本要使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="c85a1-104">Determines the color used for the shape's text.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c85a1-105">注解</span><span class="sxs-lookup"><span data-stu-id="c85a1-105">Remarks</span></span>

<span data-ttu-id="c85a1-106">若要设置该颜色，请输入一个介于 0 和 23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="c85a1-106">To set the color, enter a number from 0 to 23.</span></span>
  
<span data-ttu-id="c85a1-107">若要输入自定义颜色，请使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="c85a1-107">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="c85a1-108">自定义颜色的值是其 RGB 颜色, 而 rgb ( *r, g, b*), 而不是数字, 将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="c85a1-108">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="c85a1-109">在数值运算中使用自定义颜色时，其值将大于或等于 24。</span><span class="sxs-lookup"><span data-stu-id="c85a1-109">When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="c85a1-110">您可以在 Transparency 单元格中设置文本颜色的透明度。</span><span class="sxs-lookup"><span data-stu-id="c85a1-110">You can set the transparency of the text color in the Transparency cell.</span></span>
  
<span data-ttu-id="c85a1-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c85a1-111">To get a reference to the Color cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c85a1-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c85a1-112">Cell name:</span></span>  <br/> |<span data-ttu-id="c85a1-113">Char. Color [ *i* ] 其中*i* = <1>, 2, 3, .。。</span><span class="sxs-lookup"><span data-stu-id="c85a1-113">Char.Color[ *i*  ]           where  *i*  = <1>, 2, 3, ...</span></span>  <br/> |
   
<span data-ttu-id="c85a1-114">若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c85a1-114">To get a reference to the Color cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c85a1-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c85a1-115">Section index:</span></span>  <br/> |<span data-ttu-id="c85a1-116">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="c85a1-116">**visSectionCharacter**</span></span> <br/> |
|<span data-ttu-id="c85a1-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="c85a1-117">Row index:</span></span>  <br/> |<span data-ttu-id="c85a1-118">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="c85a1-118">**visRowCharacter** +  *i*           where  *i*  = 0, 1, 2, ...</span></span>  <br/> |
|<span data-ttu-id="c85a1-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c85a1-119">Cell index:</span></span>  <br/> |<span data-ttu-id="c85a1-120">**visCharacterColor**</span><span class="sxs-lookup"><span data-stu-id="c85a1-120">**visCharacterColor**</span></span> <br/> |
   

