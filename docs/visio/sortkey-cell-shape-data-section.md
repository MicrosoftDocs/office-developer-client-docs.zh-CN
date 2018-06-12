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
description: 影响的顺序排列形状数据窗口中的项目的字符串求值。
ms.openlocfilehash: 1dbc093f2cee509531b8148563fbdb1a777a349f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781420"
---
# <a name="sortkey-cell-shape-data-section"></a><span data-ttu-id="5b452-103">SortKey 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="5b452-103">SortKey Cell (Shape Data Section)</span></span>

<span data-ttu-id="5b452-104">影响的顺序排列**形状数据**窗口中的项目的字符串求值。</span><span class="sxs-lookup"><span data-stu-id="5b452-104">Evaluates to a string that influences the order in which items in the **Shape Data** window are listed.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5b452-105">备注</span><span class="sxs-lookup"><span data-stu-id="5b452-105">Remarks</span></span>

<span data-ttu-id="5b452-106">用于比较 SortKey 值计算是特定于区域设置和区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5b452-106">The calculation used to compare SortKey values is locale-specific and case insensitive.</span></span> <span data-ttu-id="5b452-107">如果 SortKey 值相等，形状数据行顺序列出。</span><span class="sxs-lookup"><span data-stu-id="5b452-107">If SortKey values are equal, the shape data is listed in row order.</span></span> <span data-ttu-id="5b452-108">没有排序关键字的形状数据列包含排序关键字的形状数据之后。</span><span class="sxs-lookup"><span data-stu-id="5b452-108">Shape data that have no sort key are listed after shape data that contain a sort key.</span></span>
  
<span data-ttu-id="5b452-109">以下是使用排序关键字的顺序**形状数据**窗口中显示的形状数据的示例： 项目编号、 数量、 价格。</span><span class="sxs-lookup"><span data-stu-id="5b452-109">Following is an example of using sort keys to display the shape data in the **Shape Data** window in the order: Item Number, Quantity, Price.</span></span> 
  
 <span data-ttu-id="5b452-110">*Label、、 行*和*SortKey*引用单元格的形状数据行。</span><span class="sxs-lookup"><span data-stu-id="5b452-110">*Row, Label,*  and  *SortKey*  refer to cells in the shape data row.</span></span> <span data-ttu-id="5b452-111">在这种情况下，已命名的形状数据行。</span><span class="sxs-lookup"><span data-stu-id="5b452-111">In this case, the shape data rows have been named.</span></span> 
  
|<span data-ttu-id="5b452-112">**Row**</span><span class="sxs-lookup"><span data-stu-id="5b452-112">**Row**</span></span>|<span data-ttu-id="5b452-113">**标签**</span><span class="sxs-lookup"><span data-stu-id="5b452-113">**Label**</span></span>|<span data-ttu-id="5b452-114">**SortKey**</span><span class="sxs-lookup"><span data-stu-id="5b452-114">**SortKey**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="5b452-115">Prop.Item</span><span class="sxs-lookup"><span data-stu-id="5b452-115">Prop.Item</span></span>  <br/> | <span data-ttu-id="5b452-116">项目编号</span><span class="sxs-lookup"><span data-stu-id="5b452-116">Item Number</span></span>  <br/> | <span data-ttu-id="5b452-117">1</span><span class="sxs-lookup"><span data-stu-id="5b452-117">1</span></span>  <br/> |
| <span data-ttu-id="5b452-118">Prop.Price</span><span class="sxs-lookup"><span data-stu-id="5b452-118">Prop.Price</span></span>  <br/> | <span data-ttu-id="5b452-119">价格</span><span class="sxs-lookup"><span data-stu-id="5b452-119">Price</span></span>  <br/> | <span data-ttu-id="5b452-120">3</span><span class="sxs-lookup"><span data-stu-id="5b452-120">3</span></span>  <br/> |
| <span data-ttu-id="5b452-121">Prop.Quan</span><span class="sxs-lookup"><span data-stu-id="5b452-121">Prop.Quan</span></span>  <br/> | <span data-ttu-id="5b452-122">数量</span><span class="sxs-lookup"><span data-stu-id="5b452-122">Quantity</span></span>  <br/> | <span data-ttu-id="5b452-123">2</span><span class="sxs-lookup"><span data-stu-id="5b452-123">2</span></span>  <br/> |
   
<span data-ttu-id="5b452-124">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 SortKey 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="5b452-124">To get a reference to the SortKey cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5b452-125">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5b452-125">Cell name:</span></span>  <br/> | <span data-ttu-id="5b452-126">属性。 *名称*。SortKey 其中属性。 *Name*是自定义属性行的名称</span><span class="sxs-lookup"><span data-stu-id="5b452-126">Prop.  *Name*  .SortKey where Prop.  *Name*  is the name of the custom property row</span></span>  <br/> |
   
<span data-ttu-id="5b452-127">若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5b452-127">To get a reference to the SortKey cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5b452-128">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5b452-128">Section index:</span></span>  <br/> |<span data-ttu-id="5b452-129">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="5b452-129">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="5b452-130">行索引：</span><span class="sxs-lookup"><span data-stu-id="5b452-130">Row index:</span></span>  <br/> |<span data-ttu-id="5b452-131">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="5b452-131">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5b452-132">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5b452-132">Cell index:</span></span>  <br/> |<span data-ttu-id="5b452-133">**visCustPropsSortKey**</span><span class="sxs-lookup"><span data-stu-id="5b452-133">**visCustPropsSortKey**</span></span> <br/> |
   

