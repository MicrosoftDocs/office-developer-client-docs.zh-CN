---
title: XRulerOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1170
localization_priority: Normal
ms.assetid: 328f8ab5-217f-0336-0d56-611eff509fe8
description: 指定页面 x 轴标尺上的零点。
ms.openlocfilehash: d66fd324718ec46b1209c4726eeb2d27c21db8b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346450"
---
# <a name="xrulerorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="6074e-103">XRulerOrigin 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="6074e-103">XRulerOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="6074e-104">指定页面 x 轴标尺上的零点。</span><span class="sxs-lookup"><span data-stu-id="6074e-104">Specifies the zero point on the x-axis ruler for the page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6074e-105">注解</span><span class="sxs-lookup"><span data-stu-id="6074e-105">Remarks</span></span>

<span data-ttu-id="6074e-106">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**标尺零点**" 选项。</span><span class="sxs-lookup"><span data-stu-id="6074e-106">This cell corresponds to the horizontal **Ruler zero** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="6074e-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XRulerOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6074e-107">To get a reference to the XRulerOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6074e-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6074e-108">Cell name:</span></span>  <br/> |<span data-ttu-id="6074e-109">XRulerOrigin</span><span class="sxs-lookup"><span data-stu-id="6074e-109">XRulerOrigin</span></span>  <br/> |
   
<span data-ttu-id="6074e-110">若要从某个程序按索引获取对 XRulerOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6074e-110">To get a reference to the XRulerOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6074e-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6074e-111">Section index:</span></span>  <br/> |<span data-ttu-id="6074e-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6074e-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="6074e-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="6074e-113">Row index:</span></span>  <br/> |<span data-ttu-id="6074e-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="6074e-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="6074e-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6074e-115">Cell index:</span></span>  <br/> |<span data-ttu-id="6074e-116">**visXRulerOrigin**</span><span class="sxs-lookup"><span data-stu-id="6074e-116">**visXRulerOrigin**</span></span> <br/> |
   

