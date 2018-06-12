---
title: SUBSTITUTE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60115
localization_priority: Normal
ms.assetid: 4a27663a-9d37-2ac4-5856-edeb0880f16e
description: 用不同的文本字符串替换文本字符串的一部分。
ms.openlocfilehash: 2c33d8aafbd68054ac39d14bb4fb3cf857fb367e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781462"
---
# <a name="substitute-function"></a><span data-ttu-id="0c579-103">SUBSTITUTE 函数</span><span class="sxs-lookup"><span data-stu-id="0c579-103">SUBSTITUTE Function</span></span>

<span data-ttu-id="0c579-104">用不同的文本字符串替换文本字符串的一部分。</span><span class="sxs-lookup"><span data-stu-id="0c579-104">Replaces part of a text string with a different text string.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0c579-105">语法</span><span class="sxs-lookup"><span data-stu-id="0c579-105">Syntax</span></span>

 <span data-ttu-id="0c579-106">替代 (* **文本** *，* * *old_text* * *，* * *new_text* * * [，* * *start_num* * *] [，* * *ignore_case_opt* * *)</span><span class="sxs-lookup"><span data-stu-id="0c579-106">SUBSTITUTE (** *text* **, ** *old_text* **, ** *new_text* ** [, ** *start_num* ** ][, ** *ignore_case_opt* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0c579-107">参数</span><span class="sxs-lookup"><span data-stu-id="0c579-107">Parameters</span></span>

|<span data-ttu-id="0c579-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="0c579-108">**Name**</span></span>|<span data-ttu-id="0c579-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0c579-109">**Required/Optional**</span></span>|<span data-ttu-id="0c579-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0c579-110">**Data Type**</span></span>|<span data-ttu-id="0c579-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c579-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0c579-112">_text_</span><span class="sxs-lookup"><span data-stu-id="0c579-112">_text_</span></span> <br/> |<span data-ttu-id="0c579-113">必需</span><span class="sxs-lookup"><span data-stu-id="0c579-113">Required</span></span>  <br/> |<span data-ttu-id="0c579-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="0c579-114">**String**</span></span> <br/> | <span data-ttu-id="0c579-115">要替换其字符的文本或对包含要替换其字符的文本的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="0c579-115">The text or the reference to a cell containing text for which you want to substitute characters.</span></span>  <br/> |
| <span data-ttu-id="0c579-116">_old_text_</span><span class="sxs-lookup"><span data-stu-id="0c579-116">_old_text_</span></span> <br/> |<span data-ttu-id="0c579-117">必需</span><span class="sxs-lookup"><span data-stu-id="0c579-117">Required</span></span>  <br/> |<span data-ttu-id="0c579-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="0c579-118">**String**</span></span> <br/> | <span data-ttu-id="0c579-119">您想要替换的文本。</span><span class="sxs-lookup"><span data-stu-id="0c579-119">The text you want to replace.</span></span>  <br/> |
| <span data-ttu-id="0c579-120">_new_text_</span><span class="sxs-lookup"><span data-stu-id="0c579-120">_new_text_</span></span> <br/> |<span data-ttu-id="0c579-121">必需</span><span class="sxs-lookup"><span data-stu-id="0c579-121">Required</span></span>  <br/> |<span data-ttu-id="0c579-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="0c579-122">**String**</span></span> <br/> | <span data-ttu-id="0c579-123">您想要用于替换_old_text_的文本。</span><span class="sxs-lookup"><span data-stu-id="0c579-123">The text you want to use to replace  _old_text_.</span></span>  <br/> |
| <span data-ttu-id="0c579-124">_start_num_opt_</span><span class="sxs-lookup"><span data-stu-id="0c579-124">_start_num_opt_</span></span> <br/> |<span data-ttu-id="0c579-125">可选</span><span class="sxs-lookup"><span data-stu-id="0c579-125">Optional</span></span>  <br/> |<span data-ttu-id="0c579-126">**数字**</span><span class="sxs-lookup"><span data-stu-id="0c579-126">**Numeric**</span></span> <br/> |<span data-ttu-id="0c579-127">指定要替换 old_text 的哪个匹配项。</span><span class="sxs-lookup"><span data-stu-id="0c579-127">Specifies which occurences of old_text to replace.</span></span>  <br/> |
| <span data-ttu-id="0c579-128">_ignore_case_opt_</span><span class="sxs-lookup"><span data-stu-id="0c579-128">_ignore_case_opt_</span></span> <br/> |<span data-ttu-id="0c579-129">可选</span><span class="sxs-lookup"><span data-stu-id="0c579-129">Optional</span></span>  <br/> |<span data-ttu-id="0c579-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0c579-130">**Boolean**</span></span> <br/> |<span data-ttu-id="0c579-p101">如果区分大小写，则其值为 FALSE；否则为 TRUE。默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0c579-p101">FALSE if case-sensitive; otherwise, TRUE. The default is FALSE.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="0c579-133">返回值</span><span class="sxs-lookup"><span data-stu-id="0c579-133">Return value</span></span>

<span data-ttu-id="0c579-134">String</span><span class="sxs-lookup"><span data-stu-id="0c579-134">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0c579-135">注解</span><span class="sxs-lookup"><span data-stu-id="0c579-135">Remarks</span></span>

 <span data-ttu-id="0c579-136">如果指定_start_num_opt_，替换仅的_old_text_中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="0c579-136">If you specify  _start_num_opt_, only that occurrence of  _old_text_ is replaced.</span></span> <span data-ttu-id="0c579-137">否则，将每一处的_old_text_中_的文本_更改为_new_text。_</span><span class="sxs-lookup"><span data-stu-id="0c579-137">Otherwise, every occurrence of  _old_text_ in  _text_ is changed to  _new_text._</span></span>
  
<span data-ttu-id="0c579-p103">如果要替换文本字符串中的特定文本，请使用 SUBSTITUTE 函数。如果要替换在文本字符串中的特定位置出现的文本，请使用 REPLACE 函数。</span><span class="sxs-lookup"><span data-stu-id="0c579-p103">Use the SUBSTITUTE function when you want to replace specific text in a text string. If you want to replace text that occurs in a specific location in a text string, use the REPLACE function.</span></span>
  
## <a name="example"></a><span data-ttu-id="0c579-140">示例</span><span class="sxs-lookup"><span data-stu-id="0c579-140">Example</span></span>

<span data-ttu-id="0c579-141">SUBSTITUTE ("1 January 2003", "January", "JAN")</span><span class="sxs-lookup"><span data-stu-id="0c579-141">SUBSTITUTE ("1 January 2003", "January", "JAN")</span></span> 
  
<span data-ttu-id="0c579-142">返回“1 JAN 2003”。</span><span class="sxs-lookup"><span data-stu-id="0c579-142">Returns "1 JAN 2003".</span></span> 
  
<span data-ttu-id="0c579-143">SUBSTITUTE ("1 January 2003","january","JAN")</span><span class="sxs-lookup"><span data-stu-id="0c579-143">SUBSTITUTE ("1 January 2003","january","JAN")</span></span> 
  
<span data-ttu-id="0c579-p104">返回“1 January 2003”。不会进行任何更改，因为文本搜索区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0c579-p104">Returns "1 January 2003". No change is made because the text search is case-sensitive.</span></span> 
  

