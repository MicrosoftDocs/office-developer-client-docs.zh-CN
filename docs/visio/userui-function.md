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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331323"
---
# <a name="userui-function"></a><span data-ttu-id="3b2d1-103">USERUI 函数</span><span class="sxs-lookup"><span data-stu-id="3b2d1-103">USERUI Function</span></span>

<span data-ttu-id="3b2d1-104">根据_state_的值计算两个表达式中的一个。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-104">Evaluates one of the two expressions depending on the value of  _state_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3b2d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="3b2d1-105">Syntax</span></span>

<span data-ttu-id="3b2d1-106">USERUI (\* \* *state* \* \*, \* \* *defaultexpression* \* \*, \* \* *userexpression* \* \*)</span><span class="sxs-lookup"><span data-stu-id="3b2d1-106">USERUI(\*\* *state* \*\*, \*\* *defaultexpression* \*\*, \*\* *userexpression* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3b2d1-107">参数</span><span class="sxs-lookup"><span data-stu-id="3b2d1-107">Parameters</span></span>

|<span data-ttu-id="3b2d1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-108">**Name**</span></span>|<span data-ttu-id="3b2d1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-109">**Required/Optional**</span></span>|<span data-ttu-id="3b2d1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-110">**Data Type**</span></span>|<span data-ttu-id="3b2d1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3b2d1-112">_state_</span><span class="sxs-lookup"><span data-stu-id="3b2d1-112">_state_</span></span> <br/> |<span data-ttu-id="3b2d1-113">必需</span><span class="sxs-lookup"><span data-stu-id="3b2d1-113">Required</span></span>  <br/> |<span data-ttu-id="3b2d1-114">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-114">**Boolean**</span></span> <br/> |<span data-ttu-id="3b2d1-115">确定要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-115">Determines which expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="3b2d1-116">_defaultexpression_</span><span class="sxs-lookup"><span data-stu-id="3b2d1-116">_defaultexpression_</span></span> <br/> |<span data-ttu-id="3b2d1-117">必需</span><span class="sxs-lookup"><span data-stu-id="3b2d1-117">Required</span></span>  <br/> |<span data-ttu-id="3b2d1-118">**String**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-118">**String**</span></span> <br/> |<span data-ttu-id="3b2d1-119">默认表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-119">The default expression.</span></span>  <br/> |
| <span data-ttu-id="3b2d1-120">_userexpression_</span><span class="sxs-lookup"><span data-stu-id="3b2d1-120">_userexpression_</span></span> <br/> |<span data-ttu-id="3b2d1-121">必需</span><span class="sxs-lookup"><span data-stu-id="3b2d1-121">Required</span></span>  <br/> |<span data-ttu-id="3b2d1-122">**String**</span><span class="sxs-lookup"><span data-stu-id="3b2d1-122">**String**</span></span> <br/> |<span data-ttu-id="3b2d1-123">用户提供的表达式。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-123">An expression supplied by the user.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3b2d1-124">注解</span><span class="sxs-lookup"><span data-stu-id="3b2d1-124">Remarks</span></span>

<span data-ttu-id="3b2d1-125">如果_state_为 0, 则 USERUI 函数将计算_defaultexpression_。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-125">If  _state_ is 0, the USERUI function evaluates the  _defaultexpression_.</span></span> <span data-ttu-id="3b2d1-126">如果_state_为 1, 则计算_userexpression_。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-126">If  _state_ is 1, it evaluates the  _userexpression_.</span></span>
  
## <a name="example"></a><span data-ttu-id="3b2d1-127">示例</span><span class="sxs-lookup"><span data-stu-id="3b2d1-127">Example</span></span>

<span data-ttu-id="3b2d1-128">USERUI (1, 如果 (Width\>6in, 6in, width), width\*0.75)</span><span class="sxs-lookup"><span data-stu-id="3b2d1-128">USERUI(1, if(Width\>6in, 6in, Width), Width\*0.75)</span></span> 
  
<span data-ttu-id="3b2d1-129">计算表达式 Width\*. 075 并返回结果。</span><span class="sxs-lookup"><span data-stu-id="3b2d1-129">Evaluates the expression Width\*.075 and returns the result.</span></span> 
  

