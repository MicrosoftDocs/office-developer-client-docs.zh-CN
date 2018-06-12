---
title: LineJumpFactorY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm550
localization_priority: Normal
ms.assetid: 5a14be0d-9e3c-23c4-7782-bda5470d1243
description: 确定页中垂直动态连接线上的跨线的大小（相对于 LineToLineY 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。
ms.openlocfilehash: deba4c27585644604e7bac1dbfe284bc3977835e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780590"
---
# <a name="linejumpfactory-cell-page-layout-section"></a><span data-ttu-id="7ba14-104">LineJumpFactorY 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="7ba14-104">LineJumpFactorY Cell (Page Layout Section)</span></span>

<span data-ttu-id="7ba14-p102">确定页中垂直动态连接线上的跨线的大小（相对于 LineToLineY 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。</span><span class="sxs-lookup"><span data-stu-id="7ba14-p102">Determines the size of line jumps on vertical dynamic connectors on the page, relative to the value of the LineToLineY cell. The value of this cell can range from 0 to 10 but fractional values from 0 to 1 are suggested.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7ba14-107">注解</span><span class="sxs-lookup"><span data-stu-id="7ba14-107">Remarks</span></span>

<span data-ttu-id="7ba14-108">您还可以在**页面设置**对话框中**布局和路由**选项卡上设置此单元格的值 （**设计**选项卡中，单击**页面设置**箭头，然后单击**布局与排列**）。</span><span class="sxs-lookup"><span data-stu-id="7ba14-108">You can also set the value of this cell on the **Layout and Routing** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then click **Layout and Routing**).</span></span>
  
<span data-ttu-id="7ba14-109">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LineJumpFactorY 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7ba14-109">To get a reference to the LineJumpFactorY cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ba14-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7ba14-110">Cell name:</span></span>  <br/> |<span data-ttu-id="7ba14-111">LineJumpFactorY</span><span class="sxs-lookup"><span data-stu-id="7ba14-111">LineJumpFactorY</span></span>  <br/> |
   
<span data-ttu-id="7ba14-112">若要从某个程序按索引获取对 LineJumpFactorY 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="7ba14-112">To get a reference to the LineJumpFactorY cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ba14-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7ba14-113">Section index:</span></span>  <br/> |<span data-ttu-id="7ba14-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="7ba14-114">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="7ba14-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="7ba14-115">Row index:</span></span>  <br/> |<span data-ttu-id="7ba14-116">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="7ba14-116">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="7ba14-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7ba14-117">Cell index:</span></span>  <br/> |<span data-ttu-id="7ba14-118">**visPLOJumpFactorY**</span><span class="sxs-lookup"><span data-stu-id="7ba14-118">**visPLOJumpFactorY**</span></span> <br/> |
   

