---
title: REPT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027335
localization_priority: Normal
ms.assetid: 53362a32-ac27-42a3-ace1-c6184ab20b52
description: 将文本重复给定的次数。
ms.openlocfilehash: 761f2f95824d5bdab4995b2867bfeac6be64bc12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781120"
---
# <a name="rept-function"></a><span data-ttu-id="b9463-103">REPT 函数</span><span class="sxs-lookup"><span data-stu-id="b9463-103">REPT Function</span></span>

<span data-ttu-id="b9463-104">将文本重复给定的次数。</span><span class="sxs-lookup"><span data-stu-id="b9463-104">Repeats text a given number of times.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b9463-105">语法</span><span class="sxs-lookup"><span data-stu-id="b9463-105">Syntax</span></span>

<span data-ttu-id="b9463-106">REPT (* **文本** *，* * *number_times* * *)</span><span class="sxs-lookup"><span data-stu-id="b9463-106">REPT (** *text* **, ** *number_times* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b9463-107">参数</span><span class="sxs-lookup"><span data-stu-id="b9463-107">Parameters</span></span>

|<span data-ttu-id="b9463-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b9463-108">**Name**</span></span>|<span data-ttu-id="b9463-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b9463-109">**Required/Optional**</span></span>|<span data-ttu-id="b9463-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b9463-110">**Data Type**</span></span>|<span data-ttu-id="b9463-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9463-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b9463-112">_text_</span><span class="sxs-lookup"><span data-stu-id="b9463-112">_text_</span></span> <br/> |<span data-ttu-id="b9463-113">必需</span><span class="sxs-lookup"><span data-stu-id="b9463-113">Required</span></span>  <br/> |<span data-ttu-id="b9463-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="b9463-114">**String**</span></span> <br/> | <span data-ttu-id="b9463-115">要重复的文本。</span><span class="sxs-lookup"><span data-stu-id="b9463-115">The text you want to repeat.</span></span>  <br/> |
| <span data-ttu-id="b9463-116">_number_times_</span><span class="sxs-lookup"><span data-stu-id="b9463-116">_number_times_</span></span> <br/> |<span data-ttu-id="b9463-117">必需</span><span class="sxs-lookup"><span data-stu-id="b9463-117">Required</span></span>  <br/> |<span data-ttu-id="b9463-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="b9463-118">**Number**</span></span> <br/> |<span data-ttu-id="b9463-119">指定文本重复次数的正数。</span><span class="sxs-lookup"><span data-stu-id="b9463-119">A positive number specifying the number of times to repeat text.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b9463-120">注解</span><span class="sxs-lookup"><span data-stu-id="b9463-120">Remarks</span></span>

<span data-ttu-id="b9463-121">如果*number_times:*</span><span class="sxs-lookup"><span data-stu-id="b9463-121">If  *number_times*  is:</span></span> 
  
- <span data-ttu-id="b9463-122">为零 (0)，REPT 将返回“”（空文本）。</span><span class="sxs-lookup"><span data-stu-id="b9463-122">Zero (0), REPT returns "" (empty text).</span></span>
    
- <span data-ttu-id="b9463-123">不是整数，将被截断。</span><span class="sxs-lookup"><span data-stu-id="b9463-123">Not an interger, it is truncated.</span></span>
    
## <a name="example"></a><span data-ttu-id="b9463-124">示例</span><span class="sxs-lookup"><span data-stu-id="b9463-124">Example</span></span>

<span data-ttu-id="b9463-125">REPT ("\*"，5)</span><span class="sxs-lookup"><span data-stu-id="b9463-125">REPT ("\*", 5)</span></span> 
  
<span data-ttu-id="b9463-126">返回\* \* \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="b9463-126">Returns \*\*\*\*\*.</span></span> 
  

