---
title: DAYOFYEAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251416
localization_priority: Normal
ms.assetid: 154d76a2-81f5-d8b1-b665-26dbae5da615
description: 返回一个整数，1 到 366，值，该值代表 datetime 或 expression 中的年份的顺序天。 DAYOFYEAR 函数使用公历。
ms.openlocfilehash: 2fd80a2554c268d276deaa524a9d98eebc6a48d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780077"
---
# <a name="dayofyear-function"></a><span data-ttu-id="cc1b7-104">DAYOFYEAR 函数</span><span class="sxs-lookup"><span data-stu-id="cc1b7-104">DAYOFYEAR Function</span></span>

<span data-ttu-id="cc1b7-105">返回一个整数，1 到 366，值，该值代表_datetime_或_expression_中的年份的顺序天。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-105">Returns an integer, 1 to 366, that represents the sequential day of the year in  _datetime_ or  _expression_.</span></span> <span data-ttu-id="cc1b7-106">DAYOFYEAR 函数使用公历。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-106">The DAYOFYEAR function uses the Gregorian calendar.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cc1b7-107">语法</span><span class="sxs-lookup"><span data-stu-id="cc1b7-107">Syntax</span></span>

<span data-ttu-id="cc1b7-108">DAYOFYEAR ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *])</span><span class="sxs-lookup"><span data-stu-id="cc1b7-108">DAYOFYEAR(" ** *datetime* ** "| ** *expression* ** [, ** *lcid* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cc1b7-109">参数</span><span class="sxs-lookup"><span data-stu-id="cc1b7-109">Parameters</span></span>

|<span data-ttu-id="cc1b7-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-110">**Name**</span></span>|<span data-ttu-id="cc1b7-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-111">**Required/Optional**</span></span>|<span data-ttu-id="cc1b7-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-112">**Data Type**</span></span>|<span data-ttu-id="cc1b7-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cc1b7-114">_datetime_</span><span class="sxs-lookup"><span data-stu-id="cc1b7-114">_datetime_</span></span> <br/> |<span data-ttu-id="cc1b7-115">必需</span><span class="sxs-lookup"><span data-stu-id="cc1b7-115">Required</span></span>  <br/> |<span data-ttu-id="cc1b7-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-116">**String**</span></span> <br/> |<span data-ttu-id="cc1b7-117">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-117">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="cc1b7-118">_expression_</span><span class="sxs-lookup"><span data-stu-id="cc1b7-118">_expression_</span></span> <br/> |<span data-ttu-id="cc1b7-119">必需</span><span class="sxs-lookup"><span data-stu-id="cc1b7-119">Required</span></span>  <br/> |<span data-ttu-id="cc1b7-120">**字符串**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-120">**String**</span></span> <br/> |<span data-ttu-id="cc1b7-121">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-121">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="cc1b7-122">_lcid_</span><span class="sxs-lookup"><span data-stu-id="cc1b7-122">_lcid_</span></span> <br/> |<span data-ttu-id="cc1b7-123">可选</span><span class="sxs-lookup"><span data-stu-id="cc1b7-123">Optional</span></span>  <br/> |<span data-ttu-id="cc1b7-124">**编号**</span><span class="sxs-lookup"><span data-stu-id="cc1b7-124">**Number**</span></span> <br/> |<span data-ttu-id="cc1b7-p103">指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-p103">Specifies the locale identifier to be used in evaluating a non-local datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="cc1b7-127">返回值</span><span class="sxs-lookup"><span data-stu-id="cc1b7-127">Return value</span></span>

<span data-ttu-id="cc1b7-128">Integer</span><span class="sxs-lookup"><span data-stu-id="cc1b7-128">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cc1b7-129">说明</span><span class="sxs-lookup"><span data-stu-id="cc1b7-129">Remarks</span></span>

<span data-ttu-id="cc1b7-130">_Datetime_或_expression_中的任何时间组件已被丢弃。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-130">Any time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="cc1b7-131">结果对应于 1 月 1 日到年 12 月 31 日。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-131">The result corresponds to January 1 to December 31.</span></span> <span data-ttu-id="cc1b7-132">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-132">No rounding is done.</span></span> <span data-ttu-id="cc1b7-133">如果_datetime_缺失或无法解释为有效的日期或时间，则函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-133">If  _datetime_ is missing or cannot be interpreted as a valid date or time, the function returns an error.</span></span> 
  
<span data-ttu-id="cc1b7-134">DAYOFYEAR 函数还接受值为单一数值的_表达式_，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-134">The DAYOFYEAR function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="cc1b7-135">示例 1</span><span class="sxs-lookup"><span data-stu-id="cc1b7-135">Example 1</span></span>

<span data-ttu-id="cc1b7-136">DAYOFYEAR("May 30, 1997 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="cc1b7-136">DAYOFYEAR("May 30, 1997 13:45:24")</span></span>
  
<span data-ttu-id="cc1b7-137">返回 150。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-137">Returns 150.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="cc1b7-138">示例 2</span><span class="sxs-lookup"><span data-stu-id="cc1b7-138">Example 2</span></span>

<span data-ttu-id="cc1b7-139">DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)</span><span class="sxs-lookup"><span data-stu-id="cc1b7-139">DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)</span></span>
  
<span data-ttu-id="cc1b7-140">返回 157。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-140">Returns 157.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="cc1b7-141">示例 3</span><span class="sxs-lookup"><span data-stu-id="cc1b7-141">Example 3</span></span>

<span data-ttu-id="cc1b7-142">DAYOFYEAR(35580.6337)</span><span class="sxs-lookup"><span data-stu-id="cc1b7-142">DAYOFYEAR(35580.6337)</span></span>
  
<span data-ttu-id="cc1b7-143">返回 150。</span><span class="sxs-lookup"><span data-stu-id="cc1b7-143">Returns 150.</span></span>
  

