---
title: XGridOrigin 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1155
localization_priority: Normal
ms.assetid: 2b1a8902-b1d4-c3d9-8c9f-1a28fddacc59
description: 指定网格原点的水平坐标。
ms.openlocfilehash: 0cc6ff10f9bb4ba7ee0a13a48cb55b7dcd0fa013
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781691"
---
# <a name="xgridorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="98c64-103">XGridOrigin 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="98c64-103">XGridOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="98c64-104">指定网格原点的水平坐标。</span><span class="sxs-lookup"><span data-stu-id="98c64-104">Specifies the horizontal coordinate of the grid origin.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="98c64-105">注解</span><span class="sxs-lookup"><span data-stu-id="98c64-105">Remarks</span></span>

<span data-ttu-id="98c64-106">此单元格对应于水平**网格原点**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头。</span><span class="sxs-lookup"><span data-stu-id="98c64-106">This cell corresponds to the horizontal **Grid origin** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow.</span></span> 
  
<span data-ttu-id="98c64-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XGridOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="98c64-107">To get a reference to the XGridOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98c64-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="98c64-108">Cell name:</span></span>  <br/> |<span data-ttu-id="98c64-109">XGridOrigin</span><span class="sxs-lookup"><span data-stu-id="98c64-109">XGridOrigin</span></span>  <br/> |
   
<span data-ttu-id="98c64-110">若要从某个程序按索引获取对 XGridOrigin 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="98c64-110">To get a reference to the XGridOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="98c64-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="98c64-111">Section index:</span></span>  <br/> |<span data-ttu-id="98c64-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="98c64-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="98c64-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="98c64-113">Row index:</span></span>  <br/> |<span data-ttu-id="98c64-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="98c64-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="98c64-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="98c64-115">Cell index:</span></span>  <br/> |<span data-ttu-id="98c64-116">**visXGridOrigin**</span><span class="sxs-lookup"><span data-stu-id="98c64-116">**visXGridOrigin**</span></span> <br/> |
   

