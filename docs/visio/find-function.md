---
title: FIND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60101
localization_priority: Normal
ms.assetid: c827ecd4-5593-6d4f-2746-d13b02b098fe
description: 查找包含在另一个文本字符串中的一个文本字符串，并返回您查找的文本字符串相对于其在所处文本字符串中位置的起始位置。
ms.openlocfilehash: 40d65af25d89774c1bdf7b235cf653dbb61dd1c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426574"
---
# <a name="find-function"></a><span data-ttu-id="cac03-103">FIND 函数</span><span class="sxs-lookup"><span data-stu-id="cac03-103">FIND Function</span></span>

<span data-ttu-id="cac03-104">查找包含在另一个文本字符串中的一个文本字符串，并返回您查找的文本字符串相对于其在所处文本字符串中位置的起始位置。</span><span class="sxs-lookup"><span data-stu-id="cac03-104">Finds one text string contained within another text string, and returns the starting position of the text string you are seeking relative to its position in the text string that contains it.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="cac03-105">语法</span><span class="sxs-lookup"><span data-stu-id="cac03-105">Syntax</span></span>

<span data-ttu-id="cac03-106">FIND (\*\* *find_text* \*\*， \*\* *within_text* \*\*，[ \*\* *start_num* \*\* ]， [ \*\* *ignore_case* \*\* ]) </span><span class="sxs-lookup"><span data-stu-id="cac03-106">FIND (\*\* *find_text* \*\*, \*\* *within_text* \*\*,[ \*\* *start_num* \*\* ], [ \*\* *ignore_case* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cac03-107">参数</span><span class="sxs-lookup"><span data-stu-id="cac03-107">Parameters</span></span>

|<span data-ttu-id="cac03-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cac03-108">**Name**</span></span>|<span data-ttu-id="cac03-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cac03-109">**Required/Optional**</span></span>|<span data-ttu-id="cac03-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cac03-110">**Data Type**</span></span>|<span data-ttu-id="cac03-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cac03-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cac03-112">_find_text_</span><span class="sxs-lookup"><span data-stu-id="cac03-112">_find_text_</span></span> <br/> |<span data-ttu-id="cac03-113">必需</span><span class="sxs-lookup"><span data-stu-id="cac03-113">Required</span></span>  <br/> |<span data-ttu-id="cac03-114">**String**</span><span class="sxs-lookup"><span data-stu-id="cac03-114">**String**</span></span> <br/> |<span data-ttu-id="cac03-115">要查找的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="cac03-115">The text string you want to find.</span></span>  <br/> |
| <span data-ttu-id="cac03-116">_format_</span><span class="sxs-lookup"><span data-stu-id="cac03-116">_format_</span></span> <br/> |<span data-ttu-id="cac03-117">必需</span><span class="sxs-lookup"><span data-stu-id="cac03-117">Required</span></span>  <br/> |<span data-ttu-id="cac03-118">**String**</span><span class="sxs-lookup"><span data-stu-id="cac03-118">**String**</span></span> <br/> |<span data-ttu-id="cac03-119">包含要查找的文本的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="cac03-119">The text string that contains the text you want to find.</span></span>  <br/> |
| <span data-ttu-id="cac03-120">_start_num_</span><span class="sxs-lookup"><span data-stu-id="cac03-120">_start_num_</span></span> <br/> |<span data-ttu-id="cac03-121">可选</span><span class="sxs-lookup"><span data-stu-id="cac03-121">Optional</span></span>  <br/> |<span data-ttu-id="cac03-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="cac03-122">**Number**</span></span> <br/> |<span data-ttu-id="cac03-123">从该处开始搜索的字符。</span><span class="sxs-lookup"><span data-stu-id="cac03-123">The character at which to start the search.</span></span> <span data-ttu-id="cac03-124">第一  _个字符within_text_ 1。</span><span class="sxs-lookup"><span data-stu-id="cac03-124">The first character in  _within_text_ is 1.</span></span> <span data-ttu-id="cac03-125">如果  _start_num，_ 则假定其为 1。</span><span class="sxs-lookup"><span data-stu-id="cac03-125">If  _start_num_ is missing, it is assumed to be 1.</span></span>  <br/> |
| <span data-ttu-id="cac03-126">_ignore_case_</span><span class="sxs-lookup"><span data-stu-id="cac03-126">_ignore_case_</span></span> <br/> |<span data-ttu-id="cac03-127">可选</span><span class="sxs-lookup"><span data-stu-id="cac03-127">Optional</span></span>  <br/> |<span data-ttu-id="cac03-128">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="cac03-128">**Boolean**</span></span> <br/> |<span data-ttu-id="cac03-p102">默认情况下，FIND 函数区分大小写。如果希望 FIND 函数忽略大小写，请将此参数设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="cac03-p102">By default, the FIND function is case-sensitive. If you want the FIND function to ignore case, set this argument to TRUE.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="cac03-131">返回值</span><span class="sxs-lookup"><span data-stu-id="cac03-131">Return value</span></span>

<span data-ttu-id="cac03-132">帐号</span><span class="sxs-lookup"><span data-stu-id="cac03-132">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cac03-133">备注</span><span class="sxs-lookup"><span data-stu-id="cac03-133">Remarks</span></span>

<span data-ttu-id="cac03-134">如果找到多个匹配结果，FIND 函数将返回第一个匹配结果在字符串中的起始位置。</span><span class="sxs-lookup"><span data-stu-id="cac03-134">If multiple matches are found, the FIND function returns the starting position of the first match in the string.</span></span> <span data-ttu-id="cac03-135">the  _find_text_ argument does not consider any characters to be wildcards.</span><span class="sxs-lookup"><span data-stu-id="cac03-135">The  _find_text_ argument does not consider any characters to be wildcards.</span></span> 
  
<span data-ttu-id="cac03-136">如果 _find_text：_</span><span class="sxs-lookup"><span data-stu-id="cac03-136">If  _find_text_:</span></span>
  
-  <span data-ttu-id="cac03-137">为空 ("") ，FIND 与搜索字符串中的第一个字符 (，即编号为 start_num 或 1) 。 </span><span class="sxs-lookup"><span data-stu-id="cac03-137">Is empty (""), FIND matches the first character in the search string (that is, the character numbered  _start_num_ or 1).</span></span> 
    
- <span data-ttu-id="cac03-138">不显示  _在within_text中_，FIND 将返回#VALUE！</span><span class="sxs-lookup"><span data-stu-id="cac03-138">Does not appear in  _within_text_, FIND returns the #VALUE!</span></span> <span data-ttu-id="cac03-139">。</span><span class="sxs-lookup"><span data-stu-id="cac03-139">error value.</span></span> 
    
<span data-ttu-id="cac03-140">如果 _start_num：_</span><span class="sxs-lookup"><span data-stu-id="cac03-140">If  _start_num_:</span></span>
  
- <span data-ttu-id="cac03-p105">不大于零 (0)，FIND 将返回 #VALUE! 错误值。</span><span class="sxs-lookup"><span data-stu-id="cac03-p105">Is not greater than zero (0), FIND returns the #VALUE! error value.</span></span> 
    
- <span data-ttu-id="cac03-143">大于数据长度，  _则_ WITHIN_TEXT FINDreturns the #VALUE！</span><span class="sxs-lookup"><span data-stu-id="cac03-143">Is greater than the length of  _within_text_, FINDreturns the #VALUE!</span></span> <span data-ttu-id="cac03-144">错误值。</span><span class="sxs-lookup"><span data-stu-id="cac03-144">error value.</span></span> 
    
## <a name="example"></a><span data-ttu-id="cac03-145">示例</span><span class="sxs-lookup"><span data-stu-id="cac03-145">Example</span></span>

<span data-ttu-id="cac03-146">FIND ("2003","January 1, 2003")</span><span class="sxs-lookup"><span data-stu-id="cac03-146">FIND ("2003","January 1, 2003")</span></span> 
  
<span data-ttu-id="cac03-147">返回 12。</span><span class="sxs-lookup"><span data-stu-id="cac03-147">Returns 12.</span></span> 
  

