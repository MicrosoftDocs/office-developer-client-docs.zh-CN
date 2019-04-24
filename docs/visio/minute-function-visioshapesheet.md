---
title: MINUTE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251464
localization_priority: Normal
ms.assetid: 5a90cb16-7eef-8876-8e25-408787b16f58
description: 返回一个介于0到59之间的整数, 该整数表示 datetime 或 expression 的分钟部分。
ms.openlocfilehash: 35fe1dc8d4026dd6c829a38504d9ba82d64edda2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283970"
---
# <a name="minute-function-visioshapesheet"></a><span data-ttu-id="d2622-103">MINUTE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="d2622-103">MINUTE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="d2622-104">返回一个介于0到59之间的整数, 该整数表示*datetime*或*expression*的分钟部分。</span><span class="sxs-lookup"><span data-stu-id="d2622-104">Returns an integer from 0 to 59 that represents the minutes component of  *datetime*  or  *expression*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d2622-105">语法</span><span class="sxs-lookup"><span data-stu-id="d2622-105">Syntax</span></span>

<span data-ttu-id="d2622-106">MINUTE (" *datetime* " | *表达式* [, *lcid* ])</span><span class="sxs-lookup"><span data-stu-id="d2622-106">MINUTE(" *datetime*  "|  *expression*  [,  *lcid*  ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d2622-107">参数</span><span class="sxs-lookup"><span data-stu-id="d2622-107">Parameters</span></span>

|<span data-ttu-id="d2622-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d2622-108">**Name**</span></span>|<span data-ttu-id="d2622-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d2622-109">**Required/Optional**</span></span>|<span data-ttu-id="d2622-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d2622-110">**Data Type**</span></span>|<span data-ttu-id="d2622-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2622-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d2622-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="d2622-112">_datetime_</span></span> <br/> |<span data-ttu-id="d2622-113">必需</span><span class="sxs-lookup"><span data-stu-id="d2622-113">Required</span></span>  <br/> |<span data-ttu-id="d2622-114">**String**</span><span class="sxs-lookup"><span data-stu-id="d2622-114">**String**</span></span> <br/> |<span data-ttu-id="d2622-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="d2622-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="d2622-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="d2622-116">_expression_</span></span> <br/> |<span data-ttu-id="d2622-117">必需</span><span class="sxs-lookup"><span data-stu-id="d2622-117">Required</span></span>  <br/> |<span data-ttu-id="d2622-118">**String**</span><span class="sxs-lookup"><span data-stu-id="d2622-118">**String**</span></span> <br/> | <span data-ttu-id="d2622-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="d2622-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="d2622-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="d2622-120">_lcid_</span></span> <br/> |<span data-ttu-id="d2622-121">可选</span><span class="sxs-lookup"><span data-stu-id="d2622-121">Optional</span></span>  <br/> |<span data-ttu-id="d2622-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="d2622-122">**Number**</span></span> <br/> |<span data-ttu-id="d2622-123">用于计算非本地日期时间的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="d2622-123">The locale identifier to be used in evaluating a nonlocal datetime.</span></span> <span data-ttu-id="d2622-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="d2622-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d2622-125">返回值</span><span class="sxs-lookup"><span data-stu-id="d2622-125">Return value</span></span>

<span data-ttu-id="d2622-126">整数</span><span class="sxs-lookup"><span data-stu-id="d2622-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2622-127">注解</span><span class="sxs-lookup"><span data-stu-id="d2622-127">Remarks</span></span>

<span data-ttu-id="d2622-128">_datetime_和_expression_中的日期部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="d2622-128">The date component in  _datetime_ and  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="d2622-129">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="d2622-129">No rounding is done.</span></span> <span data-ttu-id="d2622-130">如果_datetime_缺失或无法转换为有效结果, 函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="d2622-130">If  _datetime_ is missing or cannot be converted to a valid result, the function returns an error.</span></span> 
  
<span data-ttu-id="d2622-131">返回的值根据系统当前“区域设置”中设置的时间样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="d2622-131">The returned value is formatted according to the time style set by the system's current Regional Settings.</span></span>
  
<span data-ttu-id="d2622-132">MINUTE 函数还接受单个数值的_表达式_, 其中小数部分表示自午夜以来一天的时间。</span><span class="sxs-lookup"><span data-stu-id="d2622-132">The MINUTE function also accepts a single number value for  _expression_ where the decimal portion represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="d2622-133">示例 1</span><span class="sxs-lookup"><span data-stu-id="d2622-133">Example 1</span></span>

<span data-ttu-id="d2622-134">MINUTE ("7/7/1999 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="d2622-134">MINUTE("7/7/1999 13:45:24")</span></span>
  
<span data-ttu-id="d2622-135">返回 45。</span><span class="sxs-lookup"><span data-stu-id="d2622-135">Returns 45.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="d2622-136">示例 2</span><span class="sxs-lookup"><span data-stu-id="d2622-136">Example 2</span></span>

<span data-ttu-id="d2622-137">MINUTE(TIMEVALUE("Jan. 25, 1999 12:07:45")+6 em.)</span><span class="sxs-lookup"><span data-stu-id="d2622-137">MINUTE(TIMEVALUE("Jan. 25, 1999 12:07:45")+6 em.)</span></span>
  
<span data-ttu-id="d2622-138">返回 13。</span><span class="sxs-lookup"><span data-stu-id="d2622-138">Returns 13.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="d2622-139">示例 3</span><span class="sxs-lookup"><span data-stu-id="d2622-139">Example 3</span></span>

<span data-ttu-id="d2622-140">MINUTE (0.575)</span><span class="sxs-lookup"><span data-stu-id="d2622-140">MINUTE(0.575)</span></span>
  
<span data-ttu-id="d2622-141">返回 48。</span><span class="sxs-lookup"><span data-stu-id="d2622-141">Returns 48.</span></span>
  

