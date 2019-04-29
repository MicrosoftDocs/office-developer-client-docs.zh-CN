---
title: TIMEVALUE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251507
localization_priority: Normal
ms.assetid: 53579e0e-fcec-e745-0207-3861b5efa333
description: 基于系统的区域和语言设置, 返回由 datetime 或 expression 表示的时间值。
ms.openlocfilehash: 61eeafac64ce199eba0f9032c42474d2b44febce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432322"
---
# <a name="timevalue-function-visioshapesheet"></a><span data-ttu-id="989d6-103">TIMEVALUE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="989d6-103">TIMEVALUE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="989d6-104">基于系统的区域和语言设置, 返回由_datetime_或_expression_表示的时间值。</span><span class="sxs-lookup"><span data-stu-id="989d6-104">Returns the time value represented by  _datetime_ or  _expression_, based on the system's Region and Language settings.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="989d6-105">语法</span><span class="sxs-lookup"><span data-stu-id="989d6-105">Syntax</span></span>

<span data-ttu-id="989d6-106">TIMEVALUE ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="989d6-106">TIMEVALUE(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="989d6-107">参数</span><span class="sxs-lookup"><span data-stu-id="989d6-107">Parameters</span></span>

|<span data-ttu-id="989d6-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="989d6-108">**Name**</span></span>|<span data-ttu-id="989d6-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="989d6-109">**Required/Optional**</span></span>|<span data-ttu-id="989d6-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="989d6-110">**Data Type**</span></span>|<span data-ttu-id="989d6-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="989d6-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="989d6-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="989d6-112">_datetime_</span></span> <br/> |<span data-ttu-id="989d6-113">必需</span><span class="sxs-lookup"><span data-stu-id="989d6-113">Required</span></span>  <br/> |<span data-ttu-id="989d6-114">**String**</span><span class="sxs-lookup"><span data-stu-id="989d6-114">**String**</span></span> <br/> | <span data-ttu-id="989d6-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="989d6-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="989d6-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="989d6-116">_expression_</span></span> <br/> |<span data-ttu-id="989d6-117">必需</span><span class="sxs-lookup"><span data-stu-id="989d6-117">Required</span></span>  <br/> |<span data-ttu-id="989d6-118">**相同**</span><span class="sxs-lookup"><span data-stu-id="989d6-118">**Varies**</span></span> <br/> | <span data-ttu-id="989d6-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="989d6-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="989d6-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="989d6-120">_lcid_</span></span> <br/> |<span data-ttu-id="989d6-121">可选</span><span class="sxs-lookup"><span data-stu-id="989d6-121">Optional</span></span>  <br/> |<span data-ttu-id="989d6-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="989d6-122">**Number**</span></span> <br/> |<span data-ttu-id="989d6-123">用于计算非本地日期时间的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="989d6-123">The locale identifier to be used in evaluating a nonlocal datetime.</span></span> <span data-ttu-id="989d6-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="989d6-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="989d6-125">说明</span><span class="sxs-lookup"><span data-stu-id="989d6-125">Remarks</span></span>

<span data-ttu-id="989d6-126">_datetime_或_expression_中的任何日期部分都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="989d6-126">Any date component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="989d6-127">如果_datetime_缺失或无法转换为有效的结果, 则此函数返回一个 #VALUE!</span><span class="sxs-lookup"><span data-stu-id="989d6-127">If  _datetime_ is missing or cannot be converted to a valid result, this function returns a #VALUE!</span></span> <span data-ttu-id="989d6-128">误差.</span><span class="sxs-lookup"><span data-stu-id="989d6-128">error.</span></span> 
  
<span data-ttu-id="989d6-129">TIMEVALUE 函数还接受一个数值, 其中结果的__ 小数部分表示自午夜以来的一天中的某一天。</span><span class="sxs-lookup"><span data-stu-id="989d6-129">The TIMEVALUE function also accepts a single number value for  _expression_ where the decimal portion of the result represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="989d6-130">示例 1</span><span class="sxs-lookup"><span data-stu-id="989d6-130">Example 1</span></span>

<span data-ttu-id="989d6-131">TIMEVALUE("6:00 AM")</span><span class="sxs-lookup"><span data-stu-id="989d6-131">TIMEVALUE("6:00 AM")</span></span>
  
<span data-ttu-id="989d6-132">返回表示上午 6:00 的值。</span><span class="sxs-lookup"><span data-stu-id="989d6-132">Returns the value representing 6:00 AM.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="989d6-133">示例 2</span><span class="sxs-lookup"><span data-stu-id="989d6-133">Example 2</span></span>

<span data-ttu-id="989d6-134">TIMEVALUE("14:30")+4 eh.+30 em.</span><span class="sxs-lookup"><span data-stu-id="989d6-134">TIMEVALUE("14:30")+4 eh.+30 em.</span></span>
  
<span data-ttu-id="989d6-135">返回表示下午 7:00:00 的值。</span><span class="sxs-lookup"><span data-stu-id="989d6-135">Returns the value representing 19:00:00.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="989d6-136">示例 3</span><span class="sxs-lookup"><span data-stu-id="989d6-136">Example 3</span></span>

<span data-ttu-id="989d6-137">TIMEVALUE("11 AM, July 1, 1997")</span><span class="sxs-lookup"><span data-stu-id="989d6-137">TIMEVALUE("11 AM, July 1, 1997")</span></span>
  
<span data-ttu-id="989d6-138">返回表示上午 11:00 的值。</span><span class="sxs-lookup"><span data-stu-id="989d6-138">Returns the value representing 11:00 AM.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="989d6-139">示例 4</span><span class="sxs-lookup"><span data-stu-id="989d6-139">Example 4</span></span>

<span data-ttu-id="989d6-140">TIMEVALUE (0.6337)</span><span class="sxs-lookup"><span data-stu-id="989d6-140">TIMEVALUE(0.6337)</span></span>
  
<span data-ttu-id="989d6-141">返回表示下午 3:12:32 的值。</span><span class="sxs-lookup"><span data-stu-id="989d6-141">Returns the value representing 15:12:32.</span></span>
  
## <a name="example-5"></a><span data-ttu-id="989d6-142">示例 5</span><span class="sxs-lookup"><span data-stu-id="989d6-142">Example 5</span></span>

<span data-ttu-id="989d6-143">TIMEVALUE ("7:89")</span><span class="sxs-lookup"><span data-stu-id="989d6-143">TIMEVALUE("7:89")</span></span>
  
<span data-ttu-id="989d6-p103">返回 #VALUE! 错误。</span><span class="sxs-lookup"><span data-stu-id="989d6-p103">Returns a #VALUE! error.</span></span>
  

