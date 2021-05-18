---
title: DATEVALUE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251414
localization_priority: Normal
ms.assetid: 514a4053-7729-ec82-c42f-5b780e48cd2a
description: 返回 datetime 或 expression 表示的日期值。
ms.openlocfilehash: d5bc1865e76940508ddb67a9b3d2122dc7c43a50
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360310"
---
# <a name="datevalue-function-visioshapesheet"></a><span data-ttu-id="11163-103">DATEVALUE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="11163-103">DATEVALUE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="11163-104">返回 datetime 或  _expression 表示_ 的日期  _值_。</span><span class="sxs-lookup"><span data-stu-id="11163-104">Returns the date value represented by  _datetime_ or  _expression_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="11163-105">语法</span><span class="sxs-lookup"><span data-stu-id="11163-105">Syntax</span></span>

<span data-ttu-id="11163-106">DATEVALUE (" \*\* *datetime* \*\* "|\*\* *expression* \*\* [， \*\* *lcid* \*\* ]) </span><span class="sxs-lookup"><span data-stu-id="11163-106">DATEVALUE(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="11163-107">参数</span><span class="sxs-lookup"><span data-stu-id="11163-107">Parameters</span></span>

|<span data-ttu-id="11163-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="11163-108">**Name**</span></span>|<span data-ttu-id="11163-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="11163-109">**Required/Optional**</span></span>|<span data-ttu-id="11163-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="11163-110">**Data Type**</span></span>|<span data-ttu-id="11163-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="11163-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="11163-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="11163-112">_datetime_</span></span> <br/> |<span data-ttu-id="11163-113">必需</span><span class="sxs-lookup"><span data-stu-id="11163-113">Required</span></span>  <br/> |<span data-ttu-id="11163-114">**String**</span><span class="sxs-lookup"><span data-stu-id="11163-114">**String**</span></span> <br/> |<span data-ttu-id="11163-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="11163-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="11163-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="11163-116">_expression_</span></span> <br/> |<span data-ttu-id="11163-117">必需</span><span class="sxs-lookup"><span data-stu-id="11163-117">Required</span></span>  <br/> |<span data-ttu-id="11163-118">**String**</span><span class="sxs-lookup"><span data-stu-id="11163-118">**String**</span></span> <br/> |<span data-ttu-id="11163-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="11163-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="11163-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="11163-120">_lcid_</span></span> <br/> |<span data-ttu-id="11163-121">可选</span><span class="sxs-lookup"><span data-stu-id="11163-121">Optional</span></span>  <br/> |<span data-ttu-id="11163-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="11163-122">**Number**</span></span> <br/> |<span data-ttu-id="11163-p101">指定用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="11163-p101">Specifies the locale identifier to be used in evaluating a non-local datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="11163-125">返回值</span><span class="sxs-lookup"><span data-stu-id="11163-125">Return value</span></span>

<span data-ttu-id="11163-126">Datetime</span><span class="sxs-lookup"><span data-stu-id="11163-126">Datetime</span></span>
  
## <a name="remarks"></a><span data-ttu-id="11163-127">备注</span><span class="sxs-lookup"><span data-stu-id="11163-127">Remarks</span></span>

<span data-ttu-id="11163-128">datetime 或 expression  *中的*  任意  *时间*  组件都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="11163-128">Any time component in  *datetime*  or  *expression*  is discarded.</span></span> 
  
<span data-ttu-id="11163-129">如果  *datetime*  缺失或无法转换为有效结果，则 DATEVALUE 将返回一#VALUE！</span><span class="sxs-lookup"><span data-stu-id="11163-129">If  *datetime*  is missing or cannot be converted to a valid result, DATEVALUE returns a #VALUE!</span></span> <span data-ttu-id="11163-130">error。</span><span class="sxs-lookup"><span data-stu-id="11163-130">error.</span></span> 
  
<span data-ttu-id="11163-131">返回的值使用由系统当前“区域设置”所设置的短日期样式显示。</span><span class="sxs-lookup"><span data-stu-id="11163-131">The returned value is displayed using the short date style set by the system's current Regional Settings.</span></span> 
  
<span data-ttu-id="11163-132">DATEVALUE 函数还接受单个数值的  *expression，*  其中结果的整数部分表示自 1899 年 12 月 30 日起的日期。</span><span class="sxs-lookup"><span data-stu-id="11163-132">The DATEVALUE function also accepts a single number value for  *expression*  where the integer portion of the result represents the days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="11163-133">示例 1</span><span class="sxs-lookup"><span data-stu-id="11163-133">Example 1</span></span>

<span data-ttu-id="11163-134">DATEVALUE(NOW( ))+5 ed.</span><span class="sxs-lookup"><span data-stu-id="11163-134">DATEVALUE(NOW( ))+5 ed.</span></span>
  
<span data-ttu-id="11163-135">返回从现在起五天后的日期。</span><span class="sxs-lookup"><span data-stu-id="11163-135">Returns the date five days from now.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="11163-136">示例 2</span><span class="sxs-lookup"><span data-stu-id="11163-136">Example 2</span></span>

<span data-ttu-id="11163-137">DATEVALUE ("7/19/1995 12：30") </span><span class="sxs-lookup"><span data-stu-id="11163-137">DATEVALUE("7/19/1995 12:30")</span></span>
  
<span data-ttu-id="11163-138">返回该日期。</span><span class="sxs-lookup"><span data-stu-id="11163-138">Returns the date.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="11163-139">示例 3</span><span class="sxs-lookup"><span data-stu-id="11163-139">Example 3</span></span>

<span data-ttu-id="11163-140">DATEVALUE("May 33, 1997")</span><span class="sxs-lookup"><span data-stu-id="11163-140">DATEVALUE("May 33, 1997")</span></span>
  
<span data-ttu-id="11163-p103">返回 #VALUE! 错误。</span><span class="sxs-lookup"><span data-stu-id="11163-p103">Returns a #VALUE! error.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="11163-143">示例 4</span><span class="sxs-lookup"><span data-stu-id="11163-143">Example 4</span></span>

<span data-ttu-id="11163-144">DATEVALUE (35580.6337) </span><span class="sxs-lookup"><span data-stu-id="11163-144">DATEVALUE(35580.6337)</span></span>
  
<span data-ttu-id="11163-145">返回 5/30/1997。</span><span class="sxs-lookup"><span data-stu-id="11163-145">Returns 5/30/1997.</span></span>
  

