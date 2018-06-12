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
ms.openlocfilehash: 68bfa8a84adb0d46d9621e6fc5383f4b6606f542
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781574"
---
# <a name="type-cell-text-fields-section"></a><span data-ttu-id="4052e-103">Type 单元格（“Text Fields”内容）</span><span class="sxs-lookup"><span data-stu-id="4052e-103">Type Cell (Text Fields Section)</span></span>

<span data-ttu-id="4052e-104">指定文本域值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4052e-104">Specifies a data type for the text field value.</span></span>
  
|<span data-ttu-id="4052e-105">**值**</span><span class="sxs-lookup"><span data-stu-id="4052e-105">**Value**</span></span>|<span data-ttu-id="4052e-106">**说明**</span><span class="sxs-lookup"><span data-stu-id="4052e-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4052e-107">0</span><span class="sxs-lookup"><span data-stu-id="4052e-107">0</span></span>  <br/> |<span data-ttu-id="4052e-108">字符串。</span><span class="sxs-lookup"><span data-stu-id="4052e-108">String.</span></span>  <br/> |
|<span data-ttu-id="4052e-109">2</span><span class="sxs-lookup"><span data-stu-id="4052e-109">2</span></span>  <br/> |<span data-ttu-id="4052e-p101">数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="4052e-p101">Number. Includes date, time, duration, and currency values as well as scalars, dimensions, and angles. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="4052e-113">5</span><span class="sxs-lookup"><span data-stu-id="4052e-113">5</span></span>  <br/> |<span data-ttu-id="4052e-p102">日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="4052e-p102">Date or time value. Displays days, months, and years, or seconds, minutes, and hours, or a combined date and time value. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="4052e-117">6</span><span class="sxs-lookup"><span data-stu-id="4052e-117">6</span></span>  <br/> |<span data-ttu-id="4052e-p103">持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="4052e-p103">Duration value. Displays elapsed time. Specify a format picture in the Format cell.</span></span>  <br/> |
|<span data-ttu-id="4052e-121">7</span><span class="sxs-lookup"><span data-stu-id="4052e-121">7</span></span>  <br/> |<span data-ttu-id="4052e-p104">货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。</span><span class="sxs-lookup"><span data-stu-id="4052e-p104">Currency value. Uses the system's current Regional Settings. Specify a format picture in the Format cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4052e-125">注解</span><span class="sxs-lookup"><span data-stu-id="4052e-125">Remarks</span></span>

<span data-ttu-id="4052e-126">您还可以设置此单元格，使用**字段**对话框中的值 （与选定形状，在**插入**选项卡中的**文本**组中，单击**域**）。</span><span class="sxs-lookup"><span data-stu-id="4052e-126">You can also set the value of this cell using the **Field** dialog box (with a shape selected, on the **Insert** tab, in the **Text** group, click **Field** ).</span></span> 
  
<span data-ttu-id="4052e-127">若要获取对 Type 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="4052e-127">To get a reference to the Type cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4052e-128">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="4052e-128">Cell name:</span></span>  <br/> |<span data-ttu-id="4052e-129">Fields.Type [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="4052e-129">Fields.Type[ *i*  ] where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="4052e-130">若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="4052e-130">To get a reference to the Type cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4052e-131">内容索引：</span><span class="sxs-lookup"><span data-stu-id="4052e-131">Section index:</span></span>  <br/> |<span data-ttu-id="4052e-132">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="4052e-132">**visSectionTextField**</span></span> <br/> |
|<span data-ttu-id="4052e-133">行索引：</span><span class="sxs-lookup"><span data-stu-id="4052e-133">Row index:</span></span>  <br/> |<span data-ttu-id="4052e-134">**visRowField** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="4052e-134">**visRowField** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="4052e-135">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="4052e-135">Cell index:</span></span>  <br/> |<span data-ttu-id="4052e-136">**visFieldType**</span><span class="sxs-lookup"><span data-stu-id="4052e-136">**visFieldType**</span></span> <br/> |
   

