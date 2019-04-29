---
title: MONTH 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251467
localization_priority: Normal
ms.assetid: e099dbb3-c591-d934-5cfd-7728b10bd8dc
description: 返回一个1到12之间的整数, 该整数表示一个月。
ms.openlocfilehash: 71ecc7992839c871780e9b703377db37279246e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431972"
---
# <a name="month-function-visioshapesheet"></a><span data-ttu-id="a1c8a-103">MONTH 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="a1c8a-103">MONTH Function (VisioShapeSheet)</span></span>

<span data-ttu-id="a1c8a-104">返回一个1到12之间的整数, 该整数表示一个月。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-104">Returns an integer from 1 to 12 that represents a month.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a1c8a-105">语法</span><span class="sxs-lookup"><span data-stu-id="a1c8a-105">Syntax</span></span>

<span data-ttu-id="a1c8a-106">MONTH ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="a1c8a-106">MONTH(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a1c8a-107">参数</span><span class="sxs-lookup"><span data-stu-id="a1c8a-107">Parameters</span></span>

|<span data-ttu-id="a1c8a-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-108">**Name**</span></span>|<span data-ttu-id="a1c8a-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-109">**Required/Optional**</span></span>|<span data-ttu-id="a1c8a-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-110">**Data Type**</span></span>|<span data-ttu-id="a1c8a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a1c8a-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="a1c8a-112">_datetime_</span></span> <br/> |<span data-ttu-id="a1c8a-113">必需</span><span class="sxs-lookup"><span data-stu-id="a1c8a-113">Required</span></span>  <br/> |<span data-ttu-id="a1c8a-114">**String**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-114">**String**</span></span> <br/> |<span data-ttu-id="a1c8a-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="a1c8a-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="a1c8a-116">_expression_</span></span> <br/> |<span data-ttu-id="a1c8a-117">必需</span><span class="sxs-lookup"><span data-stu-id="a1c8a-117">Required</span></span>  <br/> |<span data-ttu-id="a1c8a-118">**String**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-118">**String**</span></span> <br/> | <span data-ttu-id="a1c8a-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="a1c8a-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="a1c8a-120">_lcid_</span></span> <br/> |<span data-ttu-id="a1c8a-121">可选</span><span class="sxs-lookup"><span data-stu-id="a1c8a-121">Optional</span></span>  <br/> |<span data-ttu-id="a1c8a-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="a1c8a-122">**Number**</span></span> <br/> |<span data-ttu-id="a1c8a-123">用于计算非本地日期时间的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-123">The locale identifier to be used in evaluating a nonlocal datetime.</span></span> <span data-ttu-id="a1c8a-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="a1c8a-125">返回值</span><span class="sxs-lookup"><span data-stu-id="a1c8a-125">Return value</span></span>

<span data-ttu-id="a1c8a-126">整数</span><span class="sxs-lookup"><span data-stu-id="a1c8a-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a1c8a-127">说明</span><span class="sxs-lookup"><span data-stu-id="a1c8a-127">Remarks</span></span>

<span data-ttu-id="a1c8a-128">_datetime_或_expression_的时间部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-128">The time component of  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="a1c8a-p102">无舍入过程。如果输入的字符串缺失或无法转换为有效的结果，则 MONTH 函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-p102">No rounding is done. If the input string is missing or cannot be converted to a valid result, the MONTH function returns an error.</span></span>
  
<span data-ttu-id="a1c8a-131">返回的值根据系统当前“区域设置”中的短日期样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-131">The returned value is formatted according to the short date style set by the system's current Regional Settings.</span></span>
  
<span data-ttu-id="a1c8a-132">MONTH 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-132">The MONTH function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="a1c8a-133">示例 1</span><span class="sxs-lookup"><span data-stu-id="a1c8a-133">Example 1</span></span>

<span data-ttu-id="a1c8a-134">MONTH("May 30, 1999 13:45:24")</span><span class="sxs-lookup"><span data-stu-id="a1c8a-134">MONTH("May 30, 1999 13:45:24")</span></span>
  
<span data-ttu-id="a1c8a-135">返回 5。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-135">Returns 5.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="a1c8a-136">示例 2</span><span class="sxs-lookup"><span data-stu-id="a1c8a-136">Example 2</span></span>

<span data-ttu-id="a1c8a-137">MONTH(DATEVALUE("May 30, 1999")+7 ed.)</span><span class="sxs-lookup"><span data-stu-id="a1c8a-137">MONTH(DATEVALUE("May 30, 1999")+7 ed.)</span></span>
  
<span data-ttu-id="a1c8a-138">返回 6。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-138">Returns 6.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="a1c8a-139">示例 3</span><span class="sxs-lookup"><span data-stu-id="a1c8a-139">Example 3</span></span>

<span data-ttu-id="a1c8a-140">月 (35580.6337)</span><span class="sxs-lookup"><span data-stu-id="a1c8a-140">MONTH(35580.6337)</span></span>
  
<span data-ttu-id="a1c8a-141">返回 5。</span><span class="sxs-lookup"><span data-stu-id="a1c8a-141">Returns 5.</span></span>
  

