---
title: YEAR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251513
localization_priority: Normal
ms.assetid: acc136ef-9946-7c12-a467-9ded732a3549
description: 返回一个 integer 类型的值, 该值代表日期时间或表达式中的公历年, 根据系统的当前区域和语言设置的短日期样式设置格式。
ms.openlocfilehash: c9bacd34557d365841171bee5c9f4683e6a3d296
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351651"
---
# <a name="year-function-visioshapesheet"></a><span data-ttu-id="5b46e-103">YEAR 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="5b46e-103">YEAR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="5b46e-104">返回一个 integer 类型的值, 该值代表_日期时间_或_表达式_中的公历年, 根据系统的当前区域和语言设置的短日期样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="5b46e-104">Returns an integer that represents the Gregorian year in  _datetime_ or  _expression_, formatted according to the short date style set by the system's current Region and Language settings.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5b46e-105">语法</span><span class="sxs-lookup"><span data-stu-id="5b46e-105">Syntax</span></span>

<span data-ttu-id="5b46e-106">YEAR ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="5b46e-106">YEAR(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5b46e-107">参数</span><span class="sxs-lookup"><span data-stu-id="5b46e-107">Parameters</span></span>

|<span data-ttu-id="5b46e-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5b46e-108">**Name**</span></span>|<span data-ttu-id="5b46e-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5b46e-109">**Required/Optional**</span></span>|<span data-ttu-id="5b46e-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5b46e-110">**Data Type**</span></span>|<span data-ttu-id="5b46e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b46e-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5b46e-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="5b46e-112">_datetime_</span></span> <br/> |<span data-ttu-id="5b46e-113">必需</span><span class="sxs-lookup"><span data-stu-id="5b46e-113">Required</span></span>  <br/> |<span data-ttu-id="5b46e-114">**String**</span><span class="sxs-lookup"><span data-stu-id="5b46e-114">**String**</span></span> <br/> | <span data-ttu-id="5b46e-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="5b46e-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="5b46e-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="5b46e-116">_expression_</span></span> <br/> |<span data-ttu-id="5b46e-117">必需</span><span class="sxs-lookup"><span data-stu-id="5b46e-117">Required</span></span>  <br/> |<span data-ttu-id="5b46e-118">**相同**</span><span class="sxs-lookup"><span data-stu-id="5b46e-118">**Varies**</span></span> <br/> |<span data-ttu-id="5b46e-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="5b46e-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="5b46e-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="5b46e-120">_lcid_</span></span> <br/> |<span data-ttu-id="5b46e-121">可选</span><span class="sxs-lookup"><span data-stu-id="5b46e-121">Optional</span></span>  <br/> |<span data-ttu-id="5b46e-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="5b46e-122">**Numeric**</span></span> <br/> |<span data-ttu-id="5b46e-123">用于计算非本地日期时间的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="5b46e-123">The locale identifier to be used in evaluating a nonlocal datetime.</span></span> <span data-ttu-id="5b46e-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="5b46e-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5b46e-125">返回值</span><span class="sxs-lookup"><span data-stu-id="5b46e-125">Return value</span></span>

<span data-ttu-id="5b46e-126">整数</span><span class="sxs-lookup"><span data-stu-id="5b46e-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5b46e-127">注解</span><span class="sxs-lookup"><span data-stu-id="5b46e-127">Remarks</span></span>

<span data-ttu-id="5b46e-128">_datetime_或_expression_中的时间部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="5b46e-128">The time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="5b46e-129">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="5b46e-129">No rounding is done.</span></span> <span data-ttu-id="5b46e-130">如果_datetime_缺失或无法解释为有效的日期或时间, 则 YEAR 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5b46e-130">If  _datetime_ is missing or cannot be interpreted as a valid date or time, YEAR returns an error.</span></span> 
  
<span data-ttu-id="5b46e-131">YEAR 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。</span><span class="sxs-lookup"><span data-stu-id="5b46e-131">The YEAR function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="5b46e-132">示例 1</span><span class="sxs-lookup"><span data-stu-id="5b46e-132">Example 1</span></span>

<span data-ttu-id="5b46e-133">YEAR ("10/27/2007 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="5b46e-133">YEAR("10/27/2007 13:45:24")</span></span>
  
<span data-ttu-id="5b46e-134">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="5b46e-134">Returns 2007.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="5b46e-135">示例 2</span><span class="sxs-lookup"><span data-stu-id="5b46e-135">Example 2</span></span>

<span data-ttu-id="5b46e-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span><span class="sxs-lookup"><span data-stu-id="5b46e-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span></span>
  
<span data-ttu-id="5b46e-137">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="5b46e-137">Returns 2007.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="5b46e-138">示例 3</span><span class="sxs-lookup"><span data-stu-id="5b46e-138">Example 3</span></span>

<span data-ttu-id="5b46e-139">YEAR (35580.6337)</span><span class="sxs-lookup"><span data-stu-id="5b46e-139">YEAR(35580.6337)</span></span>
  
<span data-ttu-id="5b46e-140">返回 1997。</span><span class="sxs-lookup"><span data-stu-id="5b46e-140">Returns 1997.</span></span>
  

