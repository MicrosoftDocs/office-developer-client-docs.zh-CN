---
title: Format 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm400
localization_priority: Normal
ms.assetid: ab937a00-84c2-6c1c-9080-b7c95ead4f63
description: 指定文本域的格式，该文本字段可以是字符串、数字、日期或时间、持续时间或货币。
ms.openlocfilehash: 767b658a9431dfab23d2df9bcfa6c83b52f48d75
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780310"
---
# <a name="format-cell-text-fields-section"></a><span data-ttu-id="c2797-103">Format 单元格（“Text Fields”部分）</span><span class="sxs-lookup"><span data-stu-id="c2797-103">Format Cell (Text Fields Section)</span></span>

<span data-ttu-id="c2797-104">指定文本域的格式，该文本字段可以是字符串、数字、日期或时间、持续时间或货币。</span><span class="sxs-lookup"><span data-stu-id="c2797-104">Specifies the formatting of a text field that is a string, a number, a date or time, a duration, or a currency.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c2797-105">注解</span><span class="sxs-lookup"><span data-stu-id="c2797-105">Remarks</span></span>

<span data-ttu-id="c2797-p101">如果 Type 单元格的值为 0、2、5、6 或 7（分别代表字符串、数字、日期或时间、持续时间或货币），请为该数据类型指定适当的格式图片。例如，格式图片“# #/4 UU”将数字 12.43 in. 设置为 12 2/4 INCHES 格式。有关指定格式图片的详细信息，请参见[关于格式图片](about-format-pictures.md)。</span><span class="sxs-lookup"><span data-stu-id="c2797-p101">If the value of the Type cell is 0, 2, 5, 6, or 7 (string, number, date or time, duration, or currency, respectively), specify a format picture appropriate for the data type. For example, the format picture "# #/4 UU" formats the number 12.43 in. as 12 2/4 INCHES. For more information about specifying a format picture, see [About format pictures](about-format-pictures.md).</span></span>
  
<span data-ttu-id="c2797-p102">数字 (Type = 2) 可代表尺寸、标量、角度、日期、时间或货币。要确保始终将输入的数字作为日期、时间或货币计算，请在 Format 单元格中使用 DATETIME 或 CY 函数，而不是使用格式图片。</span><span class="sxs-lookup"><span data-stu-id="c2797-p102">A number (Type = 2) can represent a dimension, scalar, angle, date, time, or currency. To ensure that an input number is always evaluated as a date, time, or currency, use the DATETIME or CY function in the Format cell instead of a format picture.</span></span>
  
<span data-ttu-id="c2797-112">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Format 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c2797-112">To get a reference to the Format cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c2797-113">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c2797-113">Cell name:</span></span>  <br/> | <span data-ttu-id="c2797-114">Fields.Format [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="c2797-114">Fields.Format[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c2797-115">要从某个程序按索引获取对 Format 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c2797-115">To get a reference to the Format cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c2797-116">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c2797-116">Section index:</span></span>  <br/> |<span data-ttu-id="c2797-117">**visSectionTextField**</span><span class="sxs-lookup"><span data-stu-id="c2797-117">**visSectionTextField**</span></span> <br/> |
| <span data-ttu-id="c2797-118">行索引：</span><span class="sxs-lookup"><span data-stu-id="c2797-118">Row index:</span></span>  <br/> |<span data-ttu-id="c2797-119">**visRowField** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="c2797-119">**visRowField** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c2797-120">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c2797-120">Cell index:</span></span>  <br/> |<span data-ttu-id="c2797-121">**visFieldFormat**</span><span class="sxs-lookup"><span data-stu-id="c2797-121">**visFieldFormat**</span></span> <br/> |
   

