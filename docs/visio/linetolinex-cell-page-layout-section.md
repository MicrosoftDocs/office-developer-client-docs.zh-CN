---
title: LineToLineX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm565
localization_priority: Normal
ms.assetid: f6b461fe-56ac-4c0e-31cd-6b3c1075db6e
description: 确定在绘图页上所有连接线之间的水平间距。
ms.openlocfilehash: f3dbf43c737fef1fa1156fb4dc8d0f23449328c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416326"
---
# <a name="linetolinex-cell-page-layout-section"></a><span data-ttu-id="4cd45-103">LineToLineX 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="4cd45-103">LineToLineX Cell (Page Layout Section)</span></span>

<span data-ttu-id="4cd45-104">确定在绘图页上所有连接线之间的水平间距。</span><span class="sxs-lookup"><span data-stu-id="4cd45-104">Determines the horizontal clearance between all connectors on the drawing page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4cd45-105">备注</span><span class="sxs-lookup"><span data-stu-id="4cd45-105">Remarks</span></span>

<span data-ttu-id="4cd45-p101">您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）</span><span class="sxs-lookup"><span data-stu-id="4cd45-p101">You can also set the value of this cell in the **Layout and Routing Spacing** dialog box. (On the **Design** tab, click the **Page Setup** arrow, click **Layout and Routing**, and then click **Spacing**.)</span></span>
  
<span data-ttu-id="4cd45-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToLineX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="4cd45-108">To get a reference to the LineToLineX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4cd45-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4cd45-109">Cell name:</span></span>  <br/> |<span data-ttu-id="4cd45-110">LineToLineX</span><span class="sxs-lookup"><span data-stu-id="4cd45-110">LineToLineX</span></span>  <br/> |
   
<span data-ttu-id="4cd45-111">若要从某个程序按索引获取对 LineToLineX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="4cd45-111">To get a reference to the LineToLineX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4cd45-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4cd45-112">Section index:</span></span>  <br/> |<span data-ttu-id="4cd45-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="4cd45-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="4cd45-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="4cd45-114">Row index:</span></span>  <br/> |<span data-ttu-id="4cd45-115">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="4cd45-115">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="4cd45-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4cd45-116">Cell index:</span></span>  <br/> |<span data-ttu-id="4cd45-117">**visPLOLineToLineX**</span><span class="sxs-lookup"><span data-stu-id="4cd45-117">**visPLOLineToLineX**</span></span> <br/> |
   

