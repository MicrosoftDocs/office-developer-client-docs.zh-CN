---
title: YGridOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1205
localization_priority: Normal
ms.assetid: eeec59f8-f301-5639-ffd6-8a36b2bf9c8f
description: 指定网格的垂直起点。
ms.openlocfilehash: fa8ee15d5ef2b5d581a9532336d3983bed17b1dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351672"
---
# <a name="ygridorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="73612-103">YGridOrigin 单元格 ( &amp; "标尺网格" 部分)</span><span class="sxs-lookup"><span data-stu-id="73612-103">YGridOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="73612-104">指定网格的垂直起点。</span><span class="sxs-lookup"><span data-stu-id="73612-104">Specifies the vertical origin of the grid.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="73612-105">注解</span><span class="sxs-lookup"><span data-stu-id="73612-105">Remarks</span></span>

<span data-ttu-id="73612-106">此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "垂直**网格起点**" 选项。</span><span class="sxs-lookup"><span data-stu-id="73612-106">This cell corresponds to the vertical **Grid origin** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="73612-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="73612-107">To get a reference to the YGridOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="73612-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="73612-108">Cell name:</span></span>  <br/> |<span data-ttu-id="73612-109">YGridOrigin</span><span class="sxs-lookup"><span data-stu-id="73612-109">YGridOrigin</span></span>  <br/> |
   
<span data-ttu-id="73612-110">若要从某个程序按索引获取对 YGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="73612-110">To get a reference to the YGridOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="73612-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="73612-111">Section index:</span></span>  <br/> |<span data-ttu-id="73612-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="73612-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="73612-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="73612-113">Row index:</span></span>  <br/> |<span data-ttu-id="73612-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="73612-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="73612-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="73612-115">Cell index:</span></span>  <br/> |<span data-ttu-id="73612-116">**visYGridOrigin**</span><span class="sxs-lookup"><span data-stu-id="73612-116">**visYGridOrigin**</span></span> <br/> |
   

