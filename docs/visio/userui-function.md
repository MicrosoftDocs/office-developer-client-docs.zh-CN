---
title: USERUI 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251511
localization_priority: Normal
ms.assetid: c01dd938-677c-b2ba-8f56-4638e7e988fd
description: 根据 state 的值计算两个表达式中的一个。
ms.openlocfilehash: 544bb2b19dc610591afc78c407301098fac9c7c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420344"
---
# <a name="userui-function"></a><span data-ttu-id="a11a6-103">USERUI 函数</span><span class="sxs-lookup"><span data-stu-id="a11a6-103">USERUI Function</span></span>

<span data-ttu-id="a11a6-104">根据_state_的值计算两个表达式中的一个。</span><span class="sxs-lookup"><span data-stu-id="a11a6-104">Evaluates one of the two expressions depending on the value of  _state_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a11a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="a11a6-105">Syntax</span></span>

<span data-ttu-id="a11a6-106">USERUI (\* \* *state* \* \*, \* \* *defaultexpression* \* \*, \* \* *userexpression* \* \*)</span><span class="sxs-lookup"><span data-stu-id="a11a6-106">USERUI(\*\* *state* \*\*, \*\* *defaultexpression* \*\*, \*\* *userexpression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a11a6-107">参数</span><span class="sxs-lookup"><span data-stu-id="a11a6-107">Parameters</span></span>

|<span data-ttu-id="a11a6-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a11a6-108">**Name**</span></span>|<span data-ttu-id="a11a6-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a11a6-109">**Required/Optional**</span></span>|<span data-ttu-id="a11a6-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a11a6-110">**Data Type**</span></span>|<span data-ttu-id="a11a6-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a11a6-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a11a6-112">_state_</span><span class="sxs-lookup"><span data-stu-id="a11a6-112">_state_</span></span> <br/> |<span data-ttu-id="a11a6-113">必需</span><span class="sxs-lookup"><span data-stu-id="a11a6-113">Required</span></span>  <br/> |<span data-ttu-id="a11a6-114">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="a11a6-114">**Boolean**</span></span> <br/> |<span data-ttu-id="a11a6-115">确定要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="a11a6-115">Determines which expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="a11a6-116">_defaultexpression_</span><span class="sxs-lookup"><span data-stu-id="a11a6-116">_defaultexpression_</span></span> <br/> |<span data-ttu-id="a11a6-117">必需</span><span class="sxs-lookup"><span data-stu-id="a11a6-117">Required</span></span>  <br/> |<span data-ttu-id="a11a6-118">**String**</span><span class="sxs-lookup"><span data-stu-id="a11a6-118">**String**</span></span> <br/> |<span data-ttu-id="a11a6-119">默认表达式。</span><span class="sxs-lookup"><span data-stu-id="a11a6-119">The default expression.</span></span>  <br/> |
| <span data-ttu-id="a11a6-120">_userexpression_</span><span class="sxs-lookup"><span data-stu-id="a11a6-120">_userexpression_</span></span> <br/> |<span data-ttu-id="a11a6-121">必需</span><span class="sxs-lookup"><span data-stu-id="a11a6-121">Required</span></span>  <br/> |<span data-ttu-id="a11a6-122">**String**</span><span class="sxs-lookup"><span data-stu-id="a11a6-122">**String**</span></span> <br/> |<span data-ttu-id="a11a6-123">用户提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="a11a6-123">An expression supplied by the user.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a11a6-124">说明</span><span class="sxs-lookup"><span data-stu-id="a11a6-124">Remarks</span></span>

<span data-ttu-id="a11a6-125">如果_state_为 0, 则 USERUI 函数将计算_defaultexpression_。</span><span class="sxs-lookup"><span data-stu-id="a11a6-125">If  _state_ is 0, the USERUI function evaluates the  _defaultexpression_.</span></span> <span data-ttu-id="a11a6-126">如果_state_为 1, 则计算_userexpression_。</span><span class="sxs-lookup"><span data-stu-id="a11a6-126">If  _state_ is 1, it evaluates the  _userexpression_.</span></span>
  
## <a name="example"></a><span data-ttu-id="a11a6-127">示例</span><span class="sxs-lookup"><span data-stu-id="a11a6-127">Example</span></span>

<span data-ttu-id="a11a6-128">USERUI (1, 如果 (Width\>6in, 6in, width), width\*0.75)</span><span class="sxs-lookup"><span data-stu-id="a11a6-128">USERUI(1, if(Width\>6in, 6in, Width), Width\*0.75)</span></span> 
  
<span data-ttu-id="a11a6-129">计算表达式 Width\*. 075 并返回结果。</span><span class="sxs-lookup"><span data-stu-id="a11a6-129">Evaluates the expression Width\*.075 and returns the result.</span></span> 
  

