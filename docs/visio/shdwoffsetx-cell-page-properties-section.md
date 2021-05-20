---
title: ShdwOffsetX 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251373
localization_priority: Normal
ms.assetid: 92ec9b11-f53f-a1c9-832a-6cac08aa5379
description: 确定形状的投影与该形状水平偏移的距离（按页面单位）。
ms.openlocfilehash: fbc7d37fc8ba45f3219af6a4350301102954f23d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431650"
---
# <a name="shdwoffsetx-cell-page-properties-section"></a><span data-ttu-id="9fd24-103">ShdwOffsetX 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="9fd24-103">ShdwOffsetX Cell (Page Properties Section)</span></span>

<span data-ttu-id="9fd24-104">确定形状的投影与该形状水平偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="9fd24-104">Determines the distance in page units that a shape's drop shadow is offset horizontally from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9fd24-105">备注</span><span class="sxs-lookup"><span data-stu-id="9fd24-105">Remarks</span></span>

<span data-ttu-id="9fd24-p101">此值在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中设置。此值与绘图的缩放比例无关。即使绘图按比例缩放，阴影偏移量也仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="9fd24-p101">This value is set in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow). This value is independent of the scale of the drawing. If the drawing is scaled, the shadow offset remains the same.</span></span> 
  
<span data-ttu-id="9fd24-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwOffsetX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9fd24-109">To get a reference to the ShdwOffsetX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9fd24-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9fd24-110">Cell name:</span></span>  <br/> | <span data-ttu-id="9fd24-111">ShdwOffsetX</span><span class="sxs-lookup"><span data-stu-id="9fd24-111">ShdwOffsetX</span></span>  <br/> |
   
<span data-ttu-id="9fd24-112">若要从某个程序按索引获取对 ShdwOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9fd24-112">To get a reference to the ShdwOffsetX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9fd24-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9fd24-113">Section index:</span></span>  <br/> |<span data-ttu-id="9fd24-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9fd24-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9fd24-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="9fd24-115">Row index:</span></span>  <br/> |<span data-ttu-id="9fd24-116">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="9fd24-116">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="9fd24-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9fd24-117">Cell index:</span></span>  <br/> |<span data-ttu-id="9fd24-118">**visPageShdwOffsetX**</span><span class="sxs-lookup"><span data-stu-id="9fd24-118">**visPageShdwOffsetX**</span></span> <br/> |
   

