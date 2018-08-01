---
title: LineToLineY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm570
localization_priority: Normal
ms.assetid: db9a8232-25c5-7087-2ae9-50470d0cf16e
description: 确定在绘图页上所有连接线之间的垂直间距。
ms.openlocfilehash: 781d166fe0b81cc2402fde2894cd1d0480a0895f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780583"
---
# <a name="linetoliney-cell-page-layout-section"></a><span data-ttu-id="2cc58-103">LineToLineY 单元格（“Page Layout”部分）</span><span class="sxs-lookup"><span data-stu-id="2cc58-103">LineToLineY Cell (Page Layout Section)</span></span>

<span data-ttu-id="2cc58-104">确定在绘图页上所有连接线之间的垂直间距。</span><span class="sxs-lookup"><span data-stu-id="2cc58-104">Determines the vertical clearance between all connectors on the drawing page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2cc58-105">注解</span><span class="sxs-lookup"><span data-stu-id="2cc58-105">Remarks</span></span>

<span data-ttu-id="2cc58-p101">您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）</span><span class="sxs-lookup"><span data-stu-id="2cc58-p101">You can also set the value of this cell in the **Layout and Routing Spacing** dialog box. (On the **Design** tab, click the **Page Setup** arrow, click **Layout and Routing**, and then click **Spacing**.)</span></span>
  
<span data-ttu-id="2cc58-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToLineY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2cc58-108">To get a reference to the LineToLineY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2cc58-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2cc58-109">Cell name:</span></span>  <br/> |<span data-ttu-id="2cc58-110">LineToLineY</span><span class="sxs-lookup"><span data-stu-id="2cc58-110">LineToLineY</span></span>  <br/> |
   
<span data-ttu-id="2cc58-111">若要从某个程序按索引获取对 LineToLineY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2cc58-111">To get a reference to the LineToLineY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2cc58-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2cc58-112">Section index:</span></span>  <br/> |<span data-ttu-id="2cc58-113">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="2cc58-113">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="2cc58-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="2cc58-114">Row index:</span></span>  <br/> |<span data-ttu-id="2cc58-115">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="2cc58-115">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="2cc58-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2cc58-116">Cell index:</span></span>  <br/> |<span data-ttu-id="2cc58-117">**visPLOLineToLineY**</span><span class="sxs-lookup"><span data-stu-id="2cc58-117">**visPLOLineToLineY**</span></span> <br/> |
   

