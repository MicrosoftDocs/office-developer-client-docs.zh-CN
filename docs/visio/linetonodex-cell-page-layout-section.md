---
title: LineToNodeX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm575
localization_priority: Normal
ms.assetid: 9d58e23e-b411-c5c1-b785-5014488d42c8
description: 确定在绘图页上所有连接线和形状之间的水平间距。
ms.openlocfilehash: 75f7e8150711421138a01175be34003d124e88ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780587"
---
# <a name="linetonodex-cell-page-layout-section"></a><span data-ttu-id="98d27-103">LineToNodeX 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="98d27-103">LineToNodeX Cell (Page Layout Section)</span></span>

<span data-ttu-id="98d27-104">确定在绘图页上所有连接线和形状之间的水平间距。</span><span class="sxs-lookup"><span data-stu-id="98d27-104">Determines the horizontal clearance between all connectors and shapes on the drawing page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="98d27-105">注解</span><span class="sxs-lookup"><span data-stu-id="98d27-105">Remarks</span></span>

<span data-ttu-id="98d27-p101">您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）</span><span class="sxs-lookup"><span data-stu-id="98d27-p101">You can also set the value of this cell in the **Layout and Routing Spacing** dialog box. (On the **Design** tab, click the **Page Setup** arrow, click **Layout and Routing**, and then click **Spacing**.)</span></span>
  
<span data-ttu-id="98d27-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToNodeY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="98d27-108">To get a reference to the LineToNodeY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98d27-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="98d27-109">Cell name:</span></span>  <br/> |<span data-ttu-id="98d27-110">LineToNodeX</span><span class="sxs-lookup"><span data-stu-id="98d27-110">LineToNodeX</span></span>  <br/> |
   
<span data-ttu-id="98d27-111">若要从某个程序按索引获取对 LineToNodeX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="98d27-111">To get a reference to the LineToNodeX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98d27-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="98d27-112">Section index:</span></span>  <br/> |<span data-ttu-id="98d27-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="98d27-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="98d27-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="98d27-114">Row index:</span></span>  <br/> |<span data-ttu-id="98d27-115">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="98d27-115">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="98d27-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="98d27-116">Cell index:</span></span>  <br/> |<span data-ttu-id="98d27-117">**visPLOLineToNodeX**</span><span class="sxs-lookup"><span data-stu-id="98d27-117">**visPLOLineToNodeX**</span></span> <br/> |
   

