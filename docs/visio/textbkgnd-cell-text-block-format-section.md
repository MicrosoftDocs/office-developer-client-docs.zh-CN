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
ms.openlocfilehash: 2256a4c89812924af820c020c225f4b82b1d4856
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781510"
---
# <a name="textbkgnd-cell-text-block-format-section"></a><span data-ttu-id="029b8-103">TextBkgnd 单元格（“Text Block Format”部分）</span><span class="sxs-lookup"><span data-stu-id="029b8-103">TextBkgnd Cell (Text Block Format Section)</span></span>

<span data-ttu-id="029b8-104">确定一个形状的文本背景色。</span><span class="sxs-lookup"><span data-stu-id="029b8-104">Determines the text background color for a shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="029b8-105">注解</span><span class="sxs-lookup"><span data-stu-id="029b8-105">Remarks</span></span>

<span data-ttu-id="029b8-106">TextBkgnd 单元格可以具有任何值从 0 到 24 或 255。</span><span class="sxs-lookup"><span data-stu-id="029b8-106">The TextBkgnd cell can have any value from 0 through 24, or 255.</span></span> <span data-ttu-id="029b8-107">值 0 和 255 ( *visTxtBlklOpaque*) 指示透明的文本背景。</span><span class="sxs-lookup"><span data-stu-id="029b8-107">The values 0 and 255 ( *visTxtBlklOpaque*) both indicate a transparent text background.</span></span> 
  
<span data-ttu-id="029b8-108">若要输入自定义颜色，使用 RGB 或 HSL 函数加 1 — 例如，RGB (255,127,255) + 1。</span><span class="sxs-lookup"><span data-stu-id="029b8-108">To enter a custom color, use the RGB or HSL function plus one—for example, RGB(255,127,255)+1.</span></span> <span data-ttu-id="029b8-109">自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*） + 1，而不是一个号码，将显示在 ShapeSheet 窗口中。</span><span class="sxs-lookup"><span data-stu-id="029b8-109">The value of a custom color is its RGB color, and RGB( *r, g, b*)+1, rather than a number, will be shown in the ShapeSheet window.</span></span> <span data-ttu-id="029b8-110">中的数字运算使用时，自定义颜色具有值将大于或等于 25。</span><span class="sxs-lookup"><span data-stu-id="029b8-110">When used in numeric operations, custom colors have values of 25 and above.</span></span> 
  
<span data-ttu-id="029b8-111">您可以在 TextBkgndTrans 单元格中设置文本背景色的透明度。</span><span class="sxs-lookup"><span data-stu-id="029b8-111">You can set the transparency of the text background color in the TextBkgndTrans cell.</span></span>
  
<span data-ttu-id="029b8-112">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 TextBkgnd 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="029b8-112">To get a reference to the TextBkgnd cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="029b8-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="029b8-113">Cell name:</span></span>  <br/> |<span data-ttu-id="029b8-114">TextBkgnd</span><span class="sxs-lookup"><span data-stu-id="029b8-114">TextBkgnd</span></span>  <br/> |
   
<span data-ttu-id="029b8-115">若要从某个程序按索引获取对 TextBkgnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="029b8-115">To get a reference to the TextBkgnd cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="029b8-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="029b8-116">Section index:</span></span>  <br/> |<span data-ttu-id="029b8-117">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="029b8-117">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="029b8-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="029b8-118">Row index:</span></span>  <br/> |<span data-ttu-id="029b8-119">**visRowText**</span><span class="sxs-lookup"><span data-stu-id="029b8-119">**visRowText**</span></span> <br/> |
|<span data-ttu-id="029b8-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="029b8-120">Cell index:</span></span>  <br/> |<span data-ttu-id="029b8-121">**visTxtBlkBkgnd**</span><span class="sxs-lookup"><span data-stu-id="029b8-121">**visTxtBlkBkgnd**</span></span> <br/> |
   

