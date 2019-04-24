---
title: SortKey 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251345
localization_priority: Normal
ms.assetid: 67fa5389-f0b9-a9db-8d19-9b16e256dfa3
description: 对影响在“形状数据”窗口中列出的项目的顺序的字符串求值。
ms.openlocfilehash: d166ea18a36f6a4101b8933fce804be2243954bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335180"
---
# <a name="sortkey-cell-shape-data-section"></a><span data-ttu-id="266c8-103">SortKey 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="266c8-103">SortKey Cell (Shape Data Section)</span></span>

<span data-ttu-id="266c8-104">对影响在 **“形状数据”** 窗口中列出的项目的顺序的字符串求值。</span><span class="sxs-lookup"><span data-stu-id="266c8-104">Evaluates to a string that influences the order in which items in the **Shape Data** window are listed.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="266c8-105">注解</span><span class="sxs-lookup"><span data-stu-id="266c8-105">Remarks</span></span>

<span data-ttu-id="266c8-106">用于比较排序关键字值的计算视具体区域设置而定，并且不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="266c8-106">The calculation used to compare SortKey values is locale-specific and case insensitive.</span></span> <span data-ttu-id="266c8-107">如果排序关键字值相等，形状数据将按行顺序列出。</span><span class="sxs-lookup"><span data-stu-id="266c8-107">If SortKey values are equal, the shape data is listed in row order.</span></span> <span data-ttu-id="266c8-108">没有排序关键字的形状数据将列在包含排序关键字的形状数据之后。</span><span class="sxs-lookup"><span data-stu-id="266c8-108">Shape data that have no sort key are listed after shape data that contain a sort key.</span></span>
  
<span data-ttu-id="266c8-109">在下面的示例中，使用排序关键字在 **“形状数据”** 窗口中显示形状数据，显示顺序为：项目编号、数量、价格。</span><span class="sxs-lookup"><span data-stu-id="266c8-109">Following is an example of using sort keys to display the shape data in the **Shape Data** window in the order: Item Number, Quantity, Price.</span></span> 
  
 <span data-ttu-id="266c8-110">*行、标签*和*SortKey*引用形状数据行中的单元格。</span><span class="sxs-lookup"><span data-stu-id="266c8-110">*Row, Label,*  and  *SortKey*  refer to cells in the shape data row.</span></span> <span data-ttu-id="266c8-111">在此例中，形状数据行已命名。</span><span class="sxs-lookup"><span data-stu-id="266c8-111">In this case, the shape data rows have been named.</span></span> 
  
|<span data-ttu-id="266c8-112">**行**</span><span class="sxs-lookup"><span data-stu-id="266c8-112">**Row**</span></span>|<span data-ttu-id="266c8-113">**Label**</span><span class="sxs-lookup"><span data-stu-id="266c8-113">**Label**</span></span>|<span data-ttu-id="266c8-114">**关键字**</span><span class="sxs-lookup"><span data-stu-id="266c8-114">**SortKey**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="266c8-115">项</span><span class="sxs-lookup"><span data-stu-id="266c8-115">Prop.Item</span></span>  <br/> | <span data-ttu-id="266c8-116">项目编号</span><span class="sxs-lookup"><span data-stu-id="266c8-116">Item Number</span></span>  <br/> | <span data-ttu-id="266c8-117">1</span><span class="sxs-lookup"><span data-stu-id="266c8-117">1</span></span>  <br/> |
| <span data-ttu-id="266c8-118">价值。价格</span><span class="sxs-lookup"><span data-stu-id="266c8-118">Prop.Price</span></span>  <br/> | <span data-ttu-id="266c8-119">价格</span><span class="sxs-lookup"><span data-stu-id="266c8-119">Price</span></span>  <br/> | <span data-ttu-id="266c8-120">第三章</span><span class="sxs-lookup"><span data-stu-id="266c8-120">3</span></span>  <br/> |
| <span data-ttu-id="266c8-121">Quan</span><span class="sxs-lookup"><span data-stu-id="266c8-121">Prop.Quan</span></span>  <br/> | <span data-ttu-id="266c8-122">数量</span><span class="sxs-lookup"><span data-stu-id="266c8-122">Quantity</span></span>  <br/> | <span data-ttu-id="266c8-123">双面</span><span class="sxs-lookup"><span data-stu-id="266c8-123">2</span></span>  <br/> |
   
<span data-ttu-id="266c8-124">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="266c8-124">To get a reference to the SortKey cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="266c8-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="266c8-125">Cell name:</span></span>  <br/> | <span data-ttu-id="266c8-126">片. *名称*。在其中的 "关键字"。 *name*是自定义属性行的名称</span><span class="sxs-lookup"><span data-stu-id="266c8-126">Prop.  *Name*  .SortKey where Prop.  *Name*  is the name of the custom property row</span></span>  <br/> |
   
<span data-ttu-id="266c8-127">若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="266c8-127">To get a reference to the SortKey cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="266c8-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="266c8-128">Section index:</span></span>  <br/> |<span data-ttu-id="266c8-129">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="266c8-129">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="266c8-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="266c8-130">Row index:</span></span>  <br/> |<span data-ttu-id="266c8-131">**visRowProp** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="266c8-131">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="266c8-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="266c8-132">Cell index:</span></span>  <br/> |<span data-ttu-id="266c8-133">**visCustPropsSortKey**</span><span class="sxs-lookup"><span data-stu-id="266c8-133">**visCustPropsSortKey**</span></span> <br/> |
   

