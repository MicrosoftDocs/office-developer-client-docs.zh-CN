---
title: CY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253223
localization_priority: Normal
ms.assetid: abb27f90-21b4-08cd-6995-9520fbcebd78
description: 返回一个货币值。
ms.openlocfilehash: 65c88d69669e2fa7f708402d9d50dfe035456edb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344987"
---
# <a name="cy-function"></a><span data-ttu-id="3ce4f-103">CY 函数</span><span class="sxs-lookup"><span data-stu-id="3ce4f-103">CY Function</span></span>

<span data-ttu-id="3ce4f-104">返回一个货币值。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-104">Returns a currency value.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3ce4f-105">语法</span><span class="sxs-lookup"><span data-stu-id="3ce4f-105">Syntax</span></span>

<span data-ttu-id="3ce4f-106">CY (\* \* *value* \* \*, \* \* *cyID* \* \*)</span><span class="sxs-lookup"><span data-stu-id="3ce4f-106">CY(\*\* *value* \*\*, \*\* *cyID* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3ce4f-107">参数</span><span class="sxs-lookup"><span data-stu-id="3ce4f-107">Parameters</span></span>

|<span data-ttu-id="3ce4f-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-108">**Name**</span></span>|<span data-ttu-id="3ce4f-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-109">**Required/Optional**</span></span>|<span data-ttu-id="3ce4f-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-110">**Data Type**</span></span>|<span data-ttu-id="3ce4f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3ce4f-112">_value_</span><span class="sxs-lookup"><span data-stu-id="3ce4f-112">_value_</span></span> <br/> |<span data-ttu-id="3ce4f-113">可选</span><span class="sxs-lookup"><span data-stu-id="3ce4f-113">Optional</span></span>  <br/> |<span data-ttu-id="3ce4f-114">**数字或字符串**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-114">**Number or String**</span></span> <br/> |<span data-ttu-id="3ce4f-115">一个数字或字符串, 其中包括特定于货币的格式。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-115">A number or a string that includes currency-specific formatting.</span></span> <span data-ttu-id="3ce4f-116">如果未指定, 则根据系统区域和语言设置中的货币样式设置货币值的格式。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-116">If not specified, the currency value is formatted according to the currency style in the system's Region and Language settings.</span></span>  <br/> |
| <span data-ttu-id="3ce4f-117">_cyID_</span><span class="sxs-lookup"><span data-stu-id="3ce4f-117">_cyID_</span></span> <br/> |<span data-ttu-id="3ce4f-118">可选</span><span class="sxs-lookup"><span data-stu-id="3ce4f-118">Optional</span></span>  <br/> |<span data-ttu-id="3ce4f-119">**Number**</span><span class="sxs-lookup"><span data-stu-id="3ce4f-119">**Number**</span></span> <br/> |<span data-ttu-id="3ce4f-120">一个数字货币 ID 或由三个字符引起来的 ISO 4217 缩写的字符串。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-120">A numeric currency ID or a three-character quoted string for the ISO 4217 abbreviation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ce4f-121">注解</span><span class="sxs-lookup"><span data-stu-id="3ce4f-121">Remarks</span></span>

<span data-ttu-id="3ce4f-122">若要指定不同的货币, 必须包含有效的_cyID_。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-122">To specify a different currency, you must include a valid  _cyID_.</span></span> <span data-ttu-id="3ce4f-123">若要获取列表，请参阅[关于货币常量](about-currency-constants.md)。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-123">For a list, see [About currency constants](about-currency-constants.md).</span></span>
  
<span data-ttu-id="3ce4f-124">如果_value_与指定的货币类型不兼容, 或者如果指定了无效参数 (如 "not number"), 则为 #VALUE!</span><span class="sxs-lookup"><span data-stu-id="3ce4f-124">If  _value_ is incompatible with the designated currency type, or if an invalid argument such as "not a number" is specified, a #VALUE!</span></span> <span data-ttu-id="3ce4f-125">错误。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-125">error is returned.</span></span> <span data-ttu-id="3ce4f-126">如果_value_大于922337203685477.5807 或小于-922337203685477.5808, 则 #VALUE!</span><span class="sxs-lookup"><span data-stu-id="3ce4f-126">If  _value_ is greater than 922,337,203,685,477.5807 or less than -922,337,203,685,477.5808, a #VALUE!</span></span> <span data-ttu-id="3ce4f-127">错误。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-127">error is returned.</span></span> 
  
<span data-ttu-id="3ce4f-128">若要更好地精确处理包含单位分数的货币值 (如 3600000000000), 请使用_值_的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-128">For better precision with very large currency values that include fractions of a unit, such as 3.6 trillion, use string arguments for  _value_.</span></span>
  
<span data-ttu-id="3ce4f-129">指定无效的_cyID_将返回错误。</span><span class="sxs-lookup"><span data-stu-id="3ce4f-129">Specifying an invalid  _cyID_ returns an error.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="3ce4f-130">示例 1</span><span class="sxs-lookup"><span data-stu-id="3ce4f-130">Example 1</span></span>

<span data-ttu-id="3ce4f-131">如果用户的“区域和语言设置”指定了美国美元：</span><span class="sxs-lookup"><span data-stu-id="3ce4f-131">If the user's Region and Language settings specify United States dollars:</span></span>
  
<span data-ttu-id="3ce4f-132">CY (999998.993)</span><span class="sxs-lookup"><span data-stu-id="3ce4f-132">CY(999998.993)</span></span>
  
<span data-ttu-id="3ce4f-133">返回 $999,998.99</span><span class="sxs-lookup"><span data-stu-id="3ce4f-133">Returns $999,998.99</span></span>
  
## <a name="example-2"></a><span data-ttu-id="3ce4f-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="3ce4f-134">Example 2</span></span>

<span data-ttu-id="3ce4f-135">CY(12345678.993, "USD")</span><span class="sxs-lookup"><span data-stu-id="3ce4f-135">CY(12345678.993, "USD")</span></span>
  
<span data-ttu-id="3ce4f-136">返回 $12,345,678.99</span><span class="sxs-lookup"><span data-stu-id="3ce4f-136">Returns $12,345,678.99</span></span>
  
## <a name="example-3"></a><span data-ttu-id="3ce4f-137">示例 3</span><span class="sxs-lookup"><span data-stu-id="3ce4f-137">Example 3</span></span>

<span data-ttu-id="3ce4f-138">CY(12345678.993, "DEM")</span><span class="sxs-lookup"><span data-stu-id="3ce4f-138">CY(12345678.993, "DEM")</span></span>
  
<span data-ttu-id="3ce4f-139">返回 12,345,678.99 DEM</span><span class="sxs-lookup"><span data-stu-id="3ce4f-139">Returns 12,345,678.99 DEM</span></span>
  
## <a name="example-4"></a><span data-ttu-id="3ce4f-140">示例 4</span><span class="sxs-lookup"><span data-stu-id="3ce4f-140">Example 4</span></span>

<span data-ttu-id="3ce4f-141">CY(12345678.7832, "XXX")</span><span class="sxs-lookup"><span data-stu-id="3ce4f-141">CY(12345678.7832, "XXX")</span></span>
  
<span data-ttu-id="3ce4f-142">返回 12,345,678.78</span><span class="sxs-lookup"><span data-stu-id="3ce4f-142">Returns 12,345,678.78</span></span>
  

