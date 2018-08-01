---
title: YEAR Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251513
localization_priority: Normal
ms.assetid: acc136ef-9946-7c12-a467-9ded732a3549
description: 返回一个整数，表示公历年 datetime 或 expression 中，根据系统当前区域和语言设置由设置的短日期样式设置格式。
ms.openlocfilehash: aaa183730440857d8d283912f4afeb3117ef737f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781715"
---
# <a name="year-function-visioshapesheet"></a><span data-ttu-id="4f2ad-103">YEAR Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="4f2ad-103">YEAR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="4f2ad-104">返回一个整数，表示公历年_datetime_或_expression_，根据系统当前区域和语言设置由设置的短日期样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-104">Returns an integer that represents the Gregorian year in  _datetime_ or  _expression_, formatted according to the short date style set by the system's current Region and Language settings.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4f2ad-105">语法</span><span class="sxs-lookup"><span data-stu-id="4f2ad-105">Syntax</span></span>

<span data-ttu-id="4f2ad-106">年 ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *])</span><span class="sxs-lookup"><span data-stu-id="4f2ad-106">YEAR(" ** *datetime* ** "| ** *expression* ** [, ** *lcid* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4f2ad-107">参数</span><span class="sxs-lookup"><span data-stu-id="4f2ad-107">Parameters</span></span>

|<span data-ttu-id="4f2ad-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-108">**Name**</span></span>|<span data-ttu-id="4f2ad-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-109">**Required/Optional**</span></span>|<span data-ttu-id="4f2ad-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-110">**Data Type**</span></span>|<span data-ttu-id="4f2ad-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4f2ad-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="4f2ad-112">_datetime_</span></span> <br/> |<span data-ttu-id="4f2ad-113">必需</span><span class="sxs-lookup"><span data-stu-id="4f2ad-113">Required</span></span>  <br/> |<span data-ttu-id="4f2ad-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-114">**String**</span></span> <br/> | <span data-ttu-id="4f2ad-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="4f2ad-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="4f2ad-116">_expression_</span></span> <br/> |<span data-ttu-id="4f2ad-117">必需</span><span class="sxs-lookup"><span data-stu-id="4f2ad-117">Required</span></span>  <br/> |<span data-ttu-id="4f2ad-118">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-118">**Varies**</span></span> <br/> |<span data-ttu-id="4f2ad-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="4f2ad-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="4f2ad-120">_lcid_</span></span> <br/> |<span data-ttu-id="4f2ad-121">可选</span><span class="sxs-lookup"><span data-stu-id="4f2ad-121">Optional</span></span>  <br/> |<span data-ttu-id="4f2ad-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="4f2ad-122">**Numeric**</span></span> <br/> |<span data-ttu-id="4f2ad-p101">用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-p101">The locale identifier to be used in evaluating a nonlocal datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4f2ad-125">返回值</span><span class="sxs-lookup"><span data-stu-id="4f2ad-125">Return value</span></span>

<span data-ttu-id="4f2ad-126">Integer</span><span class="sxs-lookup"><span data-stu-id="4f2ad-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4f2ad-127">说明</span><span class="sxs-lookup"><span data-stu-id="4f2ad-127">Remarks</span></span>

<span data-ttu-id="4f2ad-128">_Datetime_或_expression_中的时间组件已被丢弃。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-128">The time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="4f2ad-129">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-129">No rounding is done.</span></span> <span data-ttu-id="4f2ad-130">如果_datetime_缺失或无法解释为有效的日期或时间，年将返回错误。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-130">If  _datetime_ is missing or cannot be interpreted as a valid date or time, YEAR returns an error.</span></span> 
  
<span data-ttu-id="4f2ad-131">YEAR 函数还接受值为单一数值的_表达式_，其中结果的整数部分代表自 1899 年 12 月 30 日以来的天数。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-131">The YEAR function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="4f2ad-132">示例 1</span><span class="sxs-lookup"><span data-stu-id="4f2ad-132">Example 1</span></span>

<span data-ttu-id="4f2ad-133">YEAR("10/27/2007 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="4f2ad-133">YEAR("10/27/2007 13:45:24")</span></span>
  
<span data-ttu-id="4f2ad-134">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-134">Returns 2007.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="4f2ad-135">示例 2</span><span class="sxs-lookup"><span data-stu-id="4f2ad-135">Example 2</span></span>

<span data-ttu-id="4f2ad-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span><span class="sxs-lookup"><span data-stu-id="4f2ad-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span></span>
  
<span data-ttu-id="4f2ad-137">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-137">Returns 2007.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="4f2ad-138">示例 3</span><span class="sxs-lookup"><span data-stu-id="4f2ad-138">Example 3</span></span>

<span data-ttu-id="4f2ad-139">YEAR(35580.6337)</span><span class="sxs-lookup"><span data-stu-id="4f2ad-139">YEAR(35580.6337)</span></span>
  
<span data-ttu-id="4f2ad-140">返回 1997。</span><span class="sxs-lookup"><span data-stu-id="4f2ad-140">Returns 1997.</span></span>
  

