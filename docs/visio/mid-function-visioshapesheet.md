---
title: MID 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027310
localization_priority: Normal
ms.assetid: 5041d957-1bd9-4d76-cf43-7b4fcd1e7dec
description: 根据指定的字符数，从指定的位置开始，从文本字符串中返回特定数量的字符。
ms.openlocfilehash: 58d5e784e49c8e9fba0bf668626049298783c158
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410264"
---
# <a name="mid-function-visioshapesheet"></a><span data-ttu-id="f297e-103">MID 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="f297e-103">MID Function (VisioShapeSheet)</span></span>

<span data-ttu-id="f297e-104">根据指定的字符数，从指定的位置开始，从文本字符串中返回特定数量的字符。</span><span class="sxs-lookup"><span data-stu-id="f297e-104">Returns a specific number of characters from a text string, starting at the position you specify, based on the number of characters you specify.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f297e-105">语法</span><span class="sxs-lookup"><span data-stu-id="f297e-105">Syntax</span></span>

<span data-ttu-id="f297e-106">MID (\*\* *text* \*\*， \*\* *start_num* \*\*， \*\* *num_chars* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="f297e-106">MID (\*\* *text* \*\*, \*\* *start_num* \*\*, \*\* *num_chars* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f297e-107">参数</span><span class="sxs-lookup"><span data-stu-id="f297e-107">Parameters</span></span>

|<span data-ttu-id="f297e-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f297e-108">**Name**</span></span>|<span data-ttu-id="f297e-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f297e-109">**Required/Optional**</span></span>|<span data-ttu-id="f297e-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f297e-110">**Data Type**</span></span>|<span data-ttu-id="f297e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f297e-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f297e-112">_text_</span><span class="sxs-lookup"><span data-stu-id="f297e-112">_text_</span></span> <br/> |<span data-ttu-id="f297e-113">必需</span><span class="sxs-lookup"><span data-stu-id="f297e-113">Required</span></span>  <br/> |<span data-ttu-id="f297e-114">**String**</span><span class="sxs-lookup"><span data-stu-id="f297e-114">**String**</span></span> <br/> |<span data-ttu-id="f297e-115">包含要提取的字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="f297e-115">The text string that contains the characters you want to extract.</span></span>  <br/> |
| <span data-ttu-id="f297e-116">_start_num_</span><span class="sxs-lookup"><span data-stu-id="f297e-116">_start_num_</span></span> <br/> |<span data-ttu-id="f297e-117">必需</span><span class="sxs-lookup"><span data-stu-id="f297e-117">Required</span></span>  <br/> |<span data-ttu-id="f297e-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="f297e-118">**Number**</span></span> <br/> |<span data-ttu-id="f297e-p101">要提取的第一个字符的位置。文本字符串中第一个字符处于位置 1。</span><span class="sxs-lookup"><span data-stu-id="f297e-p101">The position of the first character you want to extract. The first character in the text string is position 1.</span></span>  <br/> |
| <span data-ttu-id="f297e-121">_num_chars_</span><span class="sxs-lookup"><span data-stu-id="f297e-121">_num_chars_</span></span> <br/> |<span data-ttu-id="f297e-122">必需</span><span class="sxs-lookup"><span data-stu-id="f297e-122">Required</span></span>  <br/> |<span data-ttu-id="f297e-123">**Number**</span><span class="sxs-lookup"><span data-stu-id="f297e-123">**Number**</span></span> <br/> |<span data-ttu-id="f297e-124">要返回的字符数。</span><span class="sxs-lookup"><span data-stu-id="f297e-124">The number of characters to return.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f297e-125">返回值</span><span class="sxs-lookup"><span data-stu-id="f297e-125">Return value</span></span>

<span data-ttu-id="f297e-126">String</span><span class="sxs-lookup"><span data-stu-id="f297e-126">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f297e-127">备注</span><span class="sxs-lookup"><span data-stu-id="f297e-127">Remarks</span></span>

<span data-ttu-id="f297e-128">如果  *start_num*  为：</span><span class="sxs-lookup"><span data-stu-id="f297e-128">If  *start_num*  is:</span></span> 
  
- <span data-ttu-id="f297e-129">大于文本长度  *，MID*  返回空文本 (") 。</span><span class="sxs-lookup"><span data-stu-id="f297e-129">Greater than the length of  *text*  , MID returns "" (empty text).</span></span> 
    
- <span data-ttu-id="f297e-130">小于文本的长度 *，* 但start_num加num_chars超过文本的长度，MID 将返回直到文本 *结尾的字符*。  </span><span class="sxs-lookup"><span data-stu-id="f297e-130">Less than the length of  *text*  , but  *start_num*  plus  *num_chars*  exceeds the length of  *text*  , MID returns the characters up to the end of  *text*  .</span></span> 
    
- <span data-ttu-id="f297e-p102">小于 1，MID 将返回 #VALUE! 错误值。</span><span class="sxs-lookup"><span data-stu-id="f297e-p102">Less than 1, MID returns the #VALUE! error value.</span></span> 
    
<span data-ttu-id="f297e-133">如果  *num_chars*  为负数，MID 将返回 #VALUE！</span><span class="sxs-lookup"><span data-stu-id="f297e-133">If  *num_chars*  is negative, MID returns the #VALUE!</span></span> <span data-ttu-id="f297e-134">错误值。</span><span class="sxs-lookup"><span data-stu-id="f297e-134">error value.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f297e-135">示例</span><span class="sxs-lookup"><span data-stu-id="f297e-135">Example</span></span>

<span data-ttu-id="f297e-136">MID ("SSN 999-99-9999",5,11)</span><span class="sxs-lookup"><span data-stu-id="f297e-136">MID ("SSN 999-99-9999",5,11)</span></span> 
  
<span data-ttu-id="f297e-137">返回 999-99-9999。</span><span class="sxs-lookup"><span data-stu-id="f297e-137">Returns 999-99-9999.</span></span> 
  

