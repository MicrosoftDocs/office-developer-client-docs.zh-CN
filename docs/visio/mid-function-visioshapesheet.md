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
description: 返回特定的文本字符串，指定，位置开始中的字符数根据您指定的字符数。
ms.openlocfilehash: 96e697211ebf6ea61ddf0b749d8e1259f2a1e53d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780772"
---
# <a name="mid-function-visioshapesheet"></a><span data-ttu-id="24549-103">MID 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="24549-103">MID Function (VisioShapeSheet)</span></span>

<span data-ttu-id="24549-104">返回特定的文本字符串，指定，位置开始中的字符数根据您指定的字符数。</span><span class="sxs-lookup"><span data-stu-id="24549-104">Returns a specific number of characters from a text string, starting at the position you specify, based on the number of characters you specify.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="24549-105">语法</span><span class="sxs-lookup"><span data-stu-id="24549-105">Syntax</span></span>

<span data-ttu-id="24549-106">MID (* **文本** *，* * *start_num* * *，* * *num_chars* * *)</span><span class="sxs-lookup"><span data-stu-id="24549-106">MID (** *text* **, ** *start_num* **, ** *num_chars* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="24549-107">参数</span><span class="sxs-lookup"><span data-stu-id="24549-107">Parameters</span></span>

|<span data-ttu-id="24549-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="24549-108">**Name**</span></span>|<span data-ttu-id="24549-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="24549-109">**Required/Optional**</span></span>|<span data-ttu-id="24549-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="24549-110">**Data Type**</span></span>|<span data-ttu-id="24549-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="24549-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="24549-112">_text_</span><span class="sxs-lookup"><span data-stu-id="24549-112">_text_</span></span> <br/> |<span data-ttu-id="24549-113">必需</span><span class="sxs-lookup"><span data-stu-id="24549-113">Required</span></span>  <br/> |<span data-ttu-id="24549-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="24549-114">**String**</span></span> <br/> |<span data-ttu-id="24549-115">包含要提取的字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="24549-115">The text string that contains the characters you want to extract.</span></span>  <br/> |
| <span data-ttu-id="24549-116">_start_num_</span><span class="sxs-lookup"><span data-stu-id="24549-116">_start_num_</span></span> <br/> |<span data-ttu-id="24549-117">必需</span><span class="sxs-lookup"><span data-stu-id="24549-117">Required</span></span>  <br/> |<span data-ttu-id="24549-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="24549-118">**Number**</span></span> <br/> |<span data-ttu-id="24549-p101">要提取的第一个字符的位置。文本字符串中第一个字符处于位置 1。</span><span class="sxs-lookup"><span data-stu-id="24549-p101">The position of the first character you want to extract. The first character in the text string is position 1.</span></span>  <br/> |
| <span data-ttu-id="24549-121">_num_chars_</span><span class="sxs-lookup"><span data-stu-id="24549-121">_num_chars_</span></span> <br/> |<span data-ttu-id="24549-122">必需</span><span class="sxs-lookup"><span data-stu-id="24549-122">Required</span></span>  <br/> |<span data-ttu-id="24549-123">**编号**</span><span class="sxs-lookup"><span data-stu-id="24549-123">**Number**</span></span> <br/> |<span data-ttu-id="24549-124">要返回的字符数。</span><span class="sxs-lookup"><span data-stu-id="24549-124">The number of characters to return.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="24549-125">返回值</span><span class="sxs-lookup"><span data-stu-id="24549-125">Return value</span></span>

<span data-ttu-id="24549-126">String</span><span class="sxs-lookup"><span data-stu-id="24549-126">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="24549-127">注解</span><span class="sxs-lookup"><span data-stu-id="24549-127">Remarks</span></span>

<span data-ttu-id="24549-128">如果*start_num:*</span><span class="sxs-lookup"><span data-stu-id="24549-128">If  *start_num*  is:</span></span> 
  
- <span data-ttu-id="24549-129">大于的长度*文本*，MID 将返回""（空文本）。</span><span class="sxs-lookup"><span data-stu-id="24549-129">Greater than the length of  *text*  , MID returns "" (empty text).</span></span> 
    
- <span data-ttu-id="24549-130">小于长度的*文本*，但*start_num*加上*num_chars*超过*text*的长度，MID 将返回到*文本*末尾的字符。</span><span class="sxs-lookup"><span data-stu-id="24549-130">Less than the length of  *text*  , but  *start_num*  plus  *num_chars*  exceeds the length of  *text*  , MID returns the characters up to the end of  *text*  .</span></span> 
    
- <span data-ttu-id="24549-p102">小于 1，MID 将返回 #VALUE! 错误值。</span><span class="sxs-lookup"><span data-stu-id="24549-p102">Less than 1, MID returns the #VALUE! error value.</span></span> 
    
<span data-ttu-id="24549-133">如果*num_chars*为负数，MID 将返回 #VALUE ！。</span><span class="sxs-lookup"><span data-stu-id="24549-133">If  *num_chars*  is negative, MID returns the #VALUE!</span></span> <span data-ttu-id="24549-134">错误值。</span><span class="sxs-lookup"><span data-stu-id="24549-134">error value.</span></span> 
  
## <a name="example"></a><span data-ttu-id="24549-135">示例</span><span class="sxs-lookup"><span data-stu-id="24549-135">Example</span></span>

<span data-ttu-id="24549-136">MID ("SSN 999-99-9999",5,11)</span><span class="sxs-lookup"><span data-stu-id="24549-136">MID ("SSN 999-99-9999",5,11)</span></span> 
  
<span data-ttu-id="24549-137">返回 999-99-9999。</span><span class="sxs-lookup"><span data-stu-id="24549-137">Returns 999-99-9999.</span></span> 
  

