---
title: TextBkgnd 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251267
localization_priority: Normal
ms.assetid: a238bf1c-1acd-eacd-22f3-a48acaaa4549
description: 确定一个形状的文本背景色。
ms.openlocfilehash: 2450bf0cb0e013c0f9310eacfca0f5a20e7e6063
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406540"
---
# <a name="textbkgnd-cell-text-block-format-section"></a><span data-ttu-id="ac61b-103">TextBkgnd 单元格（“Text Block Format”内容）</span><span class="sxs-lookup"><span data-stu-id="ac61b-103">TextBkgnd Cell (Text Block Format Section)</span></span>

<span data-ttu-id="ac61b-104">确定一个形状的文本背景色。</span><span class="sxs-lookup"><span data-stu-id="ac61b-104">Determines the text background color for a shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ac61b-105">说明</span><span class="sxs-lookup"><span data-stu-id="ac61b-105">Remarks</span></span>

<span data-ttu-id="ac61b-106">TextBkgnd 单元格的值可以是 0 到 24 之间的任意值，或者是 255。</span><span class="sxs-lookup"><span data-stu-id="ac61b-106">The TextBkgnd cell can have any value from 0 through 24, or 255.</span></span> <span data-ttu-id="ac61b-107">值0和 255 ( *visTxtBlklOpaque*) 都表示透明文本背景。</span><span class="sxs-lookup"><span data-stu-id="ac61b-107">The values 0 and 255 ( *visTxtBlklOpaque*) both indicate a transparent text background.</span></span> 
  
<span data-ttu-id="ac61b-108">若要输入自定义颜色，请使用 RGB 或 HSL 函数加 1，例如 RGB(255,127,255)+1。</span><span class="sxs-lookup"><span data-stu-id="ac61b-108">To enter a custom color, use the RGB or HSL function plus one—for example, RGB(255,127,255)+1.</span></span> <span data-ttu-id="ac61b-109">自定义颜色的值是其 RGB 颜色, 而 rgb ( *r, g, b*) + 1, 而不是数字, 将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="ac61b-109">The value of a custom color is its RGB color, and RGB( *r, g, b*)+1, rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="ac61b-110">在数值运算中使用自定义颜色时，其值将大于或等于 25。</span><span class="sxs-lookup"><span data-stu-id="ac61b-110">When used in numeric operations, custom colors have values of 25 and above.</span></span> 
  
<span data-ttu-id="ac61b-111">您可以在 TextBkgndTrans 单元格中设置文本背景色的透明度。</span><span class="sxs-lookup"><span data-stu-id="ac61b-111">You can set the transparency of the text background color in the TextBkgndTrans cell.</span></span>
  
<span data-ttu-id="ac61b-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 TextBkgnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ac61b-112">To get a reference to the TextBkgnd cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac61b-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ac61b-113">Cell name:</span></span>  <br/> |<span data-ttu-id="ac61b-114">TextBkgnd</span><span class="sxs-lookup"><span data-stu-id="ac61b-114">TextBkgnd</span></span>  <br/> |
   
<span data-ttu-id="ac61b-115">若要从某个程序按索引获取对 TextBkgnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ac61b-115">To get a reference to the TextBkgnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac61b-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ac61b-116">Section index:</span></span>  <br/> |<span data-ttu-id="ac61b-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ac61b-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ac61b-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="ac61b-118">Row index:</span></span>  <br/> |<span data-ttu-id="ac61b-119">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="ac61b-119">**visRowText**</span></span> <br/> |
|<span data-ttu-id="ac61b-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ac61b-120">Cell index:</span></span>  <br/> |<span data-ttu-id="ac61b-121">**visTxtBlkBkgnd**</span><span class="sxs-lookup"><span data-stu-id="ac61b-121">**visTxtBlkBkgnd**</span></span> <br/> |
   

