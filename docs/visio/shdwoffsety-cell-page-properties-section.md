---
title: ShdwOffsetY 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm930
localization_priority: Normal
ms.assetid: f3f53a7d-7450-b2b0-b508-6044a87450d9
description: 确定形状的投影与该形状垂直偏移的距离（按页面单位）。
ms.openlocfilehash: be7ec4cccd53cc9d74811e2e45122c8bc29497d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438139"
---
# <a name="shdwoffsety-cell-page-properties-section"></a><span data-ttu-id="9be50-103">ShdwOffsetY 单元格（“Page Properties”内容）</span><span class="sxs-lookup"><span data-stu-id="9be50-103">ShdwOffsetY Cell (Page Properties Section)</span></span>

<span data-ttu-id="9be50-104">确定形状的投影与该形状垂直偏移的距离（按页面单位）。</span><span class="sxs-lookup"><span data-stu-id="9be50-104">Determines the distance in page units that a shape's drop shadow is offset vertically from the shape.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9be50-105">备注</span><span class="sxs-lookup"><span data-stu-id="9be50-105">Remarks</span></span>

<span data-ttu-id="9be50-p101">此值在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中设置。此值与绘图的缩放比例无关。即使绘图按比例缩放，阴影偏移量也仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="9be50-p101">This value is set in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow). This value is independent of the scale of the drawing. If the drawing is scaled, the shadow offset remains the same.</span></span> 
  
<span data-ttu-id="9be50-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwOffsetY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9be50-109">To get a reference to the ShdwOffsetY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9be50-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9be50-110">Cell name:</span></span>  <br/> | <span data-ttu-id="9be50-111">ShdwOffsetY</span><span class="sxs-lookup"><span data-stu-id="9be50-111">ShdwOffsetY</span></span>  <br/> |
   
<span data-ttu-id="9be50-112">若要从某个程序按索引获取对 ShdwOffsetY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9be50-112">To get a reference to the ShdwOffsetY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9be50-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9be50-113">Section index:</span></span>  <br/> |<span data-ttu-id="9be50-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9be50-114">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="9be50-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="9be50-115">Row index:</span></span>  <br/> |<span data-ttu-id="9be50-116">**visRowPage**</span><span class="sxs-lookup"><span data-stu-id="9be50-116">**visRowPage**</span></span> <br/> |
| <span data-ttu-id="9be50-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9be50-117">Cell index:</span></span>  <br/> |<span data-ttu-id="9be50-118">**visPageShdwOffsetY**</span><span class="sxs-lookup"><span data-stu-id="9be50-118">**visPageShdwOffsetY**</span></span> <br/> |
   

