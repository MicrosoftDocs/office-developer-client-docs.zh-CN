---
title: WEEKDAY 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251512
localization_priority: Normal
ms.assetid: f2625ef8-3bdb-5a8d-48b9-149be0592533
description: 返回一个整数, 1 到 7, 代表 datetime 或 expression 中的工作日。
ms.openlocfilehash: 7c5d467d8c6ff14b99b64b8b0462d21d0b769998
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404804"
---
# <a name="weekday-function-visioshapesheet"></a><span data-ttu-id="32479-103">WEEKDAY 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="32479-103">WEEKDAY Function (VisioShapeSheet)</span></span>

<span data-ttu-id="32479-104">返回一个整数, 1 到 7, 代表_datetime_或_expression_中的工作日。</span><span class="sxs-lookup"><span data-stu-id="32479-104">Returns an integer, 1 to 7, representing the weekday in  _datetime_ or  _expression_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="32479-105">语法</span><span class="sxs-lookup"><span data-stu-id="32479-105">Syntax</span></span>

<span data-ttu-id="32479-106">工作日 ("\* \* *datetime* \* *" |* **表达式** \* [, \* \* *lcid* \* \*])</span><span class="sxs-lookup"><span data-stu-id="32479-106">WEEKDAY(" \*\* *datetime* \*\* "| \*\* *expression* \*\* [, \*\* *lcid* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="32479-107">参数</span><span class="sxs-lookup"><span data-stu-id="32479-107">Parameters</span></span>

|<span data-ttu-id="32479-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="32479-108">**Name**</span></span>|<span data-ttu-id="32479-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="32479-109">**Required/Optional**</span></span>|<span data-ttu-id="32479-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="32479-110">**Data Type**</span></span>|<span data-ttu-id="32479-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="32479-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="32479-112">_datetime_</span><span class="sxs-lookup"><span data-stu-id="32479-112">_datetime_</span></span> <br/> |<span data-ttu-id="32479-113">必需</span><span class="sxs-lookup"><span data-stu-id="32479-113">Required</span></span>  <br/> |<span data-ttu-id="32479-114">**String**</span><span class="sxs-lookup"><span data-stu-id="32479-114">**String**</span></span> <br/> | <span data-ttu-id="32479-115">任何通常被识别为日期和时间的字符串或对包含日期和时间的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="32479-115">Any string commonly recognized as a date and time or a reference to a cell containing a date and time.</span></span>  <br/> |
| <span data-ttu-id="32479-116">_expression_</span><span class="sxs-lookup"><span data-stu-id="32479-116">_expression_</span></span> <br/> |<span data-ttu-id="32479-117">必需</span><span class="sxs-lookup"><span data-stu-id="32479-117">Required</span></span>  <br/> |<span data-ttu-id="32479-118">**相同**</span><span class="sxs-lookup"><span data-stu-id="32479-118">**Varies**</span></span> <br/> |<span data-ttu-id="32479-119">任何生成日期和时间的表达式。</span><span class="sxs-lookup"><span data-stu-id="32479-119">Any expression that yields a date and time.</span></span>  <br/> |
| <span data-ttu-id="32479-120">_lcid_</span><span class="sxs-lookup"><span data-stu-id="32479-120">_lcid_</span></span> <br/> |<span data-ttu-id="32479-121">可选</span><span class="sxs-lookup"><span data-stu-id="32479-121">Optional</span></span>  <br/> |<span data-ttu-id="32479-122">**数值**</span><span class="sxs-lookup"><span data-stu-id="32479-122">**Numeric**</span></span> <br/> |<span data-ttu-id="32479-123">用于计算非本地日期时间的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="32479-123">The locale identifier to be used in evaluating a nonlocal datetime.</span></span> <span data-ttu-id="32479-124">区域设置标识符是系统头文件中描述的一个数字。</span><span class="sxs-lookup"><span data-stu-id="32479-124">The locale identifier is a number described in the system header files.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="32479-125">返回值</span><span class="sxs-lookup"><span data-stu-id="32479-125">Return value</span></span>

<span data-ttu-id="32479-126">整数</span><span class="sxs-lookup"><span data-stu-id="32479-126">Integer</span></span>
  
## <a name="remarks"></a><span data-ttu-id="32479-127">说明</span><span class="sxs-lookup"><span data-stu-id="32479-127">Remarks</span></span>

<span data-ttu-id="32479-128">_datetime_或_expression_中的时间部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="32479-128">The time component in  _datetime_ or  _expression_ is discarded.</span></span> 
  
<span data-ttu-id="32479-129">结果对应于星期一 (1) 到星期日 (7)。</span><span class="sxs-lookup"><span data-stu-id="32479-129">The result corresponds to Monday (1) through Sunday (7).</span></span> <span data-ttu-id="32479-130">无舍入过程。</span><span class="sxs-lookup"><span data-stu-id="32479-130">No rounding is done.</span></span> <span data-ttu-id="32479-131">如果_datetime_缺失或无法解释为有效的日期或时间, 则该函数将返回 #VALUE!</span><span class="sxs-lookup"><span data-stu-id="32479-131">If  _datetime_ is missing or cannot be interpreted as a valid date or time, the function returns a #VALUE!</span></span> <span data-ttu-id="32479-132">误差.</span><span class="sxs-lookup"><span data-stu-id="32479-132">error.</span></span> 
  
<span data-ttu-id="32479-133">WEEKDAY 函数还接受单个数值_表达式_, 其中结果的整数部分代表自1899年12月30日的天数。</span><span class="sxs-lookup"><span data-stu-id="32479-133">The WEEKDAY function also accepts a single number value for  _expression_ where the integer portion of the result represents the number of days since December 30, 1899.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="32479-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="32479-134">Example 1</span></span>

<span data-ttu-id="32479-135">WEEKDAY("May 30, 1999")</span><span class="sxs-lookup"><span data-stu-id="32479-135">WEEKDAY("May 30, 1999")</span></span>
  
<span data-ttu-id="32479-136">返回 7。</span><span class="sxs-lookup"><span data-stu-id="32479-136">Returns 7.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="32479-137">示例 2</span><span class="sxs-lookup"><span data-stu-id="32479-137">Example 2</span></span>

<span data-ttu-id="32479-138">WEEKDAY(DATEVALUE("May 30, 1999")+2 ed.)</span><span class="sxs-lookup"><span data-stu-id="32479-138">WEEKDAY(DATEVALUE("May 30, 1999")+2 ed.)</span></span>
  
<span data-ttu-id="32479-139">返回 2。</span><span class="sxs-lookup"><span data-stu-id="32479-139">Returns 2.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="32479-140">示例 3</span><span class="sxs-lookup"><span data-stu-id="32479-140">Example 3</span></span>

<span data-ttu-id="32479-141">工作日 (35880.6337)</span><span class="sxs-lookup"><span data-stu-id="32479-141">WEEKDAY(35880.6337)</span></span>
  
<span data-ttu-id="32479-142">返回 4。</span><span class="sxs-lookup"><span data-stu-id="32479-142">Returns 4.</span></span>
  

