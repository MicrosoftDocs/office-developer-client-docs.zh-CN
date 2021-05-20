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
description: 确定字符串是否相同。 如果相同，则返回 TRUE;如果不同，则返回 FALSE。
ms.openlocfilehash: 0f298c966ec7a3f1e23c89473fecc555ed950f79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428681"
---
# <a name="strsame-function"></a><span data-ttu-id="1431f-104">STRSAME 函数</span><span class="sxs-lookup"><span data-stu-id="1431f-104">STRSAME Function</span></span>

<span data-ttu-id="1431f-105">确定字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="1431f-105">Determines whether strings are the same.</span></span> <span data-ttu-id="1431f-106">如果相同，则返回 TRUE;如果不同，则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1431f-106">It returns TRUE if they are the same and FALSE if they aren't.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1431f-107">语法</span><span class="sxs-lookup"><span data-stu-id="1431f-107">Syntax</span></span>

<span data-ttu-id="1431f-108">STRSAME (" \*\* *string1* \*\* "， " \*\* *string2* \*\* "， \*\* *ignoreCase* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="1431f-108">STRSAME (" \*\* *string1* \*\* ", " \*\* *string2* \*\* ", \*\* *ignoreCase* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1431f-109">参数</span><span class="sxs-lookup"><span data-stu-id="1431f-109">Parameters</span></span>

|<span data-ttu-id="1431f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1431f-110">**Name**</span></span>|<span data-ttu-id="1431f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1431f-111">**Required/Optional**</span></span>|<span data-ttu-id="1431f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1431f-112">**Data Type**</span></span>|<span data-ttu-id="1431f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1431f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1431f-114">_string1_</span><span class="sxs-lookup"><span data-stu-id="1431f-114">_string1_</span></span> <br/> |<span data-ttu-id="1431f-115">必需</span><span class="sxs-lookup"><span data-stu-id="1431f-115">Required</span></span>  <br/> |<span data-ttu-id="1431f-116">**String**</span><span class="sxs-lookup"><span data-stu-id="1431f-116">**String**</span></span> <br/> |<span data-ttu-id="1431f-117">要比较的第一个字符串。</span><span class="sxs-lookup"><span data-stu-id="1431f-117">The first string to compare.</span></span>  <br/> |
| <span data-ttu-id="1431f-118">_string2_</span><span class="sxs-lookup"><span data-stu-id="1431f-118">_string2_</span></span> <br/> |<span data-ttu-id="1431f-119">必需</span><span class="sxs-lookup"><span data-stu-id="1431f-119">Required</span></span>  <br/> |<span data-ttu-id="1431f-120">**String**</span><span class="sxs-lookup"><span data-stu-id="1431f-120">**String**</span></span> <br/> |<span data-ttu-id="1431f-121">要比较的第二个字符串。</span><span class="sxs-lookup"><span data-stu-id="1431f-121">The second string to compare.</span></span>  <br/> |
| <span data-ttu-id="1431f-122">_ignoreCase_</span><span class="sxs-lookup"><span data-stu-id="1431f-122">_ignoreCase_</span></span> <br/> |<span data-ttu-id="1431f-123">可选</span><span class="sxs-lookup"><span data-stu-id="1431f-123">Optional</span></span>  <br/> |<span data-ttu-id="1431f-124">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="1431f-124">**Boolean**</span></span> <br/> |<span data-ttu-id="1431f-p103">TRUE 为忽略大小写，FALSE 为比较大小写。默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1431f-p103">TRUE to ignore the case and FALSE to compare the case. The default is FALSE.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1431f-127">返回值</span><span class="sxs-lookup"><span data-stu-id="1431f-127">Return value</span></span>

<span data-ttu-id="1431f-128">布尔值</span><span class="sxs-lookup"><span data-stu-id="1431f-128">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1431f-129">备注</span><span class="sxs-lookup"><span data-stu-id="1431f-129">Remarks</span></span>

<span data-ttu-id="1431f-130">若要比较多字节字符串或使用特定区域设置的大小写规则进行比较，请使用 STRSAMEEX 函数。</span><span class="sxs-lookup"><span data-stu-id="1431f-130">To compare multi-byte strings or to do comparisons using case rules for a specific locale, use the STRSAMEEX function.</span></span>
  
## <a name="example-1"></a><span data-ttu-id="1431f-131">示例 1</span><span class="sxs-lookup"><span data-stu-id="1431f-131">Example 1</span></span>

<span data-ttu-id="1431f-132">STRSAME ("cat"，"dog") </span><span class="sxs-lookup"><span data-stu-id="1431f-132">STRSAME("cat","dog")</span></span>
  
<span data-ttu-id="1431f-133">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1431f-133">Returns FALSE.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="1431f-134">示例 2</span><span class="sxs-lookup"><span data-stu-id="1431f-134">Example 2</span></span>

<span data-ttu-id="1431f-135">STRSAME ("cat"，"cat") </span><span class="sxs-lookup"><span data-stu-id="1431f-135">STRSAME("cat","cat")</span></span>
  
<span data-ttu-id="1431f-136">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1431f-136">Returns TRUE.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="1431f-137">示例 3</span><span class="sxs-lookup"><span data-stu-id="1431f-137">Example 3</span></span>

<span data-ttu-id="1431f-138">STRSAME("cat","cat", TRUE)</span><span class="sxs-lookup"><span data-stu-id="1431f-138">STRSAME("cat","cat", TRUE)</span></span>
  
<span data-ttu-id="1431f-139">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1431f-139">Returns TRUE.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="1431f-140">示例 4</span><span class="sxs-lookup"><span data-stu-id="1431f-140">Example 4</span></span>

<span data-ttu-id="1431f-141">STRSAME ("cat"，"CAT") </span><span class="sxs-lookup"><span data-stu-id="1431f-141">STRSAME("cat","CAT")</span></span>
  
<span data-ttu-id="1431f-142">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1431f-142">Returns FALSE.</span></span>
  
## <a name="example-5"></a><span data-ttu-id="1431f-143">示例 5</span><span class="sxs-lookup"><span data-stu-id="1431f-143">Example 5</span></span>

<span data-ttu-id="1431f-144">STRSAME("cat","CAT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="1431f-144">STRSAME("cat","CAT", TRUE)</span></span>
  
<span data-ttu-id="1431f-145">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1431f-145">Returns TRUE.</span></span>
  
## <a name="example-6"></a><span data-ttu-id="1431f-146">示例 6</span><span class="sxs-lookup"><span data-stu-id="1431f-146">Example 6</span></span>

<span data-ttu-id="1431f-147">STRSAME("cät,"CAT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="1431f-147">STRSAME("cät,"CAT", TRUE)</span></span>
  
<span data-ttu-id="1431f-148">返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1431f-148">Returns FALSE.</span></span>
  
## <a name="example-7"></a><span data-ttu-id="1431f-149">示例 7</span><span class="sxs-lookup"><span data-stu-id="1431f-149">Example 7</span></span>

<span data-ttu-id="1431f-150">STRSAME("cät,"CÄT", TRUE)</span><span class="sxs-lookup"><span data-stu-id="1431f-150">STRSAME("cät,"CÄT", TRUE)</span></span>
  
<span data-ttu-id="1431f-151">返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1431f-151">Returns TRUE.</span></span>
  

