---
title: DATETIME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251413
localization_priority: Normal
ms.assetid: 0bf7f757-0b7f-dec1-9709-6612c9ad0d53
description: 返回 datetime 或 expression 所表示的日期和时间值。
ms.openlocfilehash: 001430acaf9fcb670e95157380e474e12b9728cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780054"
---
# <a name="datetime-function"></a><span data-ttu-id="2d622-103">DATETIME 函数</span><span class="sxs-lookup"><span data-stu-id="2d622-103">DATETIME Function</span></span>

<span data-ttu-id="2d622-104">返回_datetime_或_expression_所表示的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="2d622-104">Returns the date and time value represented by  _datetime_ or  _expression_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2d622-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d622-105">Syntax</span></span>

<span data-ttu-id="2d622-106">DATETIME ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *])</span><span class="sxs-lookup"><span data-stu-id="2d622-106">DATETIME(" ** *datetime* ** "| ** *expression* ** [, ** *lcid* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2d622-107">参数</span><span class="sxs-lookup"><span data-stu-id="2d622-107">Parameters</span></span>

|<span data-ttu-id="2d622-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="2d622-108">**Name**</span></span>|<span data-ttu-id="2d622-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2d622-109">**Required/Optional**</span></span>|<span data-ttu-id="2d622-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2d622-110">**Data Type**</span></span>|<span data-ttu-id="2d622-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2d622-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2d622-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="2d622-112">_datetime_</span></span> <br/> |<span data-ttu-id="2d622-113">必需</span><span class="sxs-lookup"><span data-stu-id="2d622-113">Required</span></span>  <br/> |<span data-ttu-id="2d622-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="2d622-114">**String**</span></span> <br/> |<span data-ttu-id="2d622-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="2d622-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="2d622-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="2d622-116">_expression_</span></span> <br/> |<span data-ttu-id="2d622-117">必需</span><span class="sxs-lookup"><span data-stu-id="2d622-117">Required</span></span>  <br/> |<span data-ttu-id="2d622-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="2d622-118">**String**</span></span> <br/> |<span data-ttu-id="2d622-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="2d622-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="2d622-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="2d622-120">_lcid_</span></span> <br/> |<span data-ttu-id="2d622-121">可选</span><span class="sxs-lookup"><span data-stu-id="2d622-121">Optional</span></span>  <br/> |<span data-ttu-id="2d622-122">**编号**</span><span class="sxs-lookup"><span data-stu-id="2d622-122">**Number**</span></span> <br/> |<span data-ttu-id="2d622-p101">指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="2d622-p101">Specifies the locale identifier to be used in evaluating a non-local datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2d622-125">返回值</span><span class="sxs-lookup"><span data-stu-id="2d622-125">Return value</span></span>

<span data-ttu-id="2d622-126">Datetime</span><span class="sxs-lookup"><span data-stu-id="2d622-126">Datetime</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2d622-127">注解</span><span class="sxs-lookup"><span data-stu-id="2d622-127">Remarks</span></span>

<span data-ttu-id="2d622-128">如果*datetime*缺失或无法解释为有效的日期或时间，则 DATETIME 返回 #VALUE ！。</span><span class="sxs-lookup"><span data-stu-id="2d622-128">If  *datetime*  is missing or cannot be interpreted as a valid date or time, DATETIME returns a #VALUE!</span></span> <span data-ttu-id="2d622-129">错误。</span><span class="sxs-lookup"><span data-stu-id="2d622-129">error.</span></span> 
  
<span data-ttu-id="2d622-130">返回的值根据系统当前“区域设置”中的短日期样式和时间样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="2d622-130">The returned value is formatted according to the short date style and time style in the system's current Regional Settings.</span></span> 
  
<span data-ttu-id="2d622-131">DATETIME 函数还接受值为单一数值的*expression* ，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数，而的小数部分代表自午夜开始的一天的时间占。</span><span class="sxs-lookup"><span data-stu-id="2d622-131">The DATETIME function also accepts a single number value for  *expression*  where the integer portion of the result represents the number of days since December 30, 1899, and the decimal portion represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="2d622-132">示例 1</span><span class="sxs-lookup"><span data-stu-id="2d622-132">Example 1</span></span>

<span data-ttu-id="2d622-133">DATETIME("May 30, 1997")+5 ed.</span><span class="sxs-lookup"><span data-stu-id="2d622-133">DATETIME("May 30, 1997")+5 ed.</span></span>
  
<span data-ttu-id="2d622-134">返回表示 6/4/1997 的值。</span><span class="sxs-lookup"><span data-stu-id="2d622-134">Returns the value representing 6/4/1997.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="2d622-135">示例 2</span><span class="sxs-lookup"><span data-stu-id="2d622-135">Example 2</span></span>

<span data-ttu-id="2d622-136">FORMAT(DATETIME("5/20/1997 14:30:45"),"C")</span><span class="sxs-lookup"><span data-stu-id="2d622-136">FORMAT(DATETIME("5/20/1997 14:30:45"),"C")</span></span>
  
<span data-ttu-id="2d622-137">返回字符串“Tuesday, May 20, 1997 2:30:45 PM”。</span><span class="sxs-lookup"><span data-stu-id="2d622-137">Returns the string "Tuesday, May 20, 1997 2:30:45 PM."</span></span>
  
## <a name="example-3"></a><span data-ttu-id="2d622-138">示例 3</span><span class="sxs-lookup"><span data-stu-id="2d622-138">Example 3</span></span>

<span data-ttu-id="2d622-139">DATETIME("1:30 PM July 19")</span><span class="sxs-lookup"><span data-stu-id="2d622-139">DATETIME("1:30 PM July 19")</span></span>
  
<span data-ttu-id="2d622-140">返回表示 7/19/2001 1:30:00 PM 的值（假定当前为 2001 年）。</span><span class="sxs-lookup"><span data-stu-id="2d622-140">Returns the value representing 7/19/2001 1:30:00 PM (assuming the current year is 2001).</span></span>
  
## <a name="example-4"></a><span data-ttu-id="2d622-141">示例 4</span><span class="sxs-lookup"><span data-stu-id="2d622-141">Example 4</span></span>

<span data-ttu-id="2d622-142">DATETIME(35580.6337)</span><span class="sxs-lookup"><span data-stu-id="2d622-142">DATETIME(35580.6337)</span></span>
  
<span data-ttu-id="2d622-143">返回表示 5/30/1997 3:12:32 PM 的值。</span><span class="sxs-lookup"><span data-stu-id="2d622-143">Returns the value representing 5/30/1997 3:12:32 PM.</span></span>
  

