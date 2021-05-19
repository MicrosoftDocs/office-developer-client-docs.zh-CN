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
description: 返回一个整数，该整数表示日期时间或表达式中的公历年，根据系统的当前"地区"和"语言"设置设置的短日期样式进行格式设置。
ms.openlocfilehash: c9bacd34557d365841171bee5c9f4683e6a3d296
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420708"
---
# <a name="year-function-visioshapesheet"></a><span data-ttu-id="1e312-103">YEAR 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="1e312-103">YEAR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="1e312-104">返回一个整数，该整数表示日期时间或表达式中的公历年，根据系统的当前"地区"和"语言"设置设置的短日期样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="1e312-104">Returns an integer that represents the Gregorian year in  _datetime_ or  _expression_, formatted according to the short date style set by the system's current Region and Language settings.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e312-105">语法</span><span class="sxs-lookup"><span data-stu-id="1e312-105">Syntax</span></span>

<span data-ttu-id="1e312-106">YEAR (" \*\* *datetime* \*\* "|\*\* *expression* \*\* [， \*\* *lcid* \*\* ]) </span><span class="sxs-lookup"><span data-stu-id="1e312-106">YEAR(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1e312-107">参数</span><span class="sxs-lookup"><span data-stu-id="1e312-107">Parameters</span></span>

|<span data-ttu-id="1e312-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="1e312-108">**Name**</span></span>|<span data-ttu-id="1e312-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1e312-109">**Required/Optional**</span></span>|<span data-ttu-id="1e312-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1e312-110">**Data Type**</span></span>|<span data-ttu-id="1e312-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e312-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1e312-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="1e312-112">_datetime_</span></span> <br/> |<span data-ttu-id="1e312-113">必需</span><span class="sxs-lookup"><span data-stu-id="1e312-113">Required</span></span>  <br/> |<span data-ttu-id="1e312-114">**String**</span><span class="sxs-lookup"><span data-stu-id="1e312-114">**String**</span></span> <br/> | <span data-ttu-id="1e312-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="1e312-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="1e312-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="1e312-116">_expression_</span></span> <br/> |<span data-ttu-id="1e312-117">必需</span><span class="sxs-lookup"><span data-stu-id="1e312-117">Required</span></span>  <br/> |<span data-ttu-id="1e312-118">**变化**</span><span class="sxs-lookup"><span data-stu-id="1e312-118">**Varies**</span></span> <br/> |<span data-ttu-id="1e312-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="1e312-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="1e312-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="1e312-120">_lcid_</span></span> <br/> |<span data-ttu-id="1e312-121">可选</span><span class="sxs-lookup"><span data-stu-id="1e312-121">Optional</span></span>  <br/> |<span data-ttu-id="1e312-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="1e312-122">**Numeric**</span></span> <br/> |<span data-ttu-id="1e312-p101">用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="1e312-p101">The locale identifier to be used in evaluating a nonlocal datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1e312-125">返回值</span><span class="sxs-lookup"><span data-stu-id="1e312-125">Return value</span></span>

<span data-ttu-id="1e312-126">整数</span><span class="sxs-lookup"><span data-stu-id="1e312-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1e312-127">备注</span><span class="sxs-lookup"><span data-stu-id="1e312-127">Remarks</span></span>

<span data-ttu-id="1e312-128">datetime 或 expression _中__的时间_ 部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="1e312-128">The time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="1e312-129">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="1e312-129">No rounding is done.</span></span> <span data-ttu-id="1e312-130">如果  _datetime_ 缺失或无法解释为有效的日期或时间，则 YEAR 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1e312-130">If  _datetime_ is missing or cannot be interpreted as a valid date or time, YEAR returns an error.</span></span> 
  
<span data-ttu-id="1e312-131">YEAR 函数还接受单个数值的  _expression，_ 其中结果的整数部分表示自 1899 年 12 月 30 日起的天数。</span><span class="sxs-lookup"><span data-stu-id="1e312-131">The YEAR function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="1e312-132">示例 1</span><span class="sxs-lookup"><span data-stu-id="1e312-132">Example 1</span></span>

<span data-ttu-id="1e312-133">YEAR ("10/27/2007 13：45：24") </span><span class="sxs-lookup"><span data-stu-id="1e312-133">YEAR("10/27/2007 13:45:24")</span></span>
  
<span data-ttu-id="1e312-134">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="1e312-134">Returns 2007.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1e312-135">示例 2</span><span class="sxs-lookup"><span data-stu-id="1e312-135">Example 2</span></span>

<span data-ttu-id="1e312-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span><span class="sxs-lookup"><span data-stu-id="1e312-136">YEAR(DATEVALUE("Dec. 25, 2006") + 7 ed.)</span></span>
  
<span data-ttu-id="1e312-137">返回 2007。</span><span class="sxs-lookup"><span data-stu-id="1e312-137">Returns 2007.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1e312-138">示例 3</span><span class="sxs-lookup"><span data-stu-id="1e312-138">Example 3</span></span>

<span data-ttu-id="1e312-139">YEAR (35580.6337) </span><span class="sxs-lookup"><span data-stu-id="1e312-139">YEAR(35580.6337)</span></span>
  
<span data-ttu-id="1e312-140">返回 1997。</span><span class="sxs-lookup"><span data-stu-id="1e312-140">Returns 1997.</span></span>
  

