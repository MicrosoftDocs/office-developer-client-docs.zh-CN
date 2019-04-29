---
title: RIGHT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027314
localization_priority: Normal
ms.assetid: 910f0297-d588-2048-f308-03f3c2389bba
description: 根据指定的字符数, 返回文本字符串中的最后一个字符或多个字符。
ms.openlocfilehash: faf14ef55b34e51bac11129d6857e381d07357c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411454"
---
# <a name="right-function-visioshapesheet"></a><span data-ttu-id="88ae5-103">RIGHT 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="88ae5-103">RIGHT Function (VisioShapeSheet)</span></span>

<span data-ttu-id="88ae5-104">根据指定的字符数, 返回文本字符串中的最后一个字符或多个字符。</span><span class="sxs-lookup"><span data-stu-id="88ae5-104">Returns the last character or characters in a text string, based on the number of characters you specify.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="88ae5-105">语法</span><span class="sxs-lookup"><span data-stu-id="88ae5-105">Syntax</span></span>

<span data-ttu-id="88ae5-106">RIGHT (\* \* *text* \* \* [, \* \* *num_chars_opt* \* \*])</span><span class="sxs-lookup"><span data-stu-id="88ae5-106">RIGHT(\*\* *text* \*\* [, \*\* *num_chars_opt* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="88ae5-107">参数</span><span class="sxs-lookup"><span data-stu-id="88ae5-107">Parameters</span></span>

|<span data-ttu-id="88ae5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="88ae5-108">**Name**</span></span>|<span data-ttu-id="88ae5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="88ae5-109">**Required/Optional**</span></span>|<span data-ttu-id="88ae5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="88ae5-110">**Data Type**</span></span>|<span data-ttu-id="88ae5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="88ae5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="88ae5-112">_text_</span><span class="sxs-lookup"><span data-stu-id="88ae5-112">_text_</span></span> <br/> |<span data-ttu-id="88ae5-113">必需</span><span class="sxs-lookup"><span data-stu-id="88ae5-113">Required</span></span>  <br/> |<span data-ttu-id="88ae5-114">**String**</span><span class="sxs-lookup"><span data-stu-id="88ae5-114">**String**</span></span> <br/> | <span data-ttu-id="88ae5-115">包含要提取的字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="88ae5-115">The text string containing the characters you want to extract.</span></span>  <br/> |
| <span data-ttu-id="88ae5-116">_num_chars_opt_</span><span class="sxs-lookup"><span data-stu-id="88ae5-116">_num_chars_opt_</span></span> <br/> |<span data-ttu-id="88ae5-117">可选</span><span class="sxs-lookup"><span data-stu-id="88ae5-117">Optional</span></span>  <br/> |<span data-ttu-id="88ae5-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="88ae5-118">**Number**</span></span> <br/> |<span data-ttu-id="88ae5-119">要提取的字符数。</span><span class="sxs-lookup"><span data-stu-id="88ae5-119">The number of characters you want to extract.</span></span> <span data-ttu-id="88ae5-120">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="88ae5-120">The default is 1.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="88ae5-121">返回值</span><span class="sxs-lookup"><span data-stu-id="88ae5-121">Return value</span></span>

<span data-ttu-id="88ae5-122">String</span><span class="sxs-lookup"><span data-stu-id="88ae5-122">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="88ae5-123">说明</span><span class="sxs-lookup"><span data-stu-id="88ae5-123">Remarks</span></span>

<span data-ttu-id="88ae5-124">_num_chars_opt_的值必须大于或等于零 (0)。</span><span class="sxs-lookup"><span data-stu-id="88ae5-124">The value of  _num_chars_opt_ must be greater than or equal to zero (0).</span></span> 
  
<span data-ttu-id="88ae5-125">如果_num_chars_opt_大于文本的长度, 则用鼠标右键返回所有文本。</span><span class="sxs-lookup"><span data-stu-id="88ae5-125">If  _num_chars_opt_ is greater than the length of the text, RIGHT returns all of the text.</span></span> <span data-ttu-id="88ae5-126">如果省略_num_chars_opt_ , 则假定其为1。</span><span class="sxs-lookup"><span data-stu-id="88ae5-126">If  _num_chars_opt_ is omitted, it is assumed to be 1.</span></span> 
  
## <a name="example"></a><span data-ttu-id="88ae5-127">示例</span><span class="sxs-lookup"><span data-stu-id="88ae5-127">Example</span></span>

<span data-ttu-id="88ae5-128">RIGHT ("January 1, 2004", 4)</span><span class="sxs-lookup"><span data-stu-id="88ae5-128">RIGHT ("January 1, 2004", 4)</span></span> 
  
<span data-ttu-id="88ae5-129">返回值 2004。</span><span class="sxs-lookup"><span data-stu-id="88ae5-129">Returns the value 2004.</span></span> 
  

