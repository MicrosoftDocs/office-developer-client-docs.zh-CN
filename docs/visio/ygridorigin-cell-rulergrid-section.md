---
title: "\"YGridOrigin 单元格 (&amp; Ruler Grid\"内容) "
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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404489"
---
# <a name="ygridorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="9314e-103">"YGridOrigin 单元格 (&amp; Ruler Grid"内容) </span><span class="sxs-lookup"><span data-stu-id="9314e-103">YGridOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="9314e-104">指定网格的垂直起点。</span><span class="sxs-lookup"><span data-stu-id="9314e-104">Specifies the vertical origin of the grid.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9314e-105">备注</span><span class="sxs-lookup"><span data-stu-id="9314e-105">Remarks</span></span>

<span data-ttu-id="9314e-106">此单元格对应于"视图"选项卡上"标尺网格 (**对话框中** 的垂直网格原点选项，单击"显示") 。  **&amp;**</span><span class="sxs-lookup"><span data-stu-id="9314e-106">This cell corresponds to the vertical **Grid origin** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="9314e-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9314e-107">To get a reference to the YGridOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9314e-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9314e-108">Cell name:</span></span>  <br/> |<span data-ttu-id="9314e-109">YGridOrigin</span><span class="sxs-lookup"><span data-stu-id="9314e-109">YGridOrigin</span></span>  <br/> |
   
<span data-ttu-id="9314e-110">若要从某个程序按索引获取对 YGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9314e-110">To get a reference to the YGridOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9314e-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9314e-111">Section index:</span></span>  <br/> |<span data-ttu-id="9314e-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="9314e-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="9314e-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="9314e-113">Row index:</span></span>  <br/> |<span data-ttu-id="9314e-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="9314e-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="9314e-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9314e-115">Cell index:</span></span>  <br/> |<span data-ttu-id="9314e-116">**visYGridOrigin**</span><span class="sxs-lookup"><span data-stu-id="9314e-116">**visYGridOrigin**</span></span> <br/> |
   

