---
title: Type 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1055
localization_priority: Normal
ms.assetid: 1e24a906-83ce-32d2-5d7b-ba6dd6eea2d3
description: 指定形状数据值的数据类型。
ms.openlocfilehash: c2d38b521a8597a4582a4145ad808b0c0e26ff0a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406246"
---
# <a name="type-cell-shape-data-section"></a><span data-ttu-id="ed4b2-103">Type 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="ed4b2-103">Type Cell (Shape Data Section)</span></span>

<span data-ttu-id="ed4b2-104">指定形状数据值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-104">Specifies a data type for the shape data value.</span></span>
  
|<span data-ttu-id="ed4b2-105">**值**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-105">**Value**</span></span>|<span data-ttu-id="ed4b2-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-106">**Description**</span></span>|<span data-ttu-id="ed4b2-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed4b2-108">0</span><span class="sxs-lookup"><span data-stu-id="ed4b2-108">0</span></span>  <br/> |<span data-ttu-id="ed4b2-p101">字符串。此为默认值。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p101">String. This is the default.</span></span>  <br/> |<span data-ttu-id="ed4b2-111">**visPropTypeString**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-111">**visPropTypeString**</span></span> <br/> |
|<span data-ttu-id="ed4b2-112">1</span><span class="sxs-lookup"><span data-stu-id="ed4b2-112">1</span></span>  <br/> |<span data-ttu-id="ed4b2-p102">固定列表。在 **“定义形状数据”** 对话框中的下拉组合框中显示列表项。在 Format 单元格中指定列表项。用户只能从该列表中选择一项。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p102">Fixed list. Displays the list items in a drop-down combo box in the **Define Shape Data** dialog box. Specify the list items in the Format cell. Users can select only one item from the list.  </span></span><br/> |<span data-ttu-id="ed4b2-117">**visPropTypeListFix**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-117">**visPropTypeListFix**</span></span> <br/> |
|<span data-ttu-id="ed4b2-118">2</span><span class="sxs-lookup"><span data-stu-id="ed4b2-118">2</span></span>  <br/> |<span data-ttu-id="ed4b2-p103">数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p103">Number. Includes date, time, duration, and currency values as well as scalars, dimensions, and angles. Specify a format picture in the Format cell.</span></span>  <br/> |<span data-ttu-id="ed4b2-122">**visPropTypeNumber**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-122">**visPropTypeNumber**</span></span> <br/> |
|<span data-ttu-id="ed4b2-123">3</span><span class="sxs-lookup"><span data-stu-id="ed4b2-123">3</span></span>  <br/> |<span data-ttu-id="ed4b2-p104">布尔值。显示 FALSE 和 TRUE 项，这两项正是用户可以从 **“定义形状数据”** 对话框中的下拉列表框中选择的项。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p104">Boolean. Displays FALSE and TRUE as items users can select from a drop-down list box in the **Define Shape Data** dialog box.  </span></span><br/> |<span data-ttu-id="ed4b2-126">**visPropTypeBool**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-126">**visPropTypeBool**</span></span> <br/> |
|<span data-ttu-id="ed4b2-127">4 </span><span class="sxs-lookup"><span data-stu-id="ed4b2-127">4</span></span>  <br/> |<span data-ttu-id="ed4b2-p105">变量列表。在 **“定义形状数据”** 对话框中的下拉组合框中显示列表项。在 Format 单元格中指定列表项。用户可以选择列表项或在 Format 单元格中输入添加到当前列表中的新项。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p105">Variable list. Displays the list items in a drop-down combo box in the **Define Shape Data** dialog box. Specify the list items in the Format cell. Users can select a list item or enter a new item that is added to the current list in the Format cell.  </span></span><br/> |<span data-ttu-id="ed4b2-132">**visPropTypeListVar**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-132">**visPropTypeListVar**</span></span> <br/> |
|<span data-ttu-id="ed4b2-133">5 </span><span class="sxs-lookup"><span data-stu-id="ed4b2-133">5</span></span>  <br/> |<span data-ttu-id="ed4b2-p106">日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p106">Date or time value. Displays days, months, and years, or seconds, minutes, and hours, or a combined date and time value. Specify a format picture in the Format cell.</span></span>  <br/> |<span data-ttu-id="ed4b2-137">**visPropTypeDate**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-137">**visPropTypeDate**</span></span> <br/> |
|<span data-ttu-id="ed4b2-138">6 </span><span class="sxs-lookup"><span data-stu-id="ed4b2-138">6</span></span>  <br/> |<span data-ttu-id="ed4b2-p107">持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p107">Duration value. Displays elapsed time. Specify a format picture in the Format cell.</span></span>  <br/> |<span data-ttu-id="ed4b2-142">**visPropTypeDuration**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-142">**visPropTypeDuration**</span></span> <br/> |
|<span data-ttu-id="ed4b2-143">7 </span><span class="sxs-lookup"><span data-stu-id="ed4b2-143">7</span></span>  <br/> |<span data-ttu-id="ed4b2-p108">货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="ed4b2-p108">Currency value. Uses the system's current Regional Settings. Specify a format picture in the Format cell.</span></span>  <br/> |<span data-ttu-id="ed4b2-147">**visPropTypeCurrency**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-147">**visPropTypeCurrency**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed4b2-148">备注</span><span class="sxs-lookup"><span data-stu-id="ed4b2-148">Remarks</span></span>

<span data-ttu-id="ed4b2-149">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-149">To get a reference to the Type cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ed4b2-150">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-150">Cell name:</span></span>  <br/> |<span data-ttu-id="ed4b2-151">Prop. *Name*  .键入其中 Prop。  *Name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="ed4b2-151">Prop. *Name*  .Type where Prop.  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="ed4b2-152">若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-152">To get a reference to the Type cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ed4b2-153">内容索引：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-153">Section index:</span></span>  <br/> |<span data-ttu-id="ed4b2-154">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-154">**visSectionProp**</span></span> <br/> |
|<span data-ttu-id="ed4b2-155">行索引：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-155">Row index:</span></span>  <br/> |<span data-ttu-id="ed4b2-156">**visRowProp**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="ed4b2-156">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="ed4b2-157">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="ed4b2-157">Cell index:</span></span>  <br/> |<span data-ttu-id="ed4b2-158">**visCustPropsType**</span><span class="sxs-lookup"><span data-stu-id="ed4b2-158">**visCustPropsType**</span></span> <br/> |
   

