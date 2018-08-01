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
ms.openlocfilehash: ea7696e7628939466730b9c054a706a7a9fa264e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780005"
---
# <a name="cy-function"></a><span data-ttu-id="5a20b-103">CY 函数</span><span class="sxs-lookup"><span data-stu-id="5a20b-103">CY Function</span></span>

<span data-ttu-id="5a20b-104">返回一个货币值。</span><span class="sxs-lookup"><span data-stu-id="5a20b-104">Returns a currency value.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5a20b-105">语法</span><span class="sxs-lookup"><span data-stu-id="5a20b-105">Syntax</span></span>

<span data-ttu-id="5a20b-106">CY (* **值** *，* * *cyID* * *)</span><span class="sxs-lookup"><span data-stu-id="5a20b-106">CY(** *value* **, ** *cyID* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5a20b-107">参数</span><span class="sxs-lookup"><span data-stu-id="5a20b-107">Parameters</span></span>

|<span data-ttu-id="5a20b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5a20b-108">**Name**</span></span>|<span data-ttu-id="5a20b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5a20b-109">**Required/Optional**</span></span>|<span data-ttu-id="5a20b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5a20b-110">**Data Type**</span></span>|<span data-ttu-id="5a20b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5a20b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5a20b-112">_value_</span><span class="sxs-lookup"><span data-stu-id="5a20b-112">_value_</span></span> <br/> |<span data-ttu-id="5a20b-113">可选</span><span class="sxs-lookup"><span data-stu-id="5a20b-113">Optional</span></span>  <br/> |<span data-ttu-id="5a20b-114">**数字或字符串**</span><span class="sxs-lookup"><span data-stu-id="5a20b-114">**Number or String**</span></span> <br/> |<span data-ttu-id="5a20b-115">数字或字符串，其中包含货币特定的格式。</span><span class="sxs-lookup"><span data-stu-id="5a20b-115">A number or a string that includes currency-specific formatting.</span></span> <span data-ttu-id="5a20b-116">如果未指定，将货币值根据系统的区域和语言设置中的货币样式格式。</span><span class="sxs-lookup"><span data-stu-id="5a20b-116">If not specified, the currency value is formatted according to the currency style in the system's Region and Language settings.</span></span>  <br/> |
| <span data-ttu-id="5a20b-117">_cyID_</span><span class="sxs-lookup"><span data-stu-id="5a20b-117">_cyID_</span></span> <br/> |<span data-ttu-id="5a20b-118">可选</span><span class="sxs-lookup"><span data-stu-id="5a20b-118">Optional</span></span>  <br/> |<span data-ttu-id="5a20b-119">**编号**</span><span class="sxs-lookup"><span data-stu-id="5a20b-119">**Number**</span></span> <br/> |<span data-ttu-id="5a20b-120">数字货币 ID 或三个字符引号的字符串组成的 ISO 4217 缩写。</span><span class="sxs-lookup"><span data-stu-id="5a20b-120">A numeric currency ID or a three-character quoted string for the ISO 4217 abbreviation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5a20b-121">说明</span><span class="sxs-lookup"><span data-stu-id="5a20b-121">Remarks</span></span>

<span data-ttu-id="5a20b-122">若要指定不同的货币，必须包括有效的_cyID_。</span><span class="sxs-lookup"><span data-stu-id="5a20b-122">To specify a different currency, you must include a valid  _cyID_.</span></span> <span data-ttu-id="5a20b-123">有关列表，请参阅[关于货币常量](about-currency-constants.md)。</span><span class="sxs-lookup"><span data-stu-id="5a20b-123">For a list, see [About currency constants](about-currency-constants.md).</span></span>
  
<span data-ttu-id="5a20b-124">如果_值_为与指定的货币类型，不兼容或无效的参数，如"而不是数字"如果已指定，#VALUE ！</span><span class="sxs-lookup"><span data-stu-id="5a20b-124">If  _value_ is incompatible with the designated currency type, or if an invalid argument such as "not a number" is specified, a #VALUE!</span></span> <span data-ttu-id="5a20b-125">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5a20b-125">error is returned.</span></span> <span data-ttu-id="5a20b-126">如果_值_大于 922,337,203,685,477.5807 或小于-922337203685，477.5808，则 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="5a20b-126">If  _value_ is greater than 922,337,203,685,477.5807 or less than -922,337,203,685,477.5808, a #VALUE!</span></span> <span data-ttu-id="5a20b-127">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5a20b-127">error is returned.</span></span> 
  
<span data-ttu-id="5a20b-128">更加精确地非常大的货币值的带小数的单位，如 3.6 万亿，请使用字符串参数的_值_。</span><span class="sxs-lookup"><span data-stu-id="5a20b-128">For better precision with very large currency values that include fractions of a unit, such as 3.6 trillion, use string arguments for  _value_.</span></span>
  
<span data-ttu-id="5a20b-129">指定无效的_cyID_将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5a20b-129">Specifying an invalid  _cyID_ returns an error.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="5a20b-130">示例 1</span><span class="sxs-lookup"><span data-stu-id="5a20b-130">Example 1</span></span>

<span data-ttu-id="5a20b-131">如果用户的“区域和语言设置”指定了美国美元：</span><span class="sxs-lookup"><span data-stu-id="5a20b-131">If the user's Region and Language settings specify United States dollars:</span></span>
  
<span data-ttu-id="5a20b-132">CY(999998.993)</span><span class="sxs-lookup"><span data-stu-id="5a20b-132">CY(999998.993)</span></span>
  
<span data-ttu-id="5a20b-133">返回 $999,998.99</span><span class="sxs-lookup"><span data-stu-id="5a20b-133">Returns $999,998.99</span></span>
  
## <a name="example-2"></a><span data-ttu-id="5a20b-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="5a20b-134">Example 2</span></span>

<span data-ttu-id="5a20b-135">CY(12345678.993, "USD")</span><span class="sxs-lookup"><span data-stu-id="5a20b-135">CY(12345678.993, "USD")</span></span>
  
<span data-ttu-id="5a20b-136">返回 $12,345,678.99</span><span class="sxs-lookup"><span data-stu-id="5a20b-136">Returns $12,345,678.99</span></span>
  
## <a name="example-3"></a><span data-ttu-id="5a20b-137">示例 3</span><span class="sxs-lookup"><span data-stu-id="5a20b-137">Example 3</span></span>

<span data-ttu-id="5a20b-138">CY(12345678.993, "DEM")</span><span class="sxs-lookup"><span data-stu-id="5a20b-138">CY(12345678.993, "DEM")</span></span>
  
<span data-ttu-id="5a20b-139">返回 12,345,678.99 DEM</span><span class="sxs-lookup"><span data-stu-id="5a20b-139">Returns 12,345,678.99 DEM</span></span>
  
## <a name="example-4"></a><span data-ttu-id="5a20b-140">示例 4</span><span class="sxs-lookup"><span data-stu-id="5a20b-140">Example 4</span></span>

<span data-ttu-id="5a20b-141">CY(12345678.7832, "XXX")</span><span class="sxs-lookup"><span data-stu-id="5a20b-141">CY(12345678.7832, "XXX")</span></span>
  
<span data-ttu-id="5a20b-142">返回 12,345,678.78</span><span class="sxs-lookup"><span data-stu-id="5a20b-142">Returns 12,345,678.78</span></span>
  

