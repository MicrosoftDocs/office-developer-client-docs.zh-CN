---
title: LEFT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1021757
localization_priority: Normal
ms.assetid: 0c2f6e06-b772-2006-ec7b-8695d097f146
description: 根据指定的字符数, 返回文本字符串中最左侧的字符或字符。
ms.openlocfilehash: aa4141cfc53bd41a6d58e8bc666b18a06fc80245
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427519"
---
# <a name="left-function-visioshapesheet"></a><span data-ttu-id="5c7a5-103">LEFT 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="5c7a5-103">LEFT Function (VisioShapeSheet)</span></span>

<span data-ttu-id="5c7a5-104">根据指定的字符数, 返回文本字符串中最左侧的字符或字符。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-104">Returns the left-most character or characters in a text string, based on the number of characters you specify.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5c7a5-105">语法</span><span class="sxs-lookup"><span data-stu-id="5c7a5-105">Syntax</span></span>

<span data-ttu-id="5c7a5-106">LEFT (\* \* *text* \* \*, [, \* \* *num_chars_opt* \* \*])</span><span class="sxs-lookup"><span data-stu-id="5c7a5-106">LEFT(\*\* *text* \*\*, [, \*\* *num_chars_opt* \*\* ])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5c7a5-107">参数</span><span class="sxs-lookup"><span data-stu-id="5c7a5-107">Parameters</span></span>

|<span data-ttu-id="5c7a5-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-108">**Name**</span></span>|<span data-ttu-id="5c7a5-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-109">**Required/Optional**</span></span>|<span data-ttu-id="5c7a5-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-110">**Data Type**</span></span>|<span data-ttu-id="5c7a5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5c7a5-112">_text_</span><span class="sxs-lookup"><span data-stu-id="5c7a5-112">_text_</span></span> <br/> |<span data-ttu-id="5c7a5-113">必需</span><span class="sxs-lookup"><span data-stu-id="5c7a5-113">Required</span></span>  <br/> |<span data-ttu-id="5c7a5-114">**String**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-114">**String**</span></span> <br/> |<span data-ttu-id="5c7a5-115">包含要提取的字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-115">The text string that contains the characters you want to extract.</span></span>  <br/> |
| <span data-ttu-id="5c7a5-116">_num_chars_opt_</span><span class="sxs-lookup"><span data-stu-id="5c7a5-116">_num_chars_opt_</span></span> <br/> |<span data-ttu-id="5c7a5-117">可选</span><span class="sxs-lookup"><span data-stu-id="5c7a5-117">Optional</span></span>  <br/> |<span data-ttu-id="5c7a5-118">**数值**</span><span class="sxs-lookup"><span data-stu-id="5c7a5-118">**Numeric**</span></span> <br/> |<span data-ttu-id="5c7a5-119">要提取的字符数。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-119">The number of characters you want to extract.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5c7a5-120">返回值</span><span class="sxs-lookup"><span data-stu-id="5c7a5-120">Return value</span></span>

<span data-ttu-id="5c7a5-121">String</span><span class="sxs-lookup"><span data-stu-id="5c7a5-121">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c7a5-122">说明</span><span class="sxs-lookup"><span data-stu-id="5c7a5-122">Remarks</span></span>

<span data-ttu-id="5c7a5-123">_num_chars_opt_的值必须大于或等于零 (0)。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-123">The value of  _num_chars_opt_ must be greater than or equal to zero (0).</span></span> 
  
<span data-ttu-id="5c7a5-124">如果_num_chars_opt_大于文本的长度, 则 LEFT 将返回所有文本。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-124">If  _num_chars_opt_ is greater than the length of the text, LEFT returns all of the text.</span></span> <span data-ttu-id="5c7a5-125">如果省略_num_chars_opt_ , 则假定其为1。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-125">If  _num_chars_opt_ is omitted, it is assumed to be 1.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5c7a5-126">示例</span><span class="sxs-lookup"><span data-stu-id="5c7a5-126">Example</span></span>

<span data-ttu-id="5c7a5-127">LEFT ("January 1, 2004", 3)</span><span class="sxs-lookup"><span data-stu-id="5c7a5-127">LEFT ("January 1, 2004", 3)</span></span> 
  
<span data-ttu-id="5c7a5-128">返回值“Jan”。</span><span class="sxs-lookup"><span data-stu-id="5c7a5-128">Returns the value "Jan".</span></span> 
  

