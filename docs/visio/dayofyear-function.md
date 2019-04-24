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
description: 返回一个介于1到366之间的整数, 该整数表示日期时间或表达式中的一年中的连续日期。 DAYOFYEAR 函数使用公历日历。
ms.openlocfilehash: 30c0331a57282baee97e81689b6a8f362581b8f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360290"
---
# <a name="dayofyear-function"></a><span data-ttu-id="7ef25-104">DAYOFYEAR 函数</span><span class="sxs-lookup"><span data-stu-id="7ef25-104">DAYOFYEAR Function</span></span>

<span data-ttu-id="7ef25-105">返回一个介于1到366之间的整数, 该整数表示_日期时间_或_表达式_中的一年中的连续日期。</span><span class="sxs-lookup"><span data-stu-id="7ef25-105">Returns an integer, 1 to 366, that represents the sequential day of the year in  _datetime_ or  _expression_.</span></span> <span data-ttu-id="7ef25-106">DAYOFYEAR 函数使用公历日历。</span><span class="sxs-lookup"><span data-stu-id="7ef25-106">The DAYOFYEAR function uses the Gregorian calendar.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7ef25-107">语法</span><span class="sxs-lookup"><span data-stu-id="7ef25-107">Syntax</span></span>

<span data-ttu-id="7ef25-108">DAYOFYEAR ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="7ef25-108">DAYOFYEAR(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7ef25-109">参数</span><span class="sxs-lookup"><span data-stu-id="7ef25-109">Parameters</span></span>

|<span data-ttu-id="7ef25-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ef25-110">**Name**</span></span>|<span data-ttu-id="7ef25-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7ef25-111">**Required/Optional**</span></span>|<span data-ttu-id="7ef25-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7ef25-112">**Data Type**</span></span>|<span data-ttu-id="7ef25-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ef25-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7ef25-114">_datetime_</span><span class="sxs-lookup"><span data-stu-id="7ef25-114">_datetime_</span></span> <br/> |<span data-ttu-id="7ef25-115">必需</span><span class="sxs-lookup"><span data-stu-id="7ef25-115">Required</span></span>  <br/> |<span data-ttu-id="7ef25-116">**String**</span><span class="sxs-lookup"><span data-stu-id="7ef25-116">**String**</span></span> <br/> |<span data-ttu-id="7ef25-117">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="7ef25-117">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="7ef25-118">_expression_</span><span class="sxs-lookup"><span data-stu-id="7ef25-118">_expression_</span></span> <br/> |<span data-ttu-id="7ef25-119">必需</span><span class="sxs-lookup"><span data-stu-id="7ef25-119">Required</span></span>  <br/> |<span data-ttu-id="7ef25-120">**String**</span><span class="sxs-lookup"><span data-stu-id="7ef25-120">**String**</span></span> <br/> |<span data-ttu-id="7ef25-121">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="7ef25-121">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="7ef25-122">_lcid_</span><span class="sxs-lookup"><span data-stu-id="7ef25-122">_lcid_</span></span> <br/> |<span data-ttu-id="7ef25-123">可选</span><span class="sxs-lookup"><span data-stu-id="7ef25-123">Optional</span></span>  <br/> |<span data-ttu-id="7ef25-124">**Number**</span><span class="sxs-lookup"><span data-stu-id="7ef25-124">**Number**</span></span> <br/> |<span data-ttu-id="7ef25-p103">指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="7ef25-p103">Specifies the locale identifier to be used in evaluating a non-local datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="7ef25-127">返回值</span><span class="sxs-lookup"><span data-stu-id="7ef25-127">Return value</span></span>

<span data-ttu-id="7ef25-128">整数</span><span class="sxs-lookup"><span data-stu-id="7ef25-128">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7ef25-129">注解</span><span class="sxs-lookup"><span data-stu-id="7ef25-129">Remarks</span></span>

<span data-ttu-id="7ef25-130">_datetime_或_expression_中的任何时间组件都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="7ef25-130">Any time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="7ef25-131">结果对应 1 月 1 日至 12 月 31 日。</span><span class="sxs-lookup"><span data-stu-id="7ef25-131">The result corresponds to January 1 to December 31.</span></span> <span data-ttu-id="7ef25-132">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="7ef25-132">No rounding is done.</span></span> <span data-ttu-id="7ef25-133">如果_datetime_缺失或无法解释为有效的日期或时间, 则函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="7ef25-133">If  _datetime_ is missing or cannot be interpreted as a valid date or time, the function returns an error.</span></span> 
  
<span data-ttu-id="7ef25-134">DAYOFYEAR 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。</span><span class="sxs-lookup"><span data-stu-id="7ef25-134">The DAYOFYEAR function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="7ef25-135">示例 1</span><span class="sxs-lookup"><span data-stu-id="7ef25-135">Example 1</span></span>

<span data-ttu-id="7ef25-136">DAYOFYEAR("May 30, 1997 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="7ef25-136">DAYOFYEAR("May 30, 1997 13:45:24")</span></span>
  
<span data-ttu-id="7ef25-137">返回 150。</span><span class="sxs-lookup"><span data-stu-id="7ef25-137">Returns 150.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7ef25-138">示例 2</span><span class="sxs-lookup"><span data-stu-id="7ef25-138">Example 2</span></span>

<span data-ttu-id="7ef25-139">DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)</span><span class="sxs-lookup"><span data-stu-id="7ef25-139">DAYOFYEAR(DATEVALUE("May 30, 1997")+7 ed.)</span></span>
  
<span data-ttu-id="7ef25-140">返回 157。</span><span class="sxs-lookup"><span data-stu-id="7ef25-140">Returns 157.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="7ef25-141">示例 3</span><span class="sxs-lookup"><span data-stu-id="7ef25-141">Example 3</span></span>

<span data-ttu-id="7ef25-142">DAYOFYEAR (35580.6337)</span><span class="sxs-lookup"><span data-stu-id="7ef25-142">DAYOFYEAR(35580.6337)</span></span>
  
<span data-ttu-id="7ef25-143">返回 150。</span><span class="sxs-lookup"><span data-stu-id="7ef25-143">Returns 150.</span></span>
  

