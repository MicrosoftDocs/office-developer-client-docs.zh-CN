---
title: HOUR 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251437
localization_priority: Normal
ms.assetid: 2a21d6f9-bad6-92ab-6d36-477bcb9d7f17
description: 返回一个表示整数，0 到 23 datetime 或 expression 的一天的。
ms.openlocfilehash: 9cfe8c88a4a4d73be23b2ac230b0cfabc955c004
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780408"
---
# <a name="hour-function-visioshapesheet"></a><span data-ttu-id="7fdef-103">HOUR 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="7fdef-103">HOUR Function (VisioShapeSheet)</span></span>

<span data-ttu-id="7fdef-104">返回一个表示整数，0 到 23 _datetime_或_expression_的一天的。</span><span class="sxs-lookup"><span data-stu-id="7fdef-104">Returns an integer, 0 to 23, representing the hour of the day of  _datetime_ or  _expression_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7fdef-105">语法</span><span class="sxs-lookup"><span data-stu-id="7fdef-105">Syntax</span></span>

<span data-ttu-id="7fdef-106">小时 ("* * *datetime* * *"|* **表达式** * [，* * *lcid* * *])</span><span class="sxs-lookup"><span data-stu-id="7fdef-106">HOUR(" ** *datetime* ** "| ** *expression* ** [, ** *lcid* ** ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7fdef-107">参数</span><span class="sxs-lookup"><span data-stu-id="7fdef-107">Parameters</span></span>

|<span data-ttu-id="7fdef-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="7fdef-108">**Name**</span></span>|<span data-ttu-id="7fdef-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7fdef-109">**Required/Optional**</span></span>|<span data-ttu-id="7fdef-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7fdef-110">**Data Type**</span></span>|<span data-ttu-id="7fdef-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="7fdef-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7fdef-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="7fdef-112">_datetime_</span></span> <br/> |<span data-ttu-id="7fdef-113">必需</span><span class="sxs-lookup"><span data-stu-id="7fdef-113">Required</span></span>  <br/> |<span data-ttu-id="7fdef-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="7fdef-114">**String**</span></span> <br/> | <span data-ttu-id="7fdef-115">通常被识别为表示日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="7fdef-115">A string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="7fdef-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="7fdef-116">_expression_</span></span> <br/> |<span data-ttu-id="7fdef-117">必需</span><span class="sxs-lookup"><span data-stu-id="7fdef-117">Required</span></span>  <br/> |<span data-ttu-id="7fdef-118">**而异**</span><span class="sxs-lookup"><span data-stu-id="7fdef-118">**Varies**</span></span> <br/> |<span data-ttu-id="7fdef-119">生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="7fdef-119">An expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="7fdef-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="7fdef-120">_lcid_</span></span> <br/> |<span data-ttu-id="7fdef-121">可选</span><span class="sxs-lookup"><span data-stu-id="7fdef-121">Optional</span></span>  <br/> |<span data-ttu-id="7fdef-122">**编号**</span><span class="sxs-lookup"><span data-stu-id="7fdef-122">**Number**</span></span> <br/> | <span data-ttu-id="7fdef-p101">用于计算非本地日期时间的区域设置标识符。区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="7fdef-p101">A locale identifier to be used in evaluating a nonlocal datetime. The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7fdef-125">注解</span><span class="sxs-lookup"><span data-stu-id="7fdef-125">Remarks</span></span>

<span data-ttu-id="7fdef-126">*Datetime*和*expression*中的日期部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="7fdef-126">The date component in  *datetime*  and  *expression*  is discarded.</span></span> 
  
<span data-ttu-id="7fdef-127">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="7fdef-127">No rounding is done.</span></span> <span data-ttu-id="7fdef-128">如果*datetime*缺失或无法转换为有效的结果，则函数将返回错误。</span><span class="sxs-lookup"><span data-stu-id="7fdef-128">If the  *datetime*  is missing or cannot be converted to a valid result, the function returns an error.</span></span> 
  
<span data-ttu-id="7fdef-129">返回的值根据系统当前“区域设置”中设置的时间样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="7fdef-129">The returned value is formatted according to the time style set by the system's current Regional Settings.</span></span> 
  
<span data-ttu-id="7fdef-130">HOUR 函数还接受值为单一数值的*表达式*，其中结果的小数部分代表自午夜开始的一天的时间占。</span><span class="sxs-lookup"><span data-stu-id="7fdef-130">The HOUR function also accepts a single number value for  *expression*  where the decimal portion of the result represents the fraction of a day since midnight.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="7fdef-131">示例 1</span><span class="sxs-lookup"><span data-stu-id="7fdef-131">Example 1</span></span>

<span data-ttu-id="7fdef-132">HOUR("15:45")</span><span class="sxs-lookup"><span data-stu-id="7fdef-132">HOUR("15:45")</span></span>
  
<span data-ttu-id="7fdef-133">返回 15。</span><span class="sxs-lookup"><span data-stu-id="7fdef-133">Returns 15.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7fdef-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="7fdef-134">Example 2</span></span>

<span data-ttu-id="7fdef-135">HOUR("May 30, 1997 3:45:24 PM")</span><span class="sxs-lookup"><span data-stu-id="7fdef-135">HOUR("May 30, 1997 3:45:24 PM")</span></span>
  
<span data-ttu-id="7fdef-136">返回 15。</span><span class="sxs-lookup"><span data-stu-id="7fdef-136">Returns 15.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="7fdef-137">示例 3</span><span class="sxs-lookup"><span data-stu-id="7fdef-137">Example 3</span></span>

<span data-ttu-id="7fdef-138">HOUR(0.5)</span><span class="sxs-lookup"><span data-stu-id="7fdef-138">HOUR(0.5)</span></span>
  
<span data-ttu-id="7fdef-139">返回 12。</span><span class="sxs-lookup"><span data-stu-id="7fdef-139">Returns 12.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="7fdef-140">示例 4</span><span class="sxs-lookup"><span data-stu-id="7fdef-140">Example 4</span></span>

<span data-ttu-id="7fdef-141">HOUR("5/30/1997")</span><span class="sxs-lookup"><span data-stu-id="7fdef-141">HOUR("5/30/1997")</span></span>
  
<span data-ttu-id="7fdef-142">返回 0。</span><span class="sxs-lookup"><span data-stu-id="7fdef-142">Returns 0.</span></span>
  

