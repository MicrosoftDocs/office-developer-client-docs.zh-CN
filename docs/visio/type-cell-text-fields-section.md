---
title: Type 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1060
localization_priority: Normal
ms.assetid: 69d64520-9a47-07ca-09c7-d1e5da620348
description: 指定文本域值的数据类型。
ms.openlocfilehash: 91a2d60133d9a39e152656558f168742a5409883
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407982"
---
# <a name="type-cell-text-fields-section"></a><span data-ttu-id="c17ca-103">Type 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="c17ca-103">Type Cell (Text Fields Section)</span></span>

<span data-ttu-id="c17ca-104">指定文本域值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c17ca-104">Specifies a data type for the text field value.</span></span>
  
|<span data-ttu-id="c17ca-105">**值**</span><span class="sxs-lookup"><span data-stu-id="c17ca-105">**Value**</span></span>|<span data-ttu-id="c17ca-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="c17ca-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c17ca-107">0</span><span class="sxs-lookup"><span data-stu-id="c17ca-107">0</span></span>  <br/> |<span data-ttu-id="c17ca-108">字符串。</span><span class="sxs-lookup"><span data-stu-id="c17ca-108">String.</span></span>  <br/> |
|<span data-ttu-id="c17ca-109">2</span><span class="sxs-lookup"><span data-stu-id="c17ca-109">2</span></span>  <br/> |<span data-ttu-id="c17ca-p101">数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="c17ca-p101">Number. Includes date, time, duration, and currency values as well as scalars, dimensions, and angles. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="c17ca-113">5 </span><span class="sxs-lookup"><span data-stu-id="c17ca-113">5</span></span>  <br/> |<span data-ttu-id="c17ca-p102">日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="c17ca-p102">Date or time value. Displays days, months, and years, or seconds, minutes, and hours, or a combined date and time value. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="c17ca-117">6 </span><span class="sxs-lookup"><span data-stu-id="c17ca-117">6</span></span>  <br/> |<span data-ttu-id="c17ca-p103">持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="c17ca-p103">Duration value. Displays elapsed time. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="c17ca-121">7 </span><span class="sxs-lookup"><span data-stu-id="c17ca-121">7</span></span>  <br/> |<span data-ttu-id="c17ca-p104">货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="c17ca-p104">Currency value. Uses the system's current Regional Settings. Specify a format picture in the Format cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c17ca-125">备注</span><span class="sxs-lookup"><span data-stu-id="c17ca-125">Remarks</span></span>

<span data-ttu-id="c17ca-126">您还可以使用"域"对话框设置此单元格的值 (选定形状后，在"插入"选项卡上的"文本"组中，单击"域") 。 </span><span class="sxs-lookup"><span data-stu-id="c17ca-126">You can also set the value of this cell using the **Field** dialog box (with a shape selected, on the **Insert** tab, in the **Text** group, click **Field** ).</span></span> 
  
<span data-ttu-id="c17ca-127">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c17ca-127">To get a reference to the Type cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c17ca-128">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c17ca-128">Cell name:</span></span>  <br/> |<span data-ttu-id="c17ca-129">Fields.Type[ *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="c17ca-129">Fields.Type[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c17ca-130">若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c17ca-130">To get a reference to the Type cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c17ca-131">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c17ca-131">Section index:</span></span>  <br/> |<span data-ttu-id="c17ca-132">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="c17ca-132">**visSectionTextField**</span></span> <br/> |
|<span data-ttu-id="c17ca-133">行索引：</span><span class="sxs-lookup"><span data-stu-id="c17ca-133">Row index:</span></span>  <br/> |<span data-ttu-id="c17ca-134">**visRowField**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="c17ca-134">**visRowField** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="c17ca-135">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c17ca-135">Cell index:</span></span>  <br/> |<span data-ttu-id="c17ca-136">**visFieldType**</span><span class="sxs-lookup"><span data-stu-id="c17ca-136">**visFieldType**</span></span> <br/> |
   

