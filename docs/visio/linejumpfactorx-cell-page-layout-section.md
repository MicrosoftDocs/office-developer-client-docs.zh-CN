---
title: LineJumpFactorX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm545
localization_priority: Normal
ms.assetid: 0649672f-f496-ce80-6dc3-3affc9b6f913
description: 确定页中水平动态连接线上跨线的大小（相对于 LineToLineX 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。
ms.openlocfilehash: 8698d99021ca64415417de8e946cbd80b586e759
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424992"
---
# <a name="linejumpfactorx-cell-page-layout-section"></a><span data-ttu-id="fcda7-104">LineJumpFactorX 单元格（“Page Layout”内容）</span><span class="sxs-lookup"><span data-stu-id="fcda7-104">LineJumpFactorX Cell (Page Layout Section)</span></span>

<span data-ttu-id="fcda7-p102">确定页中水平动态连接线上跨线的大小（相对于 LineToLineX 单元格的值）。该单元格的值范围可介于 0 到 10 之间，但建议使用 0 到 1 之间的小数值。</span><span class="sxs-lookup"><span data-stu-id="fcda7-p102">Determines the size of line jumps on horizontal dynamic connectors on the page, relative to the value of the LineToLineX cell. The value of this cell can range from 0 to 10 but fractional values from 0 to 1 are suggested.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fcda7-107">备注</span><span class="sxs-lookup"><span data-stu-id="fcda7-107">Remarks</span></span>

<span data-ttu-id="fcda7-108">还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。</span><span class="sxs-lookup"><span data-stu-id="fcda7-108">You can also set the value of this cell on the **Layout and Routing** tab in the **Page Setup** dialog box (on the **Design** tab, click the **Page Setup** arrow, and then click **Layout and Routing**).</span></span>
  
<span data-ttu-id="fcda7-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineJumpFactorX 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="fcda7-109">To get a reference to the LineJumpFactorX cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fcda7-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="fcda7-110">Cell name:</span></span>  <br/> |<span data-ttu-id="fcda7-111">LineJumpFactorX</span><span class="sxs-lookup"><span data-stu-id="fcda7-111">LineJumpFactorX</span></span>  <br/> |
   
<span data-ttu-id="fcda7-112">若要从某个程序按索引获取对 LineJumpFactorX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="fcda7-112">To get a reference to the LineJumpFactorX cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fcda7-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="fcda7-113">Section index:</span></span>  <br/> |<span data-ttu-id="fcda7-114">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="fcda7-114">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="fcda7-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="fcda7-115">Row index:</span></span>  <br/> |<span data-ttu-id="fcda7-116">**visRowPageLayout**</span><span class="sxs-lookup"><span data-stu-id="fcda7-116">**visRowPageLayout**</span></span> <br/> |
|<span data-ttu-id="fcda7-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="fcda7-117">Cell index:</span></span>  <br/> |<span data-ttu-id="fcda7-118">**visPLOJumpFactorX**</span><span class="sxs-lookup"><span data-stu-id="fcda7-118">**visPLOJumpFactorX**</span></span> <br/> |
   

