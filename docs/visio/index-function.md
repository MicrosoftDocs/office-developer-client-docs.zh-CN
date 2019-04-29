---
title: INDEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251443
localization_priority: Normal
ms.assetid: cc46f91e-733f-e25a-17d2-19df8c8febd2
description: 在用 delimiter 分隔的 list 中返回位于从零开始的位置 index 的子字符串。 如果索引超出范围，则返回一个空字符串或返回作为 errorvalue 参数提供的可选令牌。
ms.openlocfilehash: 11362ed984a489682d57f007300e60de548ddf11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431573"
---
# <a name="index-function"></a><span data-ttu-id="7ca18-104">INDEX 函数</span><span class="sxs-lookup"><span data-stu-id="7ca18-104">INDEX Function</span></span>

<span data-ttu-id="7ca18-105">返回以_分隔符_分隔的_列表_中从零开始的位置_索引_处的子字符串。</span><span class="sxs-lookup"><span data-stu-id="7ca18-105">Returns the substring at the zero-based location  _index_ in the  _list_ delimited by  _delimiter_.</span></span> <span data-ttu-id="7ca18-106">或者, 如果索引超出范围, 则返回一个空字符串或作为*errorvalue*参数提供的可选令牌。</span><span class="sxs-lookup"><span data-stu-id="7ca18-106">Or, if the index is out of range, returns an empty string or the optional token provided as the  *errorvalue*  argument.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7ca18-107">语法</span><span class="sxs-lookup"><span data-stu-id="7ca18-107">Syntax</span></span>

<span data-ttu-id="7ca18-108">index (\* **索引** *, "* \* *list* \* *" [, [* **分隔符** *] [, [* \* *errorvalue* \* \*]]])</span><span class="sxs-lookup"><span data-stu-id="7ca18-108">INDEX(\*\* *index* \*\*," \*\* *list* \*\* "[,[ \*\* *delimiter* \*\* ][,[ \*\* *errorvalue* \*\* ]]])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="7ca18-109">参数</span><span class="sxs-lookup"><span data-stu-id="7ca18-109">Parameters</span></span>

|<span data-ttu-id="7ca18-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="7ca18-110">**Name**</span></span>|<span data-ttu-id="7ca18-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="7ca18-111">**Required/Optional**</span></span>|<span data-ttu-id="7ca18-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7ca18-112">**Data Type**</span></span>|<span data-ttu-id="7ca18-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca18-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7ca18-114">_index_</span><span class="sxs-lookup"><span data-stu-id="7ca18-114">_index_</span></span> <br/> |<span data-ttu-id="7ca18-115">必需</span><span class="sxs-lookup"><span data-stu-id="7ca18-115">Required</span></span>  <br/> |<span data-ttu-id="7ca18-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="7ca18-116">**Number**</span></span> <br/> |<span data-ttu-id="7ca18-117">要查找的位置。</span><span class="sxs-lookup"><span data-stu-id="7ca18-117">The location that you want to find.</span></span>  <br/> |
| <span data-ttu-id="7ca18-118">_列表_</span><span class="sxs-lookup"><span data-stu-id="7ca18-118">_list_</span></span> <br/> |<span data-ttu-id="7ca18-119">必需</span><span class="sxs-lookup"><span data-stu-id="7ca18-119">Required</span></span>  <br/> |<span data-ttu-id="7ca18-120">**String**</span><span class="sxs-lookup"><span data-stu-id="7ca18-120">**String**</span></span> <br/> |<span data-ttu-id="7ca18-121">要在其中进行搜索的列表。</span><span class="sxs-lookup"><span data-stu-id="7ca18-121">The list in which you want to search.</span></span>  <br/> |
| <span data-ttu-id="7ca18-122">_分隔符_</span><span class="sxs-lookup"><span data-stu-id="7ca18-122">_delimiter_</span></span> <br/> |<span data-ttu-id="7ca18-123">可选</span><span class="sxs-lookup"><span data-stu-id="7ca18-123">Optional</span></span>  <br/> |<span data-ttu-id="7ca18-124">**字符串**</span><span class="sxs-lookup"><span data-stu-id="7ca18-124">**String**</span></span> <br/> | <span data-ttu-id="7ca18-125">要用作_列表_中的分隔符的字符串。</span><span class="sxs-lookup"><span data-stu-id="7ca18-125">The string to use as a delimiter within  _list_.</span></span> <span data-ttu-id="7ca18-126">_分隔符_串的长度不能超过一个字符, 并且包含多字节字符。</span><span class="sxs-lookup"><span data-stu-id="7ca18-126">A  _delimiter_ string can be more than one character in length and include multibyte characters.</span></span> <span data-ttu-id="7ca18-127">默认值是一个分号。</span><span class="sxs-lookup"><span data-stu-id="7ca18-127">The default is a semicolon.</span></span>  <br/> |
| <span data-ttu-id="7ca18-128">_errorvalue_</span><span class="sxs-lookup"><span data-stu-id="7ca18-128">_errorvalue_</span></span> <br/> |<span data-ttu-id="7ca18-129">可选</span><span class="sxs-lookup"><span data-stu-id="7ca18-129">Optional</span></span>  <br/> |<span data-ttu-id="7ca18-130">**Number**</span><span class="sxs-lookup"><span data-stu-id="7ca18-130">**Number**</span></span> <br/> | <span data-ttu-id="7ca18-131">用户指定的在索引超出范围时返回的值。</span><span class="sxs-lookup"><span data-stu-id="7ca18-131">A user-specified value to return if the index is out of range.</span></span> <span data-ttu-id="7ca18-132">默认值是一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="7ca18-132">The default is an empty string.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ca18-133">说明</span><span class="sxs-lookup"><span data-stu-id="7ca18-133">Remarks</span></span>

<span data-ttu-id="7ca18-p105">如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。</span><span class="sxs-lookup"><span data-stu-id="7ca18-p105">If the list begins or ends with a delimiter, a null string is assumed to exist before or after the list. Consecutive delimiters imply a null string in between.</span></span> 
  
<span data-ttu-id="7ca18-136">如果索引超出范围, Visio 将返回一个空字符串或作为*errorvalue*参数提供的可选令牌。</span><span class="sxs-lookup"><span data-stu-id="7ca18-136">If the index is out of range, Visio returns an empty string or the optional token provided as the  *errorvalue*  argument.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="7ca18-137">示例 1</span><span class="sxs-lookup"><span data-stu-id="7ca18-137">Example 1</span></span>

<span data-ttu-id="7ca18-138">索引 (3, "cat; rat;;goat ")</span><span class="sxs-lookup"><span data-stu-id="7ca18-138">INDEX(3,"cat;rat;;goat")</span></span>
  
<span data-ttu-id="7ca18-139">返回“goat”。</span><span class="sxs-lookup"><span data-stu-id="7ca18-139">Returns "goat".</span></span>
  
## <a name="example-2"></a><span data-ttu-id="7ca18-140">示例 2</span><span class="sxs-lookup"><span data-stu-id="7ca18-140">Example 2</span></span>

<span data-ttu-id="7ca18-141">索引 (54, "; 1; 2; 3;",, "错误")</span><span class="sxs-lookup"><span data-stu-id="7ca18-141">INDEX(54,";1;2;3;",,"ERROR")</span></span>
  
<span data-ttu-id="7ca18-142">返回“ERROR”。</span><span class="sxs-lookup"><span data-stu-id="7ca18-142">Returns "ERROR".</span></span>
  

