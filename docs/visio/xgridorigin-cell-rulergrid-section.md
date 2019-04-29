---
title: XGridOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1155
localization_priority: Normal
ms.assetid: 2b1a8902-b1d4-c3d9-8c9f-1a28fddacc59
description: 指定网格原点的水平坐标。
ms.openlocfilehash: ee58ea7d950dd7e422f8a60a13bac8aa4ed353a6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428618"
---
# <a name="xgridorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="ca951-103">XGridOrigin 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="ca951-103">XGridOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="ca951-104">指定网格原点的水平坐标。</span><span class="sxs-lookup"><span data-stu-id="ca951-104">Specifies the horizontal coordinate of the grid origin.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ca951-105">说明</span><span class="sxs-lookup"><span data-stu-id="ca951-105">Remarks</span></span>

<span data-ttu-id="ca951-106">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**网格起点**" 选项。</span><span class="sxs-lookup"><span data-stu-id="ca951-106">This cell corresponds to the horizontal **Grid origin** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow.</span></span> 
  
<span data-ttu-id="ca951-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ca951-107">To get a reference to the XGridOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ca951-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ca951-108">Cell name:</span></span>  <br/> |<span data-ttu-id="ca951-109">XGridOrigin</span><span class="sxs-lookup"><span data-stu-id="ca951-109">XGridOrigin</span></span>  <br/> |
   
<span data-ttu-id="ca951-110">若要从某个程序按索引获取对 XGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ca951-110">To get a reference to the XGridOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ca951-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ca951-111">Section index:</span></span>  <br/> |<span data-ttu-id="ca951-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="ca951-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="ca951-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="ca951-113">Row index:</span></span>  <br/> |<span data-ttu-id="ca951-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="ca951-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="ca951-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ca951-115">Cell index:</span></span>  <br/> |<span data-ttu-id="ca951-116">**visXGridOrigin**</span><span class="sxs-lookup"><span data-stu-id="ca951-116">**visXGridOrigin**</span></span> <br/> |
   

