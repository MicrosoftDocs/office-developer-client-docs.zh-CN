---
title: YGridOrigin 单元格（“Ruler &amp; Grid”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1205
localization_priority: Normal
ms.assetid: eeec59f8-f301-5639-ffd6-8a36b2bf9c8f
description: 指定网格的垂直起点。
ms.openlocfilehash: 2d914fc15df8a100066ad17a2e35001fe8a4d587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781709"
---
# <a name="ygridorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="8d0c8-103">YGridOrigin 单元格（“Ruler &amp; Grid”部分）</span><span class="sxs-lookup"><span data-stu-id="8d0c8-103">YGridOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="8d0c8-104">指定网格的垂直起点。</span><span class="sxs-lookup"><span data-stu-id="8d0c8-104">Specifies the vertical origin of the grid.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8d0c8-105">注解</span><span class="sxs-lookup"><span data-stu-id="8d0c8-105">Remarks</span></span>

<span data-ttu-id="8d0c8-106">此单元格对应于垂直**网格原点**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="8d0c8-106">This cell corresponds to the vertical **Grid origin** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="8d0c8-107">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-107">To get a reference to the YGridOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8d0c8-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-108">Cell name:</span></span>  <br/> |<span data-ttu-id="8d0c8-109">YGridOrigin</span><span class="sxs-lookup"><span data-stu-id="8d0c8-109">YGridOrigin</span></span>  <br/> |
   
<span data-ttu-id="8d0c8-110">若要从某个程序按索引获取对 YGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-110">To get a reference to the YGridOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8d0c8-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-111">Section index:</span></span>  <br/> |<span data-ttu-id="8d0c8-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="8d0c8-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="8d0c8-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-113">Row index:</span></span>  <br/> |<span data-ttu-id="8d0c8-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="8d0c8-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="8d0c8-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="8d0c8-115">Cell index:</span></span>  <br/> |<span data-ttu-id="8d0c8-116">**visYGridOrigin**</span><span class="sxs-lookup"><span data-stu-id="8d0c8-116">**visYGridOrigin**</span></span> <br/> |
   

