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
ms.openlocfilehash: ac5a74e08079f86c28b086b92302ebb01a4b0627
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329790"
---
# <a name="strsameex-function"></a><span data-ttu-id="11821-103">STRSAMEEX 函数</span><span class="sxs-lookup"><span data-stu-id="11821-103">STRSAMEEX Function</span></span>

<span data-ttu-id="11821-104">确定两个字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="11821-104">Determines whether two strings are the same.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="11821-105">语法</span><span class="sxs-lookup"><span data-stu-id="11821-105">Syntax</span></span>

<span data-ttu-id="11821-106">STRSAMEEX ("\* \* *string1* \* *"、"* \* *string2* \* *"、* \* *localeID* \* *、* **标志** \*)</span><span class="sxs-lookup"><span data-stu-id="11821-106">STRSAMEEX (" \*\* *string1* \*\* ", " \*\* *string2* \*\* ", \*\* *localeID* \*\*, \*\* *flag* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="11821-107">参数</span><span class="sxs-lookup"><span data-stu-id="11821-107">Parameters</span></span>

|<span data-ttu-id="11821-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="11821-108">**Name**</span></span>|<span data-ttu-id="11821-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="11821-109">**Required/Optional**</span></span>|<span data-ttu-id="11821-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="11821-110">**Data Type**</span></span>|<span data-ttu-id="11821-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="11821-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="11821-112">_string1_</span><span class="sxs-lookup"><span data-stu-id="11821-112">_string1_</span></span> <br/> |<span data-ttu-id="11821-113">必需</span><span class="sxs-lookup"><span data-stu-id="11821-113">Required</span></span>  <br/> |<span data-ttu-id="11821-114">**String**</span><span class="sxs-lookup"><span data-stu-id="11821-114">**String**</span></span> <br/> |<span data-ttu-id="11821-115">要比较的第一个字符串。</span><span class="sxs-lookup"><span data-stu-id="11821-115">The first string to compare.</span></span>  <br/> |
| <span data-ttu-id="11821-116">_string2_</span><span class="sxs-lookup"><span data-stu-id="11821-116">_string2_</span></span> <br/> |<span data-ttu-id="11821-117">必需</span><span class="sxs-lookup"><span data-stu-id="11821-117">Required</span></span>  <br/> |<span data-ttu-id="11821-118">**String**</span><span class="sxs-lookup"><span data-stu-id="11821-118">**String**</span></span> <br/> | <span data-ttu-id="11821-119">要比较的第二个字符串。</span><span class="sxs-lookup"><span data-stu-id="11821-119">The second string to compare.</span></span>  <br/> |
| <span data-ttu-id="11821-120">_localeID_</span><span class="sxs-lookup"><span data-stu-id="11821-120">_localeID_</span></span> <br/> |<span data-ttu-id="11821-121">必需</span><span class="sxs-lookup"><span data-stu-id="11821-121">Required</span></span>  <br/> |<span data-ttu-id="11821-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="11821-122">**Numeric**</span></span> <br/> |<span data-ttu-id="11821-123">区域设置 ID 代码。</span><span class="sxs-lookup"><span data-stu-id="11821-123">The locale ID code.</span></span>  <br/> |
| <span data-ttu-id="11821-124">_flag_</span><span class="sxs-lookup"><span data-stu-id="11821-124">_flag_</span></span> <br/> |<span data-ttu-id="11821-125">必需</span><span class="sxs-lookup"><span data-stu-id="11821-125">Required</span></span>  <br/> |<span data-ttu-id="11821-126">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="11821-126">**Numeric**</span></span> <br/> | <span data-ttu-id="11821-127">指定比较类型的位。</span><span class="sxs-lookup"><span data-stu-id="11821-127">A bit that specifies the type of comparison.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="11821-128">返回值</span><span class="sxs-lookup"><span data-stu-id="11821-128">Return value</span></span>

<span data-ttu-id="11821-129">布尔值</span><span class="sxs-lookup"><span data-stu-id="11821-129">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="11821-130">注解</span><span class="sxs-lookup"><span data-stu-id="11821-130">Remarks</span></span>

<span data-ttu-id="11821-131">如果两个输入字符串相同，则 STRSAMEEX 会返回 TRUE；如果它们不同，则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="11821-131">STRSAMEEX returns TRUE if both input strings are the same and FALSE if they aren't.</span></span> <span data-ttu-id="11821-132">使用此函数来比较多字节字符串或使用特定区域设置的大小写规则来进行比较。</span><span class="sxs-lookup"><span data-stu-id="11821-132">Use this function to compare multi-byte strings or to do comparisons that use case rules for a specific locale.</span></span>
  
<span data-ttu-id="11821-133">您可以将下列任意标志的组合与 STRSAMEEX 函数一起使用。</span><span class="sxs-lookup"><span data-stu-id="11821-133">You can use a combination of any of the following flags with the STRSAMEEX function.</span></span>
  
|<span data-ttu-id="11821-134">**Flag**</span><span class="sxs-lookup"><span data-stu-id="11821-134">**Flag**</span></span>|<span data-ttu-id="11821-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="11821-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11821-136">1</span><span class="sxs-lookup"><span data-stu-id="11821-136">1</span></span>  <br/> |<span data-ttu-id="11821-137">忽略大小写。</span><span class="sxs-lookup"><span data-stu-id="11821-137">Ignore case.</span></span>  <br/> |
|<span data-ttu-id="11821-138">双面</span><span class="sxs-lookup"><span data-stu-id="11821-138">2</span></span>  <br/> |<span data-ttu-id="11821-139">忽略不占位字符。</span><span class="sxs-lookup"><span data-stu-id="11821-139">Ignore non-spacing characters.</span></span>  <br/> |
|<span data-ttu-id="11821-140">4</span><span class="sxs-lookup"><span data-stu-id="11821-140">4</span></span>  <br/> |<span data-ttu-id="11821-141">忽略符号。</span><span class="sxs-lookup"><span data-stu-id="11821-141">Ignore symbols.</span></span>  <br/> |
|<span data-ttu-id="11821-142">4096</span><span class="sxs-lookup"><span data-stu-id="11821-142">4096</span></span>  <br/> |<span data-ttu-id="11821-143">将标点视为符号。</span><span class="sxs-lookup"><span data-stu-id="11821-143">Treat punctuation the same as symbols.</span></span>  <br/> |
|<span data-ttu-id="11821-144">65536</span><span class="sxs-lookup"><span data-stu-id="11821-144">65536</span></span>  <br/> |<span data-ttu-id="11821-145">不区分平假名和片假名字符。</span><span class="sxs-lookup"><span data-stu-id="11821-145">Don't differentiate between Hiragana and Katakana characters.</span></span>  <br/> |
|<span data-ttu-id="11821-146">131072</span><span class="sxs-lookup"><span data-stu-id="11821-146">131072</span></span>  <br/> |<span data-ttu-id="11821-147">不区分同一字符的单字节字符和双字节字符。</span><span class="sxs-lookup"><span data-stu-id="11821-147">Don't differentiate between a single-byte character and the same character as a double-byte character.</span></span>  <br/> |
   

