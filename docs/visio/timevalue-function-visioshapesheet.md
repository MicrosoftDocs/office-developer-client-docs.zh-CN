---
title: TIMEVALUE Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251507
localization_priority: Normal
ms.assetid: 53579e0e-fcec-e745-0207-3861b5efa333
description: 返回表示的时间值的 datetime 或 expression 中，将根据系统的区域和语言设置。
ms.openlocfilehash: e75607d19dc7062af717823c13f580cb44c9406b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781522"
---
# <a name="timevalue-function-visioshapesheet"></a><span data-ttu-id="c33a3-103">TIMEVALUE Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="c33a3-103">TIMEVALUE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="c33a3-104">_Datetime_或_expression_返回表示的时间值将基于系统的区域和语言设置。</span><span class="sxs-lookup"><span data-stu-id="c33a3-104">Returns the time value represented by  _datetime_ or  _expression_, based on the system's Region and Language settings.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c33a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="c33a3-105">Syntax</span></span>

<span data-ttu-id="c33a3-106">TIMEVALUE ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *])</span><span class="sxs-lookup"><span data-stu-id="c33a3-106">TIMEVALUE(" ** *datetime* ** "| ** *expression* ** [, ** *lcid* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c33a3-107">参数</span><span class="sxs-lookup"><span data-stu-id="c33a3-107">Parameters</span></span>

|<span data-ttu-id="c33a3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c33a3-108">**Name**</span></span>|<span data-ttu-id="c33a3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c33a3-109">**Required/Optional**</span></span>|<span data-ttu-id="c33a3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c33a3-110">**Data Type**</span></span>|<span data-ttu-id="c33a3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c33a3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c33a3-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="c33a3-112">_datetime_</span></span> <br/> |<span data-ttu-id="c33a3-113">必需</span><span class="sxs-lookup"><span data-stu-id="c33a3-113">Required</span></span>  <br/> |<span data-ttu-id="c33a3-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c33a3-114">**String**</span></span> <br/> | <span data-ttu-id="c33a3-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c33a3-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="c33a3-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="c33a3-116">_expression_</span></span> <br/> |<span data-ttu-id="c33a3-117">必需</span><span class="sxs-lookup"><span data-stu-id="c33a3-117">Required</span></span>  <br/> |<span data-ttu-id="c33a3-118">**因情况而异**</span><span class="sxs-lookup"><span data-stu-id="c33a3-118">**Varies**</span></span> <br/> | <span data-ttu-id="c33a3-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="c33a3-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="c33a3-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="c33a3-120">_lcid_</span></span> <br/> |<span data-ttu-id="c33a3-121">可选</span><span class="sxs-lookup"><span data-stu-id="c33a3-121">Optional</span></span>  <br/> |<span data-ttu-id="c33a3-122">**编号**</span><span class="sxs-lookup"><span data-stu-id="c33a3-122">**Number**</span></span> <br/> |<span data-ttu-id="c33a3-p101">用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="c33a3-p101">The locale identifier to be used in evaluating a nonlocal datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c33a3-125">注解</span><span class="sxs-lookup"><span data-stu-id="c33a3-125">Remarks</span></span>

<span data-ttu-id="c33a3-126">_Datetime_或_expression_中的任何日期部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="c33a3-126">Any date component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="c33a3-127">如果_datetime_缺失或无法转换为有效的结果，则此函数返回 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="c33a3-127">If  _datetime_ is missing or cannot be converted to a valid result, this function returns a #VALUE!</span></span> <span data-ttu-id="c33a3-128">错误。</span><span class="sxs-lookup"><span data-stu-id="c33a3-128">error.</span></span> 
  
<span data-ttu-id="c33a3-129">TIMEVALUE 函数还接受值为单一数值的_表达式_，其中结果的小数部分代表自午夜开始的一天的时间占。</span><span class="sxs-lookup"><span data-stu-id="c33a3-129">The TIMEVALUE function also accepts a single number value for  _expression_ where the decimal portion of the result represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="c33a3-130">示例 1</span><span class="sxs-lookup"><span data-stu-id="c33a3-130">Example 1</span></span>

<span data-ttu-id="c33a3-131">TIMEVALUE("6:00 AM")</span><span class="sxs-lookup"><span data-stu-id="c33a3-131">TIMEVALUE("6:00 AM")</span></span>
  
<span data-ttu-id="c33a3-132">返回表示上午 6:00 的值。</span><span class="sxs-lookup"><span data-stu-id="c33a3-132">Returns the value representing 6:00 AM.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="c33a3-133">示例 2</span><span class="sxs-lookup"><span data-stu-id="c33a3-133">Example 2</span></span>

<span data-ttu-id="c33a3-134">TIMEVALUE("14:30")+4 eh.+30 em.</span><span class="sxs-lookup"><span data-stu-id="c33a3-134">TIMEVALUE("14:30")+4 eh.+30 em.</span></span>
  
<span data-ttu-id="c33a3-135">返回表示下午 7:00:00 的值。</span><span class="sxs-lookup"><span data-stu-id="c33a3-135">Returns the value representing 19:00:00.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="c33a3-136">示例 3</span><span class="sxs-lookup"><span data-stu-id="c33a3-136">Example 3</span></span>

<span data-ttu-id="c33a3-137">TIMEVALUE("11 AM, July 1, 1997")</span><span class="sxs-lookup"><span data-stu-id="c33a3-137">TIMEVALUE("11 AM, July 1, 1997")</span></span>
  
<span data-ttu-id="c33a3-138">返回表示上午 11:00 的值。</span><span class="sxs-lookup"><span data-stu-id="c33a3-138">Returns the value representing 11:00 AM.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="c33a3-139">示例 4</span><span class="sxs-lookup"><span data-stu-id="c33a3-139">Example 4</span></span>

<span data-ttu-id="c33a3-140">TIMEVALUE(0.6337)</span><span class="sxs-lookup"><span data-stu-id="c33a3-140">TIMEVALUE(0.6337)</span></span>
  
<span data-ttu-id="c33a3-141">返回表示下午 3:12:32 的值。</span><span class="sxs-lookup"><span data-stu-id="c33a3-141">Returns the value representing 15:12:32.</span></span>
  
## <a name="example-5"></a><span data-ttu-id="c33a3-142">示例 5</span><span class="sxs-lookup"><span data-stu-id="c33a3-142">Example 5</span></span>

<span data-ttu-id="c33a3-143">TIMEVALUE("7:89")</span><span class="sxs-lookup"><span data-stu-id="c33a3-143">TIMEVALUE("7:89")</span></span>
  
<span data-ttu-id="c33a3-p103">返回 #VALUE! 错误。</span><span class="sxs-lookup"><span data-stu-id="c33a3-p103">Returns a #VALUE! error.</span></span>
  

