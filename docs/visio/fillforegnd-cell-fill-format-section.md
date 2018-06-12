---
title: FillForegnd 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251241
localization_priority: Normal
ms.assetid: 7548a480-4dce-45e0-281b-f6f8bdf05c0b
description: 确定用于形状的填充图案的前景（划线）颜色。
ms.openlocfilehash: 27126457963e4e55419b0cac5baf1eab08fe3cc6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780261"
---
# <a name="fillforegnd-cell-fill-format-section"></a><span data-ttu-id="a7b65-103">FillForegnd 单元格（“Fill Format”内容）</span><span class="sxs-lookup"><span data-stu-id="a7b65-103">FillForegnd Cell (Fill Format Section)</span></span>

<span data-ttu-id="a7b65-104">确定用于形状的填充图案的前景（划线）颜色。</span><span class="sxs-lookup"><span data-stu-id="a7b65-104">Determines the color used for the foreground (stroke) of the shape's fill pattern.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a7b65-105">注解</span><span class="sxs-lookup"><span data-stu-id="a7b65-105">Remarks</span></span>

<span data-ttu-id="a7b65-106">若要设置该颜色，请输入一个介于 0 和 23 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="a7b65-106">To set the color, enter a number from 0 to 23.</span></span>
  
<span data-ttu-id="a7b65-107">若要输入自定义颜色，使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="a7b65-107">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="a7b65-108">自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="a7b65-108">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="a7b65-109">当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="a7b65-109">When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="a7b65-110">您可以在 FillForegndTrans 单元格中设置前景填充的透明度。</span><span class="sxs-lookup"><span data-stu-id="a7b65-110">You can set the transparency of the foreground fill in the FillForegndTrans cell.</span></span>
  
<span data-ttu-id="a7b65-111">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 FillForegnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a7b65-111">To get a reference to the FillForegnd cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a7b65-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a7b65-112">Cell name:</span></span>  <br/> |<span data-ttu-id="a7b65-113">FillForegnd</span><span class="sxs-lookup"><span data-stu-id="a7b65-113">FillForegnd</span></span>  <br/> |
   
<span data-ttu-id="a7b65-114">若要从某个程序按索引获取对 FillForegnd 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="a7b65-114">To get a reference to the FillForegnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a7b65-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a7b65-115">Section index:</span></span>  <br/> |<span data-ttu-id="a7b65-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="a7b65-116">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="a7b65-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="a7b65-117">Row index:</span></span>  <br/> |<span data-ttu-id="a7b65-118">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="a7b65-118">**visRowFill**</span></span> <br/> |
|<span data-ttu-id="a7b65-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a7b65-119">Cell index:</span></span>  <br/> |<span data-ttu-id="a7b65-120">**visFillForegnd**</span><span class="sxs-lookup"><span data-stu-id="a7b65-120">**visFillForegnd**</span></span> <br/> |
   

