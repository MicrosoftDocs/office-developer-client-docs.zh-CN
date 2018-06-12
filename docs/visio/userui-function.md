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
description: 计算的状态的两个表达式根据值之一。
ms.openlocfilehash: 2cfdf23986a06dcc109106bd50a1a38e5af91313
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781615"
---
# <a name="userui-function"></a><span data-ttu-id="b214b-103">USERUI 函数</span><span class="sxs-lookup"><span data-stu-id="b214b-103">USERUI Function</span></span>

<span data-ttu-id="b214b-104">计算的_状态_的两个表达式根据值之一。</span><span class="sxs-lookup"><span data-stu-id="b214b-104">Evaluates one of the two expressions depending on the value of  _state_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="b214b-105">语法</span><span class="sxs-lookup"><span data-stu-id="b214b-105">Syntax</span></span>

<span data-ttu-id="b214b-106">USERUI (* **状态** *，* * *defaultexpression* * *，* * *userexpression* * *)</span><span class="sxs-lookup"><span data-stu-id="b214b-106">USERUI(** *state* **, ** *defaultexpression* **, ** *userexpression* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b214b-107">参数</span><span class="sxs-lookup"><span data-stu-id="b214b-107">Parameters</span></span>

|<span data-ttu-id="b214b-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b214b-108">**Name**</span></span>|<span data-ttu-id="b214b-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b214b-109">**Required/Optional**</span></span>|<span data-ttu-id="b214b-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b214b-110">**Data Type**</span></span>|<span data-ttu-id="b214b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b214b-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b214b-112">_state_</span><span class="sxs-lookup"><span data-stu-id="b214b-112">_state_</span></span> <br/> |<span data-ttu-id="b214b-113">必需</span><span class="sxs-lookup"><span data-stu-id="b214b-113">Required</span></span>  <br/> |<span data-ttu-id="b214b-114">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="b214b-114">**Boolean**</span></span> <br/> |<span data-ttu-id="b214b-115">确定要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="b214b-115">Determines which expression to evaluate.</span></span>  <br/> |
| <span data-ttu-id="b214b-116">_defaultexpression_</span><span class="sxs-lookup"><span data-stu-id="b214b-116">_defaultexpression_</span></span> <br/> |<span data-ttu-id="b214b-117">必需</span><span class="sxs-lookup"><span data-stu-id="b214b-117">Required</span></span>  <br/> |<span data-ttu-id="b214b-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="b214b-118">**String**</span></span> <br/> |<span data-ttu-id="b214b-119">默认表达式。</span><span class="sxs-lookup"><span data-stu-id="b214b-119">The default expression.</span></span>  <br/> |
| <span data-ttu-id="b214b-120">_userexpression_</span><span class="sxs-lookup"><span data-stu-id="b214b-120">_userexpression_</span></span> <br/> |<span data-ttu-id="b214b-121">必需</span><span class="sxs-lookup"><span data-stu-id="b214b-121">Required</span></span>  <br/> |<span data-ttu-id="b214b-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="b214b-122">**String**</span></span> <br/> |<span data-ttu-id="b214b-123">为用户提供一个表达式。</span><span class="sxs-lookup"><span data-stu-id="b214b-123">An expression supplied by the user.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b214b-124">备注</span><span class="sxs-lookup"><span data-stu-id="b214b-124">Remarks</span></span>

<span data-ttu-id="b214b-125">如果_状态_为 0，则 USERUI 函数计算_defaultexpression_。</span><span class="sxs-lookup"><span data-stu-id="b214b-125">If  _state_ is 0, the USERUI function evaluates the  _defaultexpression_.</span></span> <span data-ttu-id="b214b-126">如果_状态_为 1，则其值_userexpression_。</span><span class="sxs-lookup"><span data-stu-id="b214b-126">If  _state_ is 1, it evaluates the  _userexpression_.</span></span>
  
## <a name="example"></a><span data-ttu-id="b214b-127">示例</span><span class="sxs-lookup"><span data-stu-id="b214b-127">Example</span></span>

<span data-ttu-id="b214b-128">USERUI (1，如果 (宽度\>6 中、 6 英寸，宽度)，宽度\*0.75)</span><span class="sxs-lookup"><span data-stu-id="b214b-128">USERUI(1, if(Width\>6in, 6in, Width), Width\*0.75)</span></span> 
  
<span data-ttu-id="b214b-129">计算表达式 Width\*.075，并返回结果。</span><span class="sxs-lookup"><span data-stu-id="b214b-129">Evaluates the expression Width\*.075 and returns the result.</span></span> 
  

