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
# <a name="lookup-function"></a><span data-ttu-id="34b43-103">LOOKUP 函数</span><span class="sxs-lookup"><span data-stu-id="34b43-103">LOOKUP Function</span></span>

<span data-ttu-id="34b43-104">返回一个从零开始索引，该索引指示子字符串键在列表中的位置，如果目标字符串包含分隔 _符_，则返回 -1。</span><span class="sxs-lookup"><span data-stu-id="34b43-104">Returns a zero-based index that indicates the location of the substring  _key_ in a  _list_, or returns -1 if the target string contains the  _delimiter_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="34b43-105">语法</span><span class="sxs-lookup"><span data-stu-id="34b43-105">Syntax</span></span>

<span data-ttu-id="34b43-106">LOOKUP (" \*\* *key* \*\* "，" \*\* *list* \*\* "[，" \*\* *delimiter* \*\* "]) </span><span class="sxs-lookup"><span data-stu-id="34b43-106">LOOKUP(" \*\* *key* \*\* "," \*\* *list* \*\* "[," \*\* *delimiter* \*\* "])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="34b43-107">参数</span><span class="sxs-lookup"><span data-stu-id="34b43-107">Parameters</span></span>

|<span data-ttu-id="34b43-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="34b43-108">**Name**</span></span>|<span data-ttu-id="34b43-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="34b43-109">**Required/Optional**</span></span>|<span data-ttu-id="34b43-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="34b43-110">**Data Type**</span></span>|<span data-ttu-id="34b43-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="34b43-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="34b43-112">_key_</span><span class="sxs-lookup"><span data-stu-id="34b43-112">_key_</span></span> <br/> |<span data-ttu-id="34b43-113">必需</span><span class="sxs-lookup"><span data-stu-id="34b43-113">Required</span></span>  <br/> |<span data-ttu-id="34b43-114">**String**</span><span class="sxs-lookup"><span data-stu-id="34b43-114">**String**</span></span> <br/> |<span data-ttu-id="34b43-115">要查找的字符串。</span><span class="sxs-lookup"><span data-stu-id="34b43-115">The string that you want to look up.</span></span>  <br/> |
| <span data-ttu-id="34b43-116">_列表_</span><span class="sxs-lookup"><span data-stu-id="34b43-116">_list_</span></span> <br/> |<span data-ttu-id="34b43-117">必需</span><span class="sxs-lookup"><span data-stu-id="34b43-117">Required</span></span>  <br/> |<span data-ttu-id="34b43-118">**String**</span><span class="sxs-lookup"><span data-stu-id="34b43-118">**String**</span></span> <br/> | <span data-ttu-id="34b43-119">要在其中进行搜索的列表。</span><span class="sxs-lookup"><span data-stu-id="34b43-119">The list in which you want to search.</span></span>  <br/> |
| <span data-ttu-id="34b43-120">_delimiter_</span><span class="sxs-lookup"><span data-stu-id="34b43-120">_delimiter_</span></span> <br/> |<span data-ttu-id="34b43-121">可选</span><span class="sxs-lookup"><span data-stu-id="34b43-121">Optional</span></span>  <br/> |<span data-ttu-id="34b43-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="34b43-122">**String**</span></span> <br/> | <span data-ttu-id="34b43-123">要用作列表 内分隔符的  _字符串_。</span><span class="sxs-lookup"><span data-stu-id="34b43-123">The string to use as a delimiter within  _list_.</span></span> <span data-ttu-id="34b43-124">_分隔符字符串_ 的长度可以超过一个字符，并且可以包含多字节字符。</span><span class="sxs-lookup"><span data-stu-id="34b43-124">A  _delimiter_ string can be more than one character in length and may include multibyte characters.</span></span> <span data-ttu-id="34b43-125">默认值是一个分号。</span><span class="sxs-lookup"><span data-stu-id="34b43-125">The default is a semicolon.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="34b43-126">返回值</span><span class="sxs-lookup"><span data-stu-id="34b43-126">Return value</span></span>

<span data-ttu-id="34b43-127">Numeric</span><span class="sxs-lookup"><span data-stu-id="34b43-127">Numeric</span></span>
  
## <a name="remarks"></a><span data-ttu-id="34b43-128">备注</span><span class="sxs-lookup"><span data-stu-id="34b43-128">Remarks</span></span>

<span data-ttu-id="34b43-p102">LOOKUP 函数使用不区分大小写的搜索。如果列表以一个分隔符开始或结束，则认为在列表前或列表后存在一个空字符串。连续的分隔符表示其间为空字符串。</span><span class="sxs-lookup"><span data-stu-id="34b43-p102">The LOOKUP function uses a case-insensitive search. If the list begins or ends with a delimiter, a null string is assumed to exist before or after the list. Consecutive delimiters imply a null string in between.</span></span> 
  
<span data-ttu-id="34b43-p103">所有参数都必须是字符串，或能够转换为字符串的表达式。否则，空字符串将替代有问题的参数。</span><span class="sxs-lookup"><span data-stu-id="34b43-p103">All the arguments must be strings or expressions that can be converted to strings. If they are not, an empty string is substituted for the offending argument.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="34b43-134">示例 1</span><span class="sxs-lookup"><span data-stu-id="34b43-134">Example 1</span></span>

<span data-ttu-id="34b43-135">LOOKUP ("，cat;rat;;") </span><span class="sxs-lookup"><span data-stu-id="34b43-135">LOOKUP("rat","cat;rat;;goat")</span></span>
  
<span data-ttu-id="34b43-136">返回 1。</span><span class="sxs-lookup"><span data-stu-id="34b43-136">Returns 1.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="34b43-137">示例 2</span><span class="sxs-lookup"><span data-stu-id="34b43-137">Example 2</span></span>

<span data-ttu-id="34b43-138">LOOKUP ("，";cat;rat;;") </span><span class="sxs-lookup"><span data-stu-id="34b43-138">LOOKUP("",";cat;rat;;goat")</span></span>
  
<span data-ttu-id="34b43-139">返回 0。</span><span class="sxs-lookup"><span data-stu-id="34b43-139">Returns 0.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="34b43-140">示例 3</span><span class="sxs-lookup"><span data-stu-id="34b43-140">Example 3</span></span>

<span data-ttu-id="34b43-141">LOOKUP ("t"，"cat;rat;;"，"a") </span><span class="sxs-lookup"><span data-stu-id="34b43-141">LOOKUP("t","cat;rat;;goat","a")</span></span>
  
<span data-ttu-id="34b43-142">返回 3。</span><span class="sxs-lookup"><span data-stu-id="34b43-142">Returns 3.</span></span>
  

