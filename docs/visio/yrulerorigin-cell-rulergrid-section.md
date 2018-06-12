---
title: YRulerOrigin 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1220
localization_priority: Normal
ms.assetid: 5d21b64f-a559-76ef-06df-d24c048cc6ef
description: 指定页面 y 轴标尺上的零点。
ms.openlocfilehash: 143f372d66ee25e90608a9b2eb252a99e7bcc52f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781719"
---
# <a name="yrulerorigin-cell-ruler-amp-grid-section"></a><span data-ttu-id="85b4c-103">YRulerOrigin 单元格 (标尺&amp;网格部分)</span><span class="sxs-lookup"><span data-stu-id="85b4c-103">YRulerOrigin Cell (Ruler &amp; Grid Section)</span></span>

<span data-ttu-id="85b4c-104">指定页面 y 轴标尺上的零点。</span><span class="sxs-lookup"><span data-stu-id="85b4c-104">Specifies the zero point on the y-axis ruler for the page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="85b4c-105">备注</span><span class="sxs-lookup"><span data-stu-id="85b4c-105">Remarks</span></span>

<span data-ttu-id="85b4c-106">此单元格对应于在垂直**标尺零点**选项**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。</span><span class="sxs-lookup"><span data-stu-id="85b4c-106">This cell corresponds to the vertical **Ruler zero** option in the **Ruler &amp; Grid** dialog box (on the **View** tab, click the **Show** arrow).</span></span> 
  
<span data-ttu-id="85b4c-107">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 YRulerOrigin 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="85b4c-107">To get a reference to the YRulerOrigin cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="85b4c-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="85b4c-108">Cell name:</span></span>  <br/> |<span data-ttu-id="85b4c-109">YRulerOrigin</span><span class="sxs-lookup"><span data-stu-id="85b4c-109">YRulerOrigin</span></span>  <br/> |
   
<span data-ttu-id="85b4c-110">若要从某个程序按索引获取对 YRulerOrigin 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="85b4c-110">To get a reference to the YRulerOrigin cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="85b4c-111">内容索引：</span><span class="sxs-lookup"><span data-stu-id="85b4c-111">Section index:</span></span>  <br/> |<span data-ttu-id="85b4c-112">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="85b4c-112">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="85b4c-113">行索引：</span><span class="sxs-lookup"><span data-stu-id="85b4c-113">Row index:</span></span>  <br/> |<span data-ttu-id="85b4c-114">**visRowRulerGrid**</span><span class="sxs-lookup"><span data-stu-id="85b4c-114">**visRowRulerGrid**</span></span> <br/> |
|<span data-ttu-id="85b4c-115">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="85b4c-115">Cell index:</span></span>  <br/> |<span data-ttu-id="85b4c-116">**visYRulerOrigin**</span><span class="sxs-lookup"><span data-stu-id="85b4c-116">**visYRulerOrigin**</span></span> <br/> |
   

