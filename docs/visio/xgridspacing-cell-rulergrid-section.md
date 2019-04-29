---
title: XGridSpacing 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1160
localization_priority: Normal
ms.assetid: e07dd983-7588-6317-944c-46da2bb65b31
description: 指定固定网格中水平线条间的距离 (XGridDensity = 0)。
ms.openlocfilehash: 05b68a9721dbfc9c03402d384d976c42ef05b134
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435073"
---
# <a name="xgridspacing-cell-ruler-amp-grid-section"></a><span data-ttu-id="56792-103">XGridSpacing 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="56792-103">XGridSpacing Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="56792-104">指定固定网格中水平线条间的距离 (XGridDensity = 0)。</span><span class="sxs-lookup"><span data-stu-id="56792-104">Specifies the distance between horizontal lines in a fixed grid (XGridDensity = 0).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="56792-105">说明</span><span class="sxs-lookup"><span data-stu-id="56792-105">Remarks</span></span>

<span data-ttu-id="56792-106">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**最小间距**" 选项。</span><span class="sxs-lookup"><span data-stu-id="56792-106">This cell corresponds to the horizontal **Minimum spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="56792-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridSpacing 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="56792-107">To get a reference to the XGridSpacing cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56792-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="56792-108">Cell name:</span></span>  <br/> |<span data-ttu-id="56792-109">XGridSpacing</span><span class="sxs-lookup"><span data-stu-id="56792-109">XGridSpacing</span></span>  <br/> |
   
<span data-ttu-id="56792-110">若要从某个程序按索引获取对 XGridSpacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="56792-110">To get a reference to the XGridSpacing cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56792-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="56792-111">Section index:</span></span>  <br/> |<span data-ttu-id="56792-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="56792-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="56792-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="56792-113">Row index:</span></span>  <br/> |<span data-ttu-id="56792-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="56792-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="56792-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="56792-115">Cell index:</span></span>  <br/> |<span data-ttu-id="56792-116">**visXGridSpacing**</span><span class="sxs-lookup"><span data-stu-id="56792-116">**visXGridSpacing**</span></span> <br/> |
   

