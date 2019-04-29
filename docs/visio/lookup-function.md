---
title: LOOKUP 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251457
localization_priority: Normal
ms.assetid: cb6ec664-6062-75d0-1514-8058b98c2c36
description: 返回基于零的索引，该索引指示子字符串 key 在 list 中的位置，或者如果目标字符串包含 delimiter，则返回 -1。
ms.openlocfilehash: 10fc32e6e979ab819246161dedfb1183c2683a99
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410327"
---
# <a name="lookup-function"></a><span data-ttu-id="4c808-103">LOOKUP 函数</span><span class="sxs-lookup"><span data-stu-id="4c808-103">LOOKUP Function</span></span>

<span data-ttu-id="4c808-104">返回一个从零开始的索引, 该索引指示子字符串_键_在_列表_中的位置, 或者, 如果目标字符串包含_分隔符_, 则返回-1。</span><span class="sxs-lookup"><span data-stu-id="4c808-104">Returns a zero-based index that indicates the location of the substring  _key_ in a  _list_, or returns -1 if the target string contains the  _delimiter_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4c808-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c808-105">Syntax</span></span>

<span data-ttu-id="4c808-106">LOOKUP ("\* \* *key* \* *", "* \* *list* \* *" [, "* **定界符** \*"])</span><span class="sxs-lookup"><span data-stu-id="4c808-106">LOOKUP(" \*\* *key* \*\* "," \*\* *list* \*\* "[," \*\* *delimiter* \*\* "])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4c808-107">参数</span><span class="sxs-lookup"><span data-stu-id="4c808-107">Parameters</span></span>

|<span data-ttu-id="4c808-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="4c808-108">**Name**</span></span>|<span data-ttu-id="4c808-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4c808-109">**Required/Optional**</span></span>|<span data-ttu-id="4c808-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4c808-110">**Data Type**</span></span>|<span data-ttu-id="4c808-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c808-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4c808-112">_key_</span><span class="sxs-lookup"><span data-stu-id="4c808-112">_key_</span></span> <br/> |<span data-ttu-id="4c808-113">必需</span><span class="sxs-lookup"><span data-stu-id="4c808-113">Required</span></span>  <br/> |<span data-ttu-id="4c808-114">**String**</span><span class="sxs-lookup"><span data-stu-id="4c808-114">**String**</span></span> <br/> |<span data-ttu-id="4c808-115">要查找的字符串。</span><span class="sxs-lookup"><span data-stu-id="4c808-115">The string that you want to look up.</span></span>  <br/> |
| <span data-ttu-id="4c808-116">_列表_</span><span class="sxs-lookup"><span data-stu-id="4c808-116">_list_</span></span> <br/> |<span data-ttu-id="4c808-117">必需</span><span class="sxs-lookup"><span data-stu-id="4c808-117">Required</span></span>  <br/> |<span data-ttu-id="4c808-118">**String**</span><span class="sxs-lookup"><span data-stu-id="4c808-118">**String**</span></span> <br/> | <span data-ttu-id="4c808-119">要在其中进行搜索的列表。</span><span class="sxs-lookup"><span data-stu-id="4c808-119">The list in which you want to search.</span></span>  <br/> |
| <span data-ttu-id="4c808-120">_分隔符_</span><span class="sxs-lookup"><span data-stu-id="4c808-120">_delimiter_</span></span> <br/> |<span data-ttu-id="4c808-121">可选</span><span class="sxs-lookup"><span data-stu-id="4c808-121">Optional</span></span>  <br/> |<span data-ttu-id="4c808-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="4c808-122">**String**</span></span> <br/> | <span data-ttu-id="4c808-123">要用作_列表_中的分隔符的字符串。</span><span class="sxs-lookup"><span data-stu-id="4c808-123">The string to use as a delimiter within  _list_.</span></span> <span data-ttu-id="4c808-124">_分隔符_串的长度不能超过一个字符, 并且可以包含多字节字符。</span><span class="sxs-lookup"><span data-stu-id="4c808-124">A  _delimiter_ string can be more than one character in length and may include multibyte characters.</span></span> <span data-ttu-id="4c808-125">默认值是一个分号。</span><span class="sxs-lookup"><span data-stu-id="4c808-125">The default is a semicolon.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4c808-126">返回值</span><span class="sxs-lookup"><span data-stu-id="4c808-126">Return value</span></span>

<span data-ttu-id="4c808-127">数值</span><span class="sxs-lookup"><span data-stu-id="4c808-127">Numeric</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c808-128">说明</span><span class="sxs-lookup"><span data-stu-id="4c808-128">Remarks</span></span>

<span data-ttu-id="4c808-p102">LOOKUP 函数使用不区分大小写的搜索。如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。</span><span class="sxs-lookup"><span data-stu-id="4c808-p102">The LOOKUP function uses a case-insensitive search. If the list begins or ends with a delimiter, a null string is assumed to exist before or after the list. Consecutive delimiters imply a null string in between.</span></span> 
  
<span data-ttu-id="4c808-p103">所有参数都必须是字符串，或能够转换为字符串的表达式。否则，空字符串将替代有问题的参数。</span><span class="sxs-lookup"><span data-stu-id="4c808-p103">All the arguments must be strings or expressions that can be converted to strings. If they are not, an empty string is substituted for the offending argument.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="4c808-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="4c808-134">Example 1</span></span>

<span data-ttu-id="4c808-135">查找 ("rat", "cat; rat;;goat ")</span><span class="sxs-lookup"><span data-stu-id="4c808-135">LOOKUP("rat","cat;rat;;goat")</span></span>
  
<span data-ttu-id="4c808-136">返回 1。</span><span class="sxs-lookup"><span data-stu-id="4c808-136">Returns 1.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="4c808-137">示例 2</span><span class="sxs-lookup"><span data-stu-id="4c808-137">Example 2</span></span>

<span data-ttu-id="4c808-138">查找 ("", "; cat; rat;;goat ")</span><span class="sxs-lookup"><span data-stu-id="4c808-138">LOOKUP("",";cat;rat;;goat")</span></span>
  
<span data-ttu-id="4c808-139">返回 0。</span><span class="sxs-lookup"><span data-stu-id="4c808-139">Returns 0.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="4c808-140">示例 3</span><span class="sxs-lookup"><span data-stu-id="4c808-140">Example 3</span></span>

<span data-ttu-id="4c808-141">查找 ("t"、"cat; rat;;goat "," a ")</span><span class="sxs-lookup"><span data-stu-id="4c808-141">LOOKUP("t","cat;rat;;goat","a")</span></span>
  
<span data-ttu-id="4c808-142">返回 3。</span><span class="sxs-lookup"><span data-stu-id="4c808-142">Returns 3.</span></span>
  

