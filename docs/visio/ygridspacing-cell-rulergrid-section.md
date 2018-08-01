---
title: YGridSpacing 单元格（“Ruler &amp; Grid”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1210
localization_priority: Normal
ms.assetid: 30766e13-c90d-62fc-9c98-35ad7b0b4056
description: 指定固定网格中垂直线条间的距离 (YGridDensity = 0)。
ms.openlocfilehash: 638479719ee0649bf271403249e2cde2ddccf09c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781717"
---
# <a name="ygridspacing-cell-ruler-amp-grid-section"></a><span data-ttu-id="240ac-103">YGridSpacing 单元格（“Ruler &amp; Grid”部分）</span><span class="sxs-lookup"><span data-stu-id="240ac-103">YGridSpacing Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="240ac-104">指定固定网格中垂直线条间的距离 (YGridDensity = 0)。</span><span class="sxs-lookup"><span data-stu-id="240ac-104">Specifies the distance between vertical lines in a fixed grid (YGridDensity = 0).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="240ac-105">注解</span><span class="sxs-lookup"><span data-stu-id="240ac-105">Remarks</span></span>

<span data-ttu-id="240ac-106">对应于垂直**最小间距**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="240ac-106">Corresponds to the vertical **Minimum spacing** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="240ac-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridSpacing 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="240ac-107">To get a reference to the YGridSpacing cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="240ac-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="240ac-108">Cell name:</span></span>  <br/> |<span data-ttu-id="240ac-109">YGridSpacing</span><span class="sxs-lookup"><span data-stu-id="240ac-109">YGridSpacing</span></span>  <br/> |
   
<span data-ttu-id="240ac-110">若要从某个程序按索引获取对 YGridSpacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="240ac-110">To get a reference to the YGridSpacing cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="240ac-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="240ac-111">Section index:</span></span>  <br/> |<span data-ttu-id="240ac-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="240ac-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="240ac-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="240ac-113">Row index:</span></span>  <br/> |<span data-ttu-id="240ac-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="240ac-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="240ac-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="240ac-115">Cell index:</span></span>  <br/> |<span data-ttu-id="240ac-116">**visYGridSpacing**</span><span class="sxs-lookup"><span data-stu-id="240ac-116">**visYGridSpacing**</span></span> <br/> |
   

