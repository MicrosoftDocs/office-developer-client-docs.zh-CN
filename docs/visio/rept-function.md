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
description: 按照给定的次数重复显示文本。
ms.openlocfilehash: 84e7167fcee426c607e6967aff0530362685dd35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412077"
---
# <a name="rept-function"></a><span data-ttu-id="cc188-103">REPT 函数</span><span class="sxs-lookup"><span data-stu-id="cc188-103">REPT Function</span></span>

<span data-ttu-id="cc188-104">按照给定的次数重复显示文本。</span><span class="sxs-lookup"><span data-stu-id="cc188-104">Repeats text a given number of times.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="cc188-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc188-105">Syntax</span></span>

<span data-ttu-id="cc188-106">REPT (\*\* *text* \*\*， \*\* *number_times* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="cc188-106">REPT (\*\* *text* \*\*, \*\* *number_times* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="cc188-107">参数</span><span class="sxs-lookup"><span data-stu-id="cc188-107">Parameters</span></span>

|<span data-ttu-id="cc188-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="cc188-108">**Name**</span></span>|<span data-ttu-id="cc188-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="cc188-109">**Required/Optional**</span></span>|<span data-ttu-id="cc188-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cc188-110">**Data Type**</span></span>|<span data-ttu-id="cc188-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc188-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cc188-112">_text_</span><span class="sxs-lookup"><span data-stu-id="cc188-112">_text_</span></span> <br/> |<span data-ttu-id="cc188-113">必需</span><span class="sxs-lookup"><span data-stu-id="cc188-113">Required</span></span>  <br/> |<span data-ttu-id="cc188-114">**String**</span><span class="sxs-lookup"><span data-stu-id="cc188-114">**String**</span></span> <br/> | <span data-ttu-id="cc188-115">要重复的文本。</span><span class="sxs-lookup"><span data-stu-id="cc188-115">The text you want to repeat.</span></span>  <br/> |
| <span data-ttu-id="cc188-116">_number_times_</span><span class="sxs-lookup"><span data-stu-id="cc188-116">_number_times_</span></span> <br/> |<span data-ttu-id="cc188-117">必需</span><span class="sxs-lookup"><span data-stu-id="cc188-117">Required</span></span>  <br/> |<span data-ttu-id="cc188-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="cc188-118">**Number**</span></span> <br/> |<span data-ttu-id="cc188-119">指定文本重复次数的正数。</span><span class="sxs-lookup"><span data-stu-id="cc188-119">A positive number specifying the number of times to repeat text.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc188-120">备注</span><span class="sxs-lookup"><span data-stu-id="cc188-120">Remarks</span></span>

<span data-ttu-id="cc188-121">如果  *number_times*  为：</span><span class="sxs-lookup"><span data-stu-id="cc188-121">If  *number_times*  is:</span></span> 
  
- <span data-ttu-id="cc188-122">为零 (0)，REPT 将返回“”（空文本）。</span><span class="sxs-lookup"><span data-stu-id="cc188-122">Zero (0), REPT returns "" (empty text).</span></span>
    
- <span data-ttu-id="cc188-123">不是整数，将被截断。</span><span class="sxs-lookup"><span data-stu-id="cc188-123">Not an interger, it is truncated.</span></span>
    
## <a name="example"></a><span data-ttu-id="cc188-124">示例</span><span class="sxs-lookup"><span data-stu-id="cc188-124">Example</span></span>

<span data-ttu-id="cc188-125">REPT (" \* "， 5) </span><span class="sxs-lookup"><span data-stu-id="cc188-125">REPT ("\*", 5)</span></span> 
  
<span data-ttu-id="cc188-126">返回 \* \* \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="cc188-126">Returns \*\*\*\*\*.</span></span> 
  

