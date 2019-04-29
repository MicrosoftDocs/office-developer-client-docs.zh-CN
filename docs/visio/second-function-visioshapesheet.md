---
title: SECOND 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251495
localization_priority: Normal
ms.assetid: 22005976-37c0-d2be-8e34-8aee8458e4be
description: 返回一个整数, 0 到 59, 表示日期时间或表达式的秒部分。
ms.openlocfilehash: c23bbded12a3886fe3bd4dd2a3c3ba1bd6d11619
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404874"
---
# <a name="second-function-visioshapesheet"></a><span data-ttu-id="83af4-103">SECOND 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="83af4-103">SECOND Function (VisioShapeSheet)</span></span>

<span data-ttu-id="83af4-104">返回一个整数, 0 到 59, 表示_日期时间_或_表达式_的秒部分。</span><span class="sxs-lookup"><span data-stu-id="83af4-104">Returns an integer, 0 to 59, that represents the seconds component of  _datetime_ or  _expression_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="83af4-105">语法</span><span class="sxs-lookup"><span data-stu-id="83af4-105">Syntax</span></span>

<span data-ttu-id="83af4-106">SECOND ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="83af4-106">SECOND(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="83af4-107">参数</span><span class="sxs-lookup"><span data-stu-id="83af4-107">Parameters</span></span>

|<span data-ttu-id="83af4-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="83af4-108">**Name**</span></span>|<span data-ttu-id="83af4-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="83af4-109">**Required/Optional**</span></span>|<span data-ttu-id="83af4-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="83af4-110">**Data Type**</span></span>|<span data-ttu-id="83af4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="83af4-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="83af4-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="83af4-112">_datetime_</span></span> <br/> |<span data-ttu-id="83af4-113">必需</span><span class="sxs-lookup"><span data-stu-id="83af4-113">Required</span></span>  <br/> |<span data-ttu-id="83af4-114">**String**</span><span class="sxs-lookup"><span data-stu-id="83af4-114">**String**</span></span> <br/> |<span data-ttu-id="83af4-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="83af4-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="83af4-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="83af4-116">_expression_</span></span> <br/> |<span data-ttu-id="83af4-117">必需</span><span class="sxs-lookup"><span data-stu-id="83af4-117">Required</span></span>  <br/> |<span data-ttu-id="83af4-118">**String**</span><span class="sxs-lookup"><span data-stu-id="83af4-118">**String**</span></span> <br/> | <span data-ttu-id="83af4-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="83af4-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="83af4-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="83af4-120">_lcid_</span></span> <br/> |<span data-ttu-id="83af4-121">可选</span><span class="sxs-lookup"><span data-stu-id="83af4-121">Optional</span></span>  <br/> |<span data-ttu-id="83af4-122">**数值**</span><span class="sxs-lookup"><span data-stu-id="83af4-122">**Numeric**</span></span> <br/> |<span data-ttu-id="83af4-123">用于计算非本地_datetime_的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="83af4-123">The locale identifier to be used in evaluating a nonlocal  _datetime_.</span></span> <span data-ttu-id="83af4-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="83af4-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="83af4-125">返回值</span><span class="sxs-lookup"><span data-stu-id="83af4-125">Return value</span></span>

<span data-ttu-id="83af4-126">整数</span><span class="sxs-lookup"><span data-stu-id="83af4-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="83af4-127">说明</span><span class="sxs-lookup"><span data-stu-id="83af4-127">Remarks</span></span>

<span data-ttu-id="83af4-128">_datetime_或_expression_中的日期部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="83af4-128">The date component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="83af4-129">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="83af4-129">No rounding is done.</span></span> <span data-ttu-id="83af4-130">如果_datetime_缺失或无法转换为有效的结果, 则此函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="83af4-130">If  _datetime_ is missing or cannot be converted to a valid result, this function returns an error.</span></span> 
  
<span data-ttu-id="83af4-131">第二个函数还接受一个数值, 其中__ 结果的小数部分表示自午夜以来的一天中的某一天。</span><span class="sxs-lookup"><span data-stu-id="83af4-131">The SECOND function also accepts a single number value for  _expression_ where the decimal portion of the result represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="83af4-132">示例 1</span><span class="sxs-lookup"><span data-stu-id="83af4-132">Example 1</span></span>

<span data-ttu-id="83af4-133">第二个 ("05/30/1997 13:45:32")</span><span class="sxs-lookup"><span data-stu-id="83af4-133">SECOND("05/30/1997 13:45:32")</span></span>
  
<span data-ttu-id="83af4-134">返回 32。</span><span class="sxs-lookup"><span data-stu-id="83af4-134">Returns 32.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="83af4-135">示例 2</span><span class="sxs-lookup"><span data-stu-id="83af4-135">Example 2</span></span>

<span data-ttu-id="83af4-136">SECOND(TIMEVALUE("May 30, 1996 12:07:45") + 7 es.)</span><span class="sxs-lookup"><span data-stu-id="83af4-136">SECOND(TIMEVALUE("May 30, 1996 12:07:45") + 7 es.)</span></span>
  
<span data-ttu-id="83af4-137">返回 52。</span><span class="sxs-lookup"><span data-stu-id="83af4-137">Returns 52.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="83af4-138">示例 3</span><span class="sxs-lookup"><span data-stu-id="83af4-138">Example 3</span></span>

<span data-ttu-id="83af4-139">SECOND (0.6337)</span><span class="sxs-lookup"><span data-stu-id="83af4-139">SECOND(0.6337)</span></span>
  
<span data-ttu-id="83af4-140">返回 32。</span><span class="sxs-lookup"><span data-stu-id="83af4-140">Returns 32.</span></span>
  

