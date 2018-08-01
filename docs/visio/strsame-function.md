---
title: STRSAME 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251786
localization_priority: Normal
ms.assetid: d9fc2007-cc21-b20c-adee-be87cc356753
description: 确定字符串是否相同。 如果它们是相同的则返回 TRUE 和 FALSE 如果它们不是。
ms.openlocfilehash: 5365ce6e679f708a47f4bcbdebbc4cabb13a2aee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781436"
---
# <a name="strsame-function"></a><span data-ttu-id="20bf8-104">STRSAME 函数</span><span class="sxs-lookup"><span data-stu-id="20bf8-104">STRSAME Function</span></span>

<span data-ttu-id="20bf8-105">确定字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="20bf8-105">Determines whether strings are the same.</span></span> <span data-ttu-id="20bf8-106">如果它们是相同的则返回 TRUE 和 FALSE 如果它们不是。</span><span class="sxs-lookup"><span data-stu-id="20bf8-106">It returns TRUE if they are the same and FALSE if they aren't.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="20bf8-107">语法</span><span class="sxs-lookup"><span data-stu-id="20bf8-107">Syntax</span></span>

<span data-ttu-id="20bf8-108">STRSAME ("* * *string1* * *"，"* * *string2* * *"，* * *ignoreCase* * *)</span><span class="sxs-lookup"><span data-stu-id="20bf8-108">STRSAME (" ** *string1* ** ", " ** *string2* ** ", ** *ignoreCase* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="20bf8-109">参数</span><span class="sxs-lookup"><span data-stu-id="20bf8-109">Parameters</span></span>

|<span data-ttu-id="20bf8-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="20bf8-110">**Name**</span></span>|<span data-ttu-id="20bf8-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="20bf8-111">**Required/Optional**</span></span>|<span data-ttu-id="20bf8-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="20bf8-112">**Data Type**</span></span>|<span data-ttu-id="20bf8-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="20bf8-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="20bf8-114">_string1_</span><span class="sxs-lookup"><span data-stu-id="20bf8-114">_string1_</span></span> <br/> |<span data-ttu-id="20bf8-115">必需</span><span class="sxs-lookup"><span data-stu-id="20bf8-115">Required</span></span>  <br/> |<span data-ttu-id="20bf8-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="20bf8-116">**String**</span></span> <br/> |<span data-ttu-id="20bf8-117">要比较的第一个字符串。</span><span class="sxs-lookup"><span data-stu-id="20bf8-117">The first string to compare.</span></span>  <br/> |
| <span data-ttu-id="20bf8-118">_string2_</span><span class="sxs-lookup"><span data-stu-id="20bf8-118">_string2_</span></span> <br/> |<span data-ttu-id="20bf8-119">必需</span><span class="sxs-lookup"><span data-stu-id="20bf8-119">Required</span></span>  <br/> |<span data-ttu-id="20bf8-120">**字符串**</span><span class="sxs-lookup"><span data-stu-id="20bf8-120">**String**</span></span> <br/> |<span data-ttu-id="20bf8-121">要比较的第二个字符串。</span><span class="sxs-lookup"><span data-stu-id="20bf8-121">The second string to compare.</span></span>  <br/> |
| <span data-ttu-id="20bf8-122">_ignoreCase_</span><span class="sxs-lookup"><span data-stu-id="20bf8-122">_ignoreCase_</span></span> <br/> |<span data-ttu-id="20bf8-123">可选</span><span class="sxs-lookup"><span data-stu-id="20bf8-123">Optional</span></span>  <br/> |<span data-ttu-id="20bf8-124">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="20bf8-124">**Boolean**</span></span> <br/> |<span data-ttu-id="20bf8-p103">TRUE 为忽略大小写，FALSE 为比较大小写。默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-p103">TRUE to ignore the case and FALSE to compare the case. The default is FALSE.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="20bf8-127">返回值</span><span class="sxs-lookup"><span data-stu-id="20bf8-127">Return value</span></span>

<span data-ttu-id="20bf8-128">Boolean</span><span class="sxs-lookup"><span data-stu-id="20bf8-128">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="20bf8-129">注解</span><span class="sxs-lookup"><span data-stu-id="20bf8-129">Remarks</span></span>

<span data-ttu-id="20bf8-130">若要比较多字节字符串或使用特定区域设置的大小写规则进行比较，请使用 STRSAMEEX 函数。</span><span class="sxs-lookup"><span data-stu-id="20bf8-130">To compare multi-byte strings or to do comparisons using case rules for a specific locale, use the STRSAMEEX function.</span></span>
  
## <a name="example-1"></a><span data-ttu-id="20bf8-131">示例 1</span><span class="sxs-lookup"><span data-stu-id="20bf8-131">Example 1</span></span>

<span data-ttu-id="20bf8-132">STRSAME("cat","dog")</span><span class="sxs-lookup"><span data-stu-id="20bf8-132">STRSAME("cat","dog")</span></span>
  
<span data-ttu-id="20bf8-133">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-133">Returns FALSE.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="20bf8-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="20bf8-134">Example 2</span></span>

<span data-ttu-id="20bf8-135">STRSAME("cat","cat")</span><span class="sxs-lookup"><span data-stu-id="20bf8-135">STRSAME("cat","cat")</span></span>
  
<span data-ttu-id="20bf8-136">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-136">Returns TRUE.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="20bf8-137">示例 3</span><span class="sxs-lookup"><span data-stu-id="20bf8-137">Example 3</span></span>

<span data-ttu-id="20bf8-138">STRSAME("cat","cat", TRUE)</span><span class="sxs-lookup"><span data-stu-id="20bf8-138">STRSAME("cat","cat", TRUE)</span></span>
  
<span data-ttu-id="20bf8-139">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-139">Returns TRUE.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="20bf8-140">示例 4</span><span class="sxs-lookup"><span data-stu-id="20bf8-140">Example 4</span></span>

<span data-ttu-id="20bf8-141">STRSAME("cat","CAT")</span><span class="sxs-lookup"><span data-stu-id="20bf8-141">STRSAME("cat","CAT")</span></span>
  
<span data-ttu-id="20bf8-142">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-142">Returns FALSE.</span></span>
  
## <a name="example-5"></a><span data-ttu-id="20bf8-143">示例 5</span><span class="sxs-lookup"><span data-stu-id="20bf8-143">Example 5</span></span>

<span data-ttu-id="20bf8-144">STRSAME("cat","CAT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="20bf8-144">STRSAME("cat","CAT", TRUE)</span></span>
  
<span data-ttu-id="20bf8-145">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-145">Returns TRUE.</span></span>
  
## <a name="example-6"></a><span data-ttu-id="20bf8-146">示例 6</span><span class="sxs-lookup"><span data-stu-id="20bf8-146">Example 6</span></span>

<span data-ttu-id="20bf8-147">STRSAME("cät,"CAT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="20bf8-147">STRSAME("cät,"CAT", TRUE)</span></span>
  
<span data-ttu-id="20bf8-148">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-148">Returns FALSE.</span></span>
  
## <a name="example-7"></a><span data-ttu-id="20bf8-149">示例 7</span><span class="sxs-lookup"><span data-stu-id="20bf8-149">Example 7</span></span>

<span data-ttu-id="20bf8-150">STRSAME("cät,"CÄT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="20bf8-150">STRSAME("cät,"CÄT", TRUE)</span></span>
  
<span data-ttu-id="20bf8-151">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="20bf8-151">Returns TRUE.</span></span>
  

