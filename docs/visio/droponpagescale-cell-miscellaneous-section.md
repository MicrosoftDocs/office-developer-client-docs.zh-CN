---
title: DropOnPageScale 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60042
localization_priority: Normal
ms.assetid: 8927f811-7d8e-ed54-9eec-b86a781168dd
ms.openlocfilehash: a586cca497e1ba04848142917a84c3aa8a25d081
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780141"
---
# <a name="droponpagescale-cell-miscellaneous-section"></a><span data-ttu-id="39421-102">DropOnPageScale 单元格（“Miscellaneous”部分）</span><span class="sxs-lookup"><span data-stu-id="39421-102">DropOnPageScale Cell (Miscellaneous Section)</span></span>

<span data-ttu-id="39421-103">包含形状在绘图页上放下时缩放比例的百分比。</span><span class="sxs-lookup"><span data-stu-id="39421-103">Contains the percentage by which a shape is scaled when dropped on the drawing page.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="39421-104">注释</span><span class="sxs-lookup"><span data-stu-id="39421-104">Remarks</span></span>

<span data-ttu-id="39421-105">在下面两种情况下，Visio 将缩放形状，以使其适当地显示在绘图页上：</span><span class="sxs-lookup"><span data-stu-id="39421-105">In the following two cases, Visio scales shapes so that they appear appropriately on the drawing page:</span></span>
  
- <span data-ttu-id="39421-106">将不可测量的形状放在有比例的绘图上时。</span><span class="sxs-lookup"><span data-stu-id="39421-106">When unmeasured shapes are dropped onto scaled drawings.</span></span>
    
- <span data-ttu-id="39421-107">测量的形状放在上时无比例的绘图。</span><span class="sxs-lookup"><span data-stu-id="39421-107">When measured shapes are dropped onto unscaled drawings.</span></span>
    
<span data-ttu-id="39421-108">DropOnPageScale 单元格中的百分比指示 Visio 缩放形状，或者 up 因子 (\>100) 或向下 (\<100)。</span><span class="sxs-lookup"><span data-stu-id="39421-108">The percentage in the DropOnPageScale cell indicates the factor by which Visio scaled the shape, either up (\>100) or down (\<100).</span></span> <span data-ttu-id="39421-109">计算硬编码值时，您可以使用此号码作为因素。</span><span class="sxs-lookup"><span data-stu-id="39421-109">You can use this number as a factor when calculating hard-coded values.</span></span> 
  
<span data-ttu-id="39421-110">对于有比例绘图上的可测量形状或无比例绘图上的不可测量形状，此值是 100%。</span><span class="sxs-lookup"><span data-stu-id="39421-110">This value is 100% for measured shapes on scaled drawings or unmeasured shapes on unscaled drawings.</span></span> 
  
<span data-ttu-id="39421-111">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DropOnPageScale 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="39421-111">To get a reference to the DropOnPageScale cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="39421-112">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="39421-112">Cell name:</span></span>  <br/> | <span data-ttu-id="39421-113">DropOnPageScale</span><span class="sxs-lookup"><span data-stu-id="39421-113">DropOnPageScale</span></span>  <br/> |
   
<span data-ttu-id="39421-114">要从某个程序按索引获取对 DropOnPageScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="39421-114">To get a reference to the DropOnPageScale cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="39421-115">内容索引：</span><span class="sxs-lookup"><span data-stu-id="39421-115">Section index:</span></span>  <br/> |<span data-ttu-id="39421-116">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="39421-116">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="39421-117">行索引：</span><span class="sxs-lookup"><span data-stu-id="39421-117">Row index:</span></span>  <br/> |<span data-ttu-id="39421-118">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="39421-118">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="39421-119">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="39421-119">Cell index:</span></span>  <br/> |<span data-ttu-id="39421-120">**visObjDropOnPageScale**</span><span class="sxs-lookup"><span data-stu-id="39421-120">**visObjDropOnPageScale**</span></span> <br/> |
   

