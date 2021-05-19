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
ms.openlocfilehash: fc12ab30ec9c509e2f126931bee837f518e96f3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346821"
---
# <a name="substitute-function"></a><span data-ttu-id="482d2-103">SUBSTITUTE 函数</span><span class="sxs-lookup"><span data-stu-id="482d2-103">SUBSTITUTE Function</span></span>

<span data-ttu-id="482d2-104">用不同的文本字符串替换文本字符串的一部分。</span><span class="sxs-lookup"><span data-stu-id="482d2-104">Replaces part of a text string with a different text string.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="482d2-105">语法</span><span class="sxs-lookup"><span data-stu-id="482d2-105">Syntax</span></span>

 <span data-ttu-id="482d2-106">SUBSTITUTE (\*\* *text* \*\*， \*\* *old_text* \*\*， \*\* *new_text* \*\* [， \*\* *start_num* \*\* ][， \*\* *ignore_case_opt* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="482d2-106">SUBSTITUTE (\*\* *text* \*\*, \*\* *old_text* \*\*, \*\* *new_text* \*\* [, \*\* *start_num* \*\* ][, \*\* *ignore_case_opt* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="482d2-107">参数</span><span class="sxs-lookup"><span data-stu-id="482d2-107">Parameters</span></span>

|<span data-ttu-id="482d2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="482d2-108">**Name**</span></span>|<span data-ttu-id="482d2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="482d2-109">**Required/Optional**</span></span>|<span data-ttu-id="482d2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="482d2-110">**Data Type**</span></span>|<span data-ttu-id="482d2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="482d2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="482d2-112">_text_</span><span class="sxs-lookup"><span data-stu-id="482d2-112">_text_</span></span> <br/> |<span data-ttu-id="482d2-113">必需</span><span class="sxs-lookup"><span data-stu-id="482d2-113">Required</span></span>  <br/> |<span data-ttu-id="482d2-114">**String**</span><span class="sxs-lookup"><span data-stu-id="482d2-114">**String**</span></span> <br/> | <span data-ttu-id="482d2-115">要替换其字符的文本或对包含要替换其字符的文本的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="482d2-115">The text or the reference to a cell containing text for which you want to substitute characters.</span></span>  <br/> |
| <span data-ttu-id="482d2-116">_old_text_</span><span class="sxs-lookup"><span data-stu-id="482d2-116">_old_text_</span></span> <br/> |<span data-ttu-id="482d2-117">必需</span><span class="sxs-lookup"><span data-stu-id="482d2-117">Required</span></span>  <br/> |<span data-ttu-id="482d2-118">**String**</span><span class="sxs-lookup"><span data-stu-id="482d2-118">**String**</span></span> <br/> | <span data-ttu-id="482d2-119">要替换的文本。</span><span class="sxs-lookup"><span data-stu-id="482d2-119">The text you want to replace.</span></span>  <br/> |
| <span data-ttu-id="482d2-120">_new_text_</span><span class="sxs-lookup"><span data-stu-id="482d2-120">_new_text_</span></span> <br/> |<span data-ttu-id="482d2-121">必需</span><span class="sxs-lookup"><span data-stu-id="482d2-121">Required</span></span>  <br/> |<span data-ttu-id="482d2-122">**String**</span><span class="sxs-lookup"><span data-stu-id="482d2-122">**String**</span></span> <br/> | <span data-ttu-id="482d2-123">要用于替换  _文本的文本_ old_text。</span><span class="sxs-lookup"><span data-stu-id="482d2-123">The text you want to use to replace  _old_text_.</span></span>  <br/> |
| <span data-ttu-id="482d2-124">_start_num_opt_</span><span class="sxs-lookup"><span data-stu-id="482d2-124">_start_num_opt_</span></span> <br/> |<span data-ttu-id="482d2-125">可选</span><span class="sxs-lookup"><span data-stu-id="482d2-125">Optional</span></span>  <br/> |<span data-ttu-id="482d2-126">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="482d2-126">**Numeric**</span></span> <br/> |<span data-ttu-id="482d2-127">指定要替换old_text的匹配项。</span><span class="sxs-lookup"><span data-stu-id="482d2-127">Specifies which occurrences of old_text to replace.</span></span>  <br/> |
| <span data-ttu-id="482d2-128">_ignore_case_opt_</span><span class="sxs-lookup"><span data-stu-id="482d2-128">_ignore_case_opt_</span></span> <br/> |<span data-ttu-id="482d2-129">可选</span><span class="sxs-lookup"><span data-stu-id="482d2-129">Optional</span></span>  <br/> |<span data-ttu-id="482d2-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="482d2-130">**Boolean**</span></span> <br/> |<span data-ttu-id="482d2-p101">如果区分大小写，则其值为 FALSE；否则为 TRUE。默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="482d2-p101">FALSE if case-sensitive; otherwise, TRUE. The default is FALSE.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="482d2-133">返回值</span><span class="sxs-lookup"><span data-stu-id="482d2-133">Return value</span></span>

<span data-ttu-id="482d2-134">String</span><span class="sxs-lookup"><span data-stu-id="482d2-134">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="482d2-135">备注</span><span class="sxs-lookup"><span data-stu-id="482d2-135">Remarks</span></span>

 <span data-ttu-id="482d2-136">如果 _指定_ start_num_opt ，则仅替换 _old_text匹配项。_</span><span class="sxs-lookup"><span data-stu-id="482d2-136">If you specify  _start_num_opt_, only that occurrence of  _old_text_ is replaced.</span></span> <span data-ttu-id="482d2-137">否则，_文本中old_text__每个匹配项_ 都会更改为 _new_text。_</span><span class="sxs-lookup"><span data-stu-id="482d2-137">Otherwise, every occurrence of  _old_text_ in  _text_ is changed to  _new_text._</span></span>
  
<span data-ttu-id="482d2-p103">如果要替换文本字符串中的特定文本，请使用 SUBSTITUTE 函数。如果要替换在文本字符串中的特定位置出现的文本，请使用 REPLACE 函数。</span><span class="sxs-lookup"><span data-stu-id="482d2-p103">Use the SUBSTITUTE function when you want to replace specific text in a text string. If you want to replace text that occurs in a specific location in a text string, use the REPLACE function.</span></span>
  
## <a name="example"></a><span data-ttu-id="482d2-140">示例</span><span class="sxs-lookup"><span data-stu-id="482d2-140">Example</span></span>

<span data-ttu-id="482d2-141">SUBSTITUTE ("1 January 2003", "January", "JAN")</span><span class="sxs-lookup"><span data-stu-id="482d2-141">SUBSTITUTE ("1 January 2003", "January", "JAN")</span></span> 
  
<span data-ttu-id="482d2-142">返回“1 JAN 2003”。</span><span class="sxs-lookup"><span data-stu-id="482d2-142">Returns "1 JAN 2003".</span></span> 
  
<span data-ttu-id="482d2-143">SUBSTITUTE ("1 January 2003","january","JAN")</span><span class="sxs-lookup"><span data-stu-id="482d2-143">SUBSTITUTE ("1 January 2003","january","JAN")</span></span> 
  
<span data-ttu-id="482d2-p104">返回“1 January 2003”。不会进行任何更改，因为文本搜索区分大小写。</span><span class="sxs-lookup"><span data-stu-id="482d2-p104">Returns "1 January 2003". No change is made because the text search is case-sensitive.</span></span> 
  

