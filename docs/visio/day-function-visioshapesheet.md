---
title: DAY 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251415
localization_priority: Normal
ms.assetid: 3b0842ae-6893-2d7b-6cb2-8905198fae30
description: 返回一个整数，1 到 31，表示日期时间或表达式中的天。 DAY 函数使用公历。
ms.openlocfilehash: 49c29d5dc25bf11599f89a20cb2bc2367bd74187
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360293"
---
# <a name="day-function-visioshapesheet"></a><span data-ttu-id="0aaf1-104">DAY 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="0aaf1-104">DAY Function (VisioShapeSheet)</span></span>

<span data-ttu-id="0aaf1-105">返回一个整数，1 到 31，表示 _日期时间或表达式中的__天_。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-105">Returns an integer, 1 to 31, representing the day in  _datetime_ or  _expression_.</span></span> <span data-ttu-id="0aaf1-106">DAY 函数使用公历。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-106">The DAY function uses the Gregorian calendar.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0aaf1-107">语法</span><span class="sxs-lookup"><span data-stu-id="0aaf1-107">Syntax</span></span>

<span data-ttu-id="0aaf1-108">DAY (" \*\* *datetime* \*\* "|\*\* *expression* \*\* [， \*\* *lcid* \*\* ]) </span><span class="sxs-lookup"><span data-stu-id="0aaf1-108">DAY(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0aaf1-109">参数</span><span class="sxs-lookup"><span data-stu-id="0aaf1-109">Parameters</span></span>

|<span data-ttu-id="0aaf1-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-110">**Name**</span></span>|<span data-ttu-id="0aaf1-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-111">**Required/Optional**</span></span>|<span data-ttu-id="0aaf1-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-112">**Data Type**</span></span>|<span data-ttu-id="0aaf1-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0aaf1-114">_datetime_</span><span class="sxs-lookup"><span data-stu-id="0aaf1-114">_datetime_</span></span> <br/> |<span data-ttu-id="0aaf1-115">必需</span><span class="sxs-lookup"><span data-stu-id="0aaf1-115">Required</span></span>  <br/> |<span data-ttu-id="0aaf1-116">**String**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-116">**String**</span></span> <br/> |<span data-ttu-id="0aaf1-117">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-117">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="0aaf1-118">_expression_</span><span class="sxs-lookup"><span data-stu-id="0aaf1-118">_expression_</span></span> <br/> |<span data-ttu-id="0aaf1-119">必需</span><span class="sxs-lookup"><span data-stu-id="0aaf1-119">Required</span></span>  <br/> |<span data-ttu-id="0aaf1-120">**String**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-120">**String**</span></span> <br/> |<span data-ttu-id="0aaf1-121">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-121">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="0aaf1-122">_lcid_</span><span class="sxs-lookup"><span data-stu-id="0aaf1-122">_lcid_</span></span> <br/> |<span data-ttu-id="0aaf1-123">可选</span><span class="sxs-lookup"><span data-stu-id="0aaf1-123">Optional</span></span>  <br/> |<span data-ttu-id="0aaf1-124">**Number**</span><span class="sxs-lookup"><span data-stu-id="0aaf1-124">**Number**</span></span> <br/> |<span data-ttu-id="0aaf1-p103">指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-p103">Specifies the locale identifier to be used in evaluating a non-local datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="0aaf1-127">返回值</span><span class="sxs-lookup"><span data-stu-id="0aaf1-127">Return value</span></span>

<span data-ttu-id="0aaf1-128">整数</span><span class="sxs-lookup"><span data-stu-id="0aaf1-128">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0aaf1-129">备注</span><span class="sxs-lookup"><span data-stu-id="0aaf1-129">Remarks</span></span>

<span data-ttu-id="0aaf1-130">datetime 或 expression  _中的_ 任意  _时间_ 组件都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-130">Any time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="0aaf1-131">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-131">No rounding is done.</span></span> <span data-ttu-id="0aaf1-132">如果  _datetime_ 缺失或无法转换为有效结果，函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-132">If  _datetime_ is missing or cannot be converted to a valid result, the function returns an error.</span></span> 
  
<span data-ttu-id="0aaf1-133">DAY 函数还接受表达式的单个数值，其中结果的整数部分表示自 1899 年 12 月 30 日起的天数。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-133">The DAY function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="0aaf1-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="0aaf1-134">Example 1</span></span>

<span data-ttu-id="0aaf1-135">DAY("May 30, 1997 15:45:24")</span><span class="sxs-lookup"><span data-stu-id="0aaf1-135">DAY("May 30, 1997 15:45:24")</span></span>
  
<span data-ttu-id="0aaf1-136">返回 30。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-136">Returns 30.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="0aaf1-137">示例 2</span><span class="sxs-lookup"><span data-stu-id="0aaf1-137">Example 2</span></span>

<span data-ttu-id="0aaf1-138">DAY(DATEVALUE("May 30, 1997")+7 ed.)</span><span class="sxs-lookup"><span data-stu-id="0aaf1-138">DAY(DATEVALUE("May 30, 1997")+7 ed.)</span></span>
  
<span data-ttu-id="0aaf1-139">返回 6。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-139">Returns 6.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="0aaf1-140">示例 3</span><span class="sxs-lookup"><span data-stu-id="0aaf1-140">Example 3</span></span>

<span data-ttu-id="0aaf1-141">DAY (35580.6337) </span><span class="sxs-lookup"><span data-stu-id="0aaf1-141">DAY(35580.6337)</span></span>
  
<span data-ttu-id="0aaf1-142">返回 30。</span><span class="sxs-lookup"><span data-stu-id="0aaf1-142">Returns 30.</span></span>
  

