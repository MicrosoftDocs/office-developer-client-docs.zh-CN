---
title: STRSAMEEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251787
localization_priority: Normal
ms.assetid: 056b54ae-1475-9480-6ebc-5c34ef48e0f8
description: 确定两个字符串是否相同。
ms.openlocfilehash: 129c7429fbb3b3e5d09193b8be570045d43a0f0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781458"
---
# <a name="strsameex-function"></a><span data-ttu-id="19ff5-103">STRSAMEEX 函数</span><span class="sxs-lookup"><span data-stu-id="19ff5-103">STRSAMEEX Function</span></span>

<span data-ttu-id="19ff5-104">确定两个字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="19ff5-104">Determines whether two strings are the same.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="19ff5-105">语法</span><span class="sxs-lookup"><span data-stu-id="19ff5-105">Syntax</span></span>

<span data-ttu-id="19ff5-106">STRSAMEEX ("* * *string1* * *"，"* * *string2* * *"，* * *localeID* * *，* **标志** *)</span><span class="sxs-lookup"><span data-stu-id="19ff5-106">STRSAMEEX (" ** *string1* ** ", " ** *string2* ** ", ** *localeID* **, ** *flag* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="19ff5-107">参数</span><span class="sxs-lookup"><span data-stu-id="19ff5-107">Parameters</span></span>

|<span data-ttu-id="19ff5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="19ff5-108">**Name**</span></span>|<span data-ttu-id="19ff5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="19ff5-109">**Required/Optional**</span></span>|<span data-ttu-id="19ff5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="19ff5-110">**Data Type**</span></span>|<span data-ttu-id="19ff5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="19ff5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="19ff5-112">_string1_</span><span class="sxs-lookup"><span data-stu-id="19ff5-112">_string1_</span></span> <br/> |<span data-ttu-id="19ff5-113">必需</span><span class="sxs-lookup"><span data-stu-id="19ff5-113">Required</span></span>  <br/> |<span data-ttu-id="19ff5-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="19ff5-114">**String**</span></span> <br/> |<span data-ttu-id="19ff5-115">要比较的第一个字符串。</span><span class="sxs-lookup"><span data-stu-id="19ff5-115">The first string to compare.</span></span>  <br/> |
| <span data-ttu-id="19ff5-116">_string2_</span><span class="sxs-lookup"><span data-stu-id="19ff5-116">_string2_</span></span> <br/> |<span data-ttu-id="19ff5-117">必需</span><span class="sxs-lookup"><span data-stu-id="19ff5-117">Required</span></span>  <br/> |<span data-ttu-id="19ff5-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="19ff5-118">**String**</span></span> <br/> | <span data-ttu-id="19ff5-119">要比较的第二个字符串。</span><span class="sxs-lookup"><span data-stu-id="19ff5-119">The second string to compare.</span></span>  <br/> |
| <span data-ttu-id="19ff5-120">_localeID_</span><span class="sxs-lookup"><span data-stu-id="19ff5-120">_localeID_</span></span> <br/> |<span data-ttu-id="19ff5-121">必需</span><span class="sxs-lookup"><span data-stu-id="19ff5-121">Required</span></span>  <br/> |<span data-ttu-id="19ff5-122">**数字**</span><span class="sxs-lookup"><span data-stu-id="19ff5-122">**Numeric**</span></span> <br/> |<span data-ttu-id="19ff5-123">区域设置 ID 代码。</span><span class="sxs-lookup"><span data-stu-id="19ff5-123">The locale ID code.</span></span>  <br/> |
| <span data-ttu-id="19ff5-124">_标志_</span><span class="sxs-lookup"><span data-stu-id="19ff5-124">_flag_</span></span> <br/> |<span data-ttu-id="19ff5-125">必需</span><span class="sxs-lookup"><span data-stu-id="19ff5-125">Required</span></span>  <br/> |<span data-ttu-id="19ff5-126">**数字**</span><span class="sxs-lookup"><span data-stu-id="19ff5-126">**Numeric**</span></span> <br/> | <span data-ttu-id="19ff5-127">指定比较类型的位。</span><span class="sxs-lookup"><span data-stu-id="19ff5-127">A bit that specifies the type of comparison.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="19ff5-128">返回值</span><span class="sxs-lookup"><span data-stu-id="19ff5-128">Return value</span></span>

<span data-ttu-id="19ff5-129">Boolean</span><span class="sxs-lookup"><span data-stu-id="19ff5-129">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="19ff5-130">备注</span><span class="sxs-lookup"><span data-stu-id="19ff5-130">Remarks</span></span>

<span data-ttu-id="19ff5-131">如果两个输入的字符串相同 TRUE 和 FALSE 如果它们不 STRSAMEEX 返回。</span><span class="sxs-lookup"><span data-stu-id="19ff5-131">STRSAMEEX returns TRUE if both input strings are the same and FALSE if they aren't.</span></span> <span data-ttu-id="19ff5-132">若要比较多字节字符串或大小写规则用于特定区域设置的比较，请使用此函数。</span><span class="sxs-lookup"><span data-stu-id="19ff5-132">Use this function to compare multi-byte strings or to do comparisons that use case rules for a specific locale.</span></span>
  
<span data-ttu-id="19ff5-133">您可以将下列任意标志的组合与 STRSAMEEX 函数一起使用。</span><span class="sxs-lookup"><span data-stu-id="19ff5-133">You can use a combination of any of the following flags with the STRSAMEEX function.</span></span>
  
|<span data-ttu-id="19ff5-134">**Flag**</span><span class="sxs-lookup"><span data-stu-id="19ff5-134">**Flag**</span></span>|<span data-ttu-id="19ff5-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="19ff5-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19ff5-136">1</span><span class="sxs-lookup"><span data-stu-id="19ff5-136">1</span></span>  <br/> |<span data-ttu-id="19ff5-137">忽略大小写。</span><span class="sxs-lookup"><span data-stu-id="19ff5-137">Ignore case.</span></span>  <br/> |
|<span data-ttu-id="19ff5-138">2</span><span class="sxs-lookup"><span data-stu-id="19ff5-138">2</span></span>  <br/> |<span data-ttu-id="19ff5-139">忽略不占位字符。</span><span class="sxs-lookup"><span data-stu-id="19ff5-139">Ignore non-spacing characters.</span></span>  <br/> |
|<span data-ttu-id="19ff5-140">4</span><span class="sxs-lookup"><span data-stu-id="19ff5-140">4</span></span>  <br/> |<span data-ttu-id="19ff5-141">忽略符号。</span><span class="sxs-lookup"><span data-stu-id="19ff5-141">Ignore symbols.</span></span>  <br/> |
|<span data-ttu-id="19ff5-142">4096</span><span class="sxs-lookup"><span data-stu-id="19ff5-142">4096</span></span>  <br/> |<span data-ttu-id="19ff5-143">将标点视为符号。</span><span class="sxs-lookup"><span data-stu-id="19ff5-143">Treat punctuation the same as symbols.</span></span>  <br/> |
|<span data-ttu-id="19ff5-144">65536</span><span class="sxs-lookup"><span data-stu-id="19ff5-144">65536</span></span>  <br/> |<span data-ttu-id="19ff5-145">不区分平假名和片假名字符。</span><span class="sxs-lookup"><span data-stu-id="19ff5-145">Don't differentiate between Hiragana and Katakana characters.</span></span>  <br/> |
|<span data-ttu-id="19ff5-146">131072</span><span class="sxs-lookup"><span data-stu-id="19ff5-146">131072</span></span>  <br/> |<span data-ttu-id="19ff5-147">不区分同一字符的单字节字符和双字节字符。</span><span class="sxs-lookup"><span data-stu-id="19ff5-147">Don't differentiate between a single-byte character and the same character as a double-byte character.</span></span>  <br/> |
   

