---
title: 关于日期、时间和持续时间值
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251852
localization_priority: Normal
ms.assetid: b6951a92-f32a-5829-5e07-b277b7934df3
description: 您可以在公式中使用日期、时间和持续时间值执行运算。在 Microsoft Visio 中，日期和时间表达式可以计算为单个值。日期和时间表达式是任何公认的日期和/或时间表达式，或者是对包含日期和/或时间的单元格的引用。这里所指的日期和/或时间包括显示为日期和时间的字符串和数字，以及从函数返回的日期和时间值。
ms.openlocfilehash: 936055ed6d13b75bd0c42c95564046a76082ec0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779613"
---
# <a name="about-date-time-and-duration-values"></a><span data-ttu-id="34b24-106">关于日期、时间和持续时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-106">About Date, Time, and Duration Values</span></span>

<span data-ttu-id="34b24-p102">您可以在公式中使用日期、时间和持续时间值执行运算。在 Microsoft Visio 中，日期和时间表达式可以计算为单个值。日期和时间表达式是任何公认的日期和/或时间表达式，或者是对包含日期和/或时间的单元格的引用。这里所指的日期和/或时间包括显示为日期和时间的字符串和数字，以及从函数返回的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="34b24-p102">You can perform operations in formulas using date, time, and duration values. In Microsoft Visio, a date and time expression can be evaluated as a single value. A date and time expression is any expression commonly recognized as a date and/or time or a reference to a cell containing a date and/or time. This includes strings and numbers that look like a date and time, and date and time values returned from functions.</span></span>
  
<span data-ttu-id="34b24-p103">日期和时间值在 Visio 中以 64 位浮点数在内部存储。小数点左侧的值表示从 1899 年 12 月 30 日至今的天数。小数点右侧的值表示从午夜到现在按分数表示的当日时间，正午用 .5 表示。</span><span class="sxs-lookup"><span data-stu-id="34b24-p103">Date and time values in Visio are stored internally as a 64-bit floating point number. The value to the left of the decimal represents the number of days since December 30, 1899. The value to the right of the decimal represents the fraction of a day since midnight. Noon is represented by .5.</span></span>
  
<span data-ttu-id="34b24-115">要在表达式中使用多个日期和时间（而不是作为单个常数），必须用相应的函数将它们标识为日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="34b24-115">To use dates and times within an expression (rather than as a single constant), you must use the appropriate function to identify them as date and time values.</span></span>
  
## <a name="valid-dates"></a><span data-ttu-id="34b24-116">有效日期</span><span class="sxs-lookup"><span data-stu-id="34b24-116">Valid dates</span></span>

||||
|:-----|:-----|:-----|
| <span data-ttu-id="34b24-117">"2/28"</span><span class="sxs-lookup"><span data-stu-id="34b24-117">"2/28"</span></span>  <br/> | <span data-ttu-id="34b24-118">"28/2/99"</span><span class="sxs-lookup"><span data-stu-id="34b24-118">"2/28/99"</span></span>  <br/> | <span data-ttu-id="34b24-119">"28/2/1999"</span><span class="sxs-lookup"><span data-stu-id="34b24-119">"2/28/1999"</span></span>  <br/> |
| <span data-ttu-id="34b24-120">"2-28"</span><span class="sxs-lookup"><span data-stu-id="34b24-120">"2-28"</span></span>  <br/> | <span data-ttu-id="34b24-121">"2-28-99"</span><span class="sxs-lookup"><span data-stu-id="34b24-121">"2-28-99"</span></span>  <br/> | <span data-ttu-id="34b24-122">"1999 年 2-28"</span><span class="sxs-lookup"><span data-stu-id="34b24-122">"2-28/1999"</span></span>  <br/> |
| <span data-ttu-id="34b24-123">"6 Mar 99"</span><span class="sxs-lookup"><span data-stu-id="34b24-123">"6 Mar 99"</span></span>  <br/> | <span data-ttu-id="34b24-124">"6 Mar"</span><span class="sxs-lookup"><span data-stu-id="34b24-124">"6 Mar"</span></span>  <br/> | <span data-ttu-id="34b24-125">"6 Mar 99"</span><span class="sxs-lookup"><span data-stu-id="34b24-125">"6 Mar 99"</span></span>  <br/> |
| <span data-ttu-id="34b24-126">"1 January 99"</span><span class="sxs-lookup"><span data-stu-id="34b24-126">"1 January 99"</span></span>  <br/> | <span data-ttu-id="34b24-127">"Jan 1, 99"</span><span class="sxs-lookup"><span data-stu-id="34b24-127">"Jan 1, 99"</span></span>  <br/> | <span data-ttu-id="34b24-128">"Jan 1, 1999"</span><span class="sxs-lookup"><span data-stu-id="34b24-128">"Jan 1, 1999"</span></span>  <br/> |
| <span data-ttu-id="34b24-129">"Jan 00"</span><span class="sxs-lookup"><span data-stu-id="34b24-129">"Jan 00"</span></span>  <br/> | <span data-ttu-id="34b24-130">"January, 2000"</span><span class="sxs-lookup"><span data-stu-id="34b24-130">"January, 2000"</span></span>  <br/> | <span data-ttu-id="34b24-131">"Jan 1, 00"</span><span class="sxs-lookup"><span data-stu-id="34b24-131">"Jan 1, 00"</span></span>  <br/> |
   
## <a name="valid-times"></a><span data-ttu-id="34b24-132">有效时间</span><span class="sxs-lookup"><span data-stu-id="34b24-132">Valid times</span></span>

||||
|:-----|:-----|:-----|
| <span data-ttu-id="34b24-133">"3:45"</span><span class="sxs-lookup"><span data-stu-id="34b24-133">"3:45"</span></span>  <br/> | <span data-ttu-id="34b24-134">"3: 45:27"</span><span class="sxs-lookup"><span data-stu-id="34b24-134">"3:45:27"</span></span>  <br/> | <span data-ttu-id="34b24-135">"7a"</span><span class="sxs-lookup"><span data-stu-id="34b24-135">"7a"</span></span>  <br/> |
| <span data-ttu-id="34b24-136">"7 am"</span><span class="sxs-lookup"><span data-stu-id="34b24-136">"7 am"</span></span>  <br/> | <span data-ttu-id="34b24-137">"7 p"</span><span class="sxs-lookup"><span data-stu-id="34b24-137">"7 p"</span></span>  <br/> | <span data-ttu-id="34b24-138">"7:30 PM"</span><span class="sxs-lookup"><span data-stu-id="34b24-138">"7:30 PM"</span></span>  <br/> |
   
## <a name="date-and-time-functions"></a><span data-ttu-id="34b24-139">日期和时间函数</span><span class="sxs-lookup"><span data-stu-id="34b24-139">Date and time functions</span></span>

|<span data-ttu-id="34b24-140">**函数**</span><span class="sxs-lookup"><span data-stu-id="34b24-140">**Function**</span></span>|<span data-ttu-id="34b24-141">**说明**</span><span class="sxs-lookup"><span data-stu-id="34b24-141">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="34b24-142">日期</span><span class="sxs-lookup"><span data-stu-id="34b24-142">DATE</span></span>](date-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-143">将数字转换为日期值。</span><span class="sxs-lookup"><span data-stu-id="34b24-143">Converts numbers to a date value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-144">DATETIME</span><span class="sxs-lookup"><span data-stu-id="34b24-144">DATETIME</span></span>](datetime-function.md) <br/> | <span data-ttu-id="34b24-145">将字符串转换为日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="34b24-145">Converts a string to a date and time value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-146">DATEVALUE</span><span class="sxs-lookup"><span data-stu-id="34b24-146">DATEVALUE</span></span>](datevalue-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-147">将字符串转换为日期值。</span><span class="sxs-lookup"><span data-stu-id="34b24-147">Converts a string to a date value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-148">立即</span><span class="sxs-lookup"><span data-stu-id="34b24-148">NOW</span></span>](now-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-149">以日期和时间值返回当前系统日期。</span><span class="sxs-lookup"><span data-stu-id="34b24-149">Returns the current system date as a date and time value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-150">时间</span><span class="sxs-lookup"><span data-stu-id="34b24-150">TIME</span></span>](time-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-151">将数字转换为时间值。</span><span class="sxs-lookup"><span data-stu-id="34b24-151">Converts numbers to a time value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-152">TIMEVALUE</span><span class="sxs-lookup"><span data-stu-id="34b24-152">TIMEVALUE</span></span>](timevalue-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-153">将字符串转换为时间值。</span><span class="sxs-lookup"><span data-stu-id="34b24-153">Converts a string to a time value.</span></span>  <br/> |
|[<span data-ttu-id="34b24-154">一天</span><span class="sxs-lookup"><span data-stu-id="34b24-154">DAY</span></span>](day-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-155">返回日期和时间表达式中的日期部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-155">Returns the day component in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-156">DAYOFYEAR</span><span class="sxs-lookup"><span data-stu-id="34b24-156">DAYOFYEAR</span></span>](dayofyear-function.md) <br/> | <span data-ttu-id="34b24-157">根据日期和时间表达式，返回从年初至今的天数。</span><span class="sxs-lookup"><span data-stu-id="34b24-157">Returns the sequential day of the year in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-158">小时</span><span class="sxs-lookup"><span data-stu-id="34b24-158">HOUR</span></span>](hour-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-159">返回日期和时间表达式中的小时部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-159">Returns the hours component in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-160">分钟</span><span class="sxs-lookup"><span data-stu-id="34b24-160">MINUTE</span></span>](minute-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-161">返回日期和时间表达式中的分钟部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-161">Returns the minutes component in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-162">月</span><span class="sxs-lookup"><span data-stu-id="34b24-162">MONTH</span></span>](month-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-163">返回日期和时间表达式中的月部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-163">Returns the month component in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-164">第二个</span><span class="sxs-lookup"><span data-stu-id="34b24-164">SECOND</span></span>](second-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-165">返回日期和时间表达式中的秒部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-165">Returns the seconds component in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-166">WEEKDAY</span><span class="sxs-lookup"><span data-stu-id="34b24-166">WEEKDAY</span></span>](weekday-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-167">返回日期和时间表达式中一个星期中的第几天。</span><span class="sxs-lookup"><span data-stu-id="34b24-167">Returns the number of the weekday in a date and time expression.</span></span>  <br/> |
|[<span data-ttu-id="34b24-168">年</span><span class="sxs-lookup"><span data-stu-id="34b24-168">YEAR</span></span>](year-function-visioshapesheet.md) <br/> | <span data-ttu-id="34b24-169">返回日期和时间表达式中的年部分。</span><span class="sxs-lookup"><span data-stu-id="34b24-169">Returns the year component in a date and time expression.</span></span>  <br/> |
   
## <a name="duration"></a><span data-ttu-id="34b24-170">Duration</span><span class="sxs-lookup"><span data-stu-id="34b24-170">Duration</span></span>

<span data-ttu-id="34b24-p104">您可以执行用来计算持续时间或经过时间的运算。持续时间在内部存储为整天数和分数天数。例如，经过 1 周、经过 7 日以及经过 168 个小时都在内部存储为 7.0，但它们会以适当的单位显示。</span><span class="sxs-lookup"><span data-stu-id="34b24-p104">You can perform operations that calculate duration or elapsed time. Duration is stored internally as days and the fraction of a day. For example, 1 elapsed week, 7 elapsed days, and 168 elapsed hours all are stored internally as 7.0, but are displayed with the appropriate units.</span></span>
  
<span data-ttu-id="34b24-174">Visio 可识别下表中的持续时间单位。</span><span class="sxs-lookup"><span data-stu-id="34b24-174">Visio recognizes the units of duration in the following table.</span></span>
  
|<span data-ttu-id="34b24-175">**Unit**</span><span class="sxs-lookup"><span data-stu-id="34b24-175">**Unit**</span></span>|<span data-ttu-id="34b24-176">**Abbreviation**</span><span class="sxs-lookup"><span data-stu-id="34b24-176">**Abbreviation**</span></span>|<span data-ttu-id="34b24-177">**通用缩写形式**</span><span class="sxs-lookup"><span data-stu-id="34b24-177">**Universal abbreviation**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="34b24-178">已用天数</span><span class="sxs-lookup"><span data-stu-id="34b24-178">elapsed day</span></span>  <br/> | <span data-ttu-id="34b24-179">eday、ed.</span><span class="sxs-lookup"><span data-stu-id="34b24-179">eday, ed.</span></span>  <br/> | <span data-ttu-id="34b24-180">ed</span><span class="sxs-lookup"><span data-stu-id="34b24-180">ed</span></span>  <br/> |
| <span data-ttu-id="34b24-181">已用小时数</span><span class="sxs-lookup"><span data-stu-id="34b24-181">elapsed hour</span></span>  <br/> | <span data-ttu-id="34b24-182">ehour、eh.</span><span class="sxs-lookup"><span data-stu-id="34b24-182">ehour, eh.</span></span>  <br/> | <span data-ttu-id="34b24-183">eh</span><span class="sxs-lookup"><span data-stu-id="34b24-183">eh</span></span>  <br/> |
| <span data-ttu-id="34b24-184">已用分钟数</span><span class="sxs-lookup"><span data-stu-id="34b24-184">elapsed minute</span></span>  <br/> | <span data-ttu-id="34b24-185">eminute、em.</span><span class="sxs-lookup"><span data-stu-id="34b24-185">eminute, em.</span></span>  <br/> | <span data-ttu-id="34b24-186">em</span><span class="sxs-lookup"><span data-stu-id="34b24-186">em</span></span>  <br/> |
| <span data-ttu-id="34b24-187">已用秒数</span><span class="sxs-lookup"><span data-stu-id="34b24-187">elapsed second</span></span>  <br/> | <span data-ttu-id="34b24-188">esecond、es.</span><span class="sxs-lookup"><span data-stu-id="34b24-188">esecond, es.</span></span>  <br/> | <span data-ttu-id="34b24-189">es</span><span class="sxs-lookup"><span data-stu-id="34b24-189">es</span></span>  <br/> |
| <span data-ttu-id="34b24-190">已用星期数</span><span class="sxs-lookup"><span data-stu-id="34b24-190">elapsed week</span></span>  <br/> | <span data-ttu-id="34b24-191">eweek、ew.</span><span class="sxs-lookup"><span data-stu-id="34b24-191">eweek, ew.</span></span>  <br/> | <span data-ttu-id="34b24-192">ew</span><span class="sxs-lookup"><span data-stu-id="34b24-192">ew</span></span>  <br/> |
   
<span data-ttu-id="34b24-p105">您可以将日期和时间与持续时间相加得到一个新的日期和时间。还可以用日期、时间和持续时间执行在下表中列出的运算。</span><span class="sxs-lookup"><span data-stu-id="34b24-p105">You can add a date and time to a duration to calculate a new date and time. You can perform the operations listed in this table using dates, times, and durations.</span></span>
  
|<span data-ttu-id="34b24-195">**输入**</span><span class="sxs-lookup"><span data-stu-id="34b24-195">**Input**</span></span>|<span data-ttu-id="34b24-196">**结果**</span><span class="sxs-lookup"><span data-stu-id="34b24-196">**Result**</span></span>|
|:-----|:-----|
| <span data-ttu-id="34b24-197">日期时间 +/- 持续时间</span><span class="sxs-lookup"><span data-stu-id="34b24-197">Date-time +/- duration</span></span>  <br/> | <span data-ttu-id="34b24-198">日期和时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-198">Date and time value</span></span>  <br/> |
| <span data-ttu-id="34b24-199">持续时间 +/- 日期时间</span><span class="sxs-lookup"><span data-stu-id="34b24-199">Duration +/- date-time</span></span>  <br/> | <span data-ttu-id="34b24-200">日期和时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-200">Date and time value</span></span>  <br/> |
| <span data-ttu-id="34b24-201">持续时间 +/- 持续时间</span><span class="sxs-lookup"><span data-stu-id="34b24-201">Duration +/- duration</span></span>  <br/> | <span data-ttu-id="34b24-202">持续时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-202">Duration value</span></span>  <br/> |
| <span data-ttu-id="34b24-203">日期时间 + 日期时间</span><span class="sxs-lookup"><span data-stu-id="34b24-203">Date-time + date-time</span></span>  <br/> | <span data-ttu-id="34b24-204">日期和时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-204">Date and time value</span></span>  <br/> |
| <span data-ttu-id="34b24-205">日期时间 - 日期时间</span><span class="sxs-lookup"><span data-stu-id="34b24-205">Date-time - date-time</span></span>  <br/> | <span data-ttu-id="34b24-206">持续时间值</span><span class="sxs-lookup"><span data-stu-id="34b24-206">Duration value</span></span>  <br/> |
   

