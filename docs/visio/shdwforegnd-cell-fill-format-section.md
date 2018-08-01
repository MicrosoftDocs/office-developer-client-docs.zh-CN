---
title: ShdwForegnd 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251244
localization_priority: Normal
ms.assetid: ea153390-631d-79fd-c1ba-4c281239a24e
description: 确定用于形状的投影填充图案的前景（划线）的颜色。
ms.openlocfilehash: f39109a296949d23142017661bb55f0708402d8f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781331"
---
# <a name="shdwforegnd-cell-fill-format-section"></a><span data-ttu-id="742b3-103">ShdwForegnd 单元格（“Fill Format”部分）</span><span class="sxs-lookup"><span data-stu-id="742b3-103">ShdwForegnd Cell (Fill Format Section)</span></span>

<span data-ttu-id="742b3-104">确定用于形状的投影填充图案的前景（划线）的颜色。</span><span class="sxs-lookup"><span data-stu-id="742b3-104">Determines the color used for the foreground (stroke) of the shape's drop shadow fill pattern.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="742b3-105">注解</span><span class="sxs-lookup"><span data-stu-id="742b3-105">Remarks</span></span>

<span data-ttu-id="742b3-106">若要设置颜色，请输入 0 到 23 之间的一个数字，该数字是颜色集合中的一个索引。</span><span class="sxs-lookup"><span data-stu-id="742b3-106">To set the color, enter a number from 0 to 23, which is an index into a collection of colors.</span></span>
  
<span data-ttu-id="742b3-107">若要输入自定义颜色，使用 RGB 或 HSL 函数。</span><span class="sxs-lookup"><span data-stu-id="742b3-107">To enter a custom color, use the RGB or HSL function.</span></span> <span data-ttu-id="742b3-108">自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="742b3-108">The value of a custom color is its RGB color, and RGB( *r, g, b*), rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="742b3-109">当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。</span><span class="sxs-lookup"><span data-stu-id="742b3-109">When used in numeric operations, custom colors have values of 24 and above.</span></span> 
  
<span data-ttu-id="742b3-110">您可以在 ShdwForegndTrans 单元格中设置形状的投影填充图案前景色的透明度。</span><span class="sxs-lookup"><span data-stu-id="742b3-110">You can set the transparency of the foreground color of the shape's drop shadow fill pattern in the ShdwForegndTrans cell.</span></span>
  
<span data-ttu-id="742b3-111">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwForegnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="742b3-111">To get a reference to the ShdwForegnd cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="742b3-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="742b3-112">Cell name:</span></span>  <br/> | <span data-ttu-id="742b3-113">ShdwForegnd</span><span class="sxs-lookup"><span data-stu-id="742b3-113">ShdwForegnd</span></span>  <br/> |
   
<span data-ttu-id="742b3-114">若要从某个程序按索引获取对 ShdwForegnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="742b3-114">To get a reference to the ShdwForegnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="742b3-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="742b3-115">Section index:</span></span>  <br/> |<span data-ttu-id="742b3-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="742b3-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="742b3-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="742b3-117">Row index:</span></span>  <br/> |<span data-ttu-id="742b3-118">**visRowFill**</span><span class="sxs-lookup"><span data-stu-id="742b3-118">**visRowFill**</span></span> <br/> |
| <span data-ttu-id="742b3-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="742b3-119">Cell index:</span></span>  <br/> |<span data-ttu-id="742b3-120">**visFillShdwForegnd**</span><span class="sxs-lookup"><span data-stu-id="742b3-120">**visFillShdwForegnd**</span></span> <br/> |
   

