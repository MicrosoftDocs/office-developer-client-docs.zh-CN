---
title: MAGNITUDE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251461
localization_priority: Normal
ms.assetid: 9f443687-9861-5f51-94c4-f056805f736b
description: 将返回向量程度其矢高是 A 和 B，乘以各自其运行常量 constantA 和 constantB。
ms.openlocfilehash: f4c428b8b381af58958dab66a71ddd0bcaf715c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780681"
---
# <a name="magnitude-function"></a><span data-ttu-id="d37ad-103">MAGNITUDE 函数</span><span class="sxs-lookup"><span data-stu-id="d37ad-103">MAGNITUDE Function</span></span>

<span data-ttu-id="d37ad-104">将返回向量程度其矢高是_A_和_B_，乘以各自常量其运行_constantA_和_constantB_。</span><span class="sxs-lookup"><span data-stu-id="d37ad-104">Returns the magnitude of the vector whose rise is  _A_ and whose run is  _B_, multiplied by the respective constants  _constantA_ and  _constantB_.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d37ad-105">语法</span><span class="sxs-lookup"><span data-stu-id="d37ad-105">Syntax</span></span>

<span data-ttu-id="d37ad-106">MAGNITUDE (* * *constantA* * *，* * *A* * *，* * *constantB* * *，* * *B* * *)</span><span class="sxs-lookup"><span data-stu-id="d37ad-106">MAGNITUDE(** *constantA* **, ** *A* **, ** *constantB* **, ** *B* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d37ad-107">参数</span><span class="sxs-lookup"><span data-stu-id="d37ad-107">Parameters</span></span>

|<span data-ttu-id="d37ad-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d37ad-108">**Name**</span></span>|<span data-ttu-id="d37ad-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d37ad-109">**Required/Optional**</span></span>|<span data-ttu-id="d37ad-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d37ad-110">**Data Type**</span></span>|<span data-ttu-id="d37ad-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d37ad-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d37ad-112">_constantA_</span><span class="sxs-lookup"><span data-stu-id="d37ad-112">_constantA_</span></span> <br/> |<span data-ttu-id="d37ad-113">必需</span><span class="sxs-lookup"><span data-stu-id="d37ad-113">Required</span></span>  <br/> |<span data-ttu-id="d37ad-114">**编号**</span><span class="sxs-lookup"><span data-stu-id="d37ad-114">**Number**</span></span> <br/> |<span data-ttu-id="d37ad-115">矢高要乘以的常量。</span><span class="sxs-lookup"><span data-stu-id="d37ad-115">The constant by which to multiply the rise.</span></span>  <br/> |
| <span data-ttu-id="d37ad-116">_A_</span><span class="sxs-lookup"><span data-stu-id="d37ad-116">_A_</span></span> <br/> |<span data-ttu-id="d37ad-117">必需</span><span class="sxs-lookup"><span data-stu-id="d37ad-117">Required</span></span>  <br/> |<span data-ttu-id="d37ad-118">**编号**</span><span class="sxs-lookup"><span data-stu-id="d37ad-118">**Number**</span></span> <br/> |<span data-ttu-id="d37ad-119">矢高。</span><span class="sxs-lookup"><span data-stu-id="d37ad-119">The rise.</span></span>  <br/> |
| <span data-ttu-id="d37ad-120">_constantB_</span><span class="sxs-lookup"><span data-stu-id="d37ad-120">_constantB_</span></span> <br/> |<span data-ttu-id="d37ad-121">必需</span><span class="sxs-lookup"><span data-stu-id="d37ad-121">Required</span></span>  <br/> |<span data-ttu-id="d37ad-122">**编号**</span><span class="sxs-lookup"><span data-stu-id="d37ad-122">**Number**</span></span> <br/> |<span data-ttu-id="d37ad-123">游程要乘以的常量。</span><span class="sxs-lookup"><span data-stu-id="d37ad-123">The constant by which to multiply the run.</span></span>  <br/> |
| <span data-ttu-id="d37ad-124">_B_</span><span class="sxs-lookup"><span data-stu-id="d37ad-124">_B_</span></span> <br/> |<span data-ttu-id="d37ad-125">必需</span><span class="sxs-lookup"><span data-stu-id="d37ad-125">Required</span></span>  <br/> |<span data-ttu-id="d37ad-126">**编号**</span><span class="sxs-lookup"><span data-stu-id="d37ad-126">**Number**</span></span> <br/> |<span data-ttu-id="d37ad-127">游程。</span><span class="sxs-lookup"><span data-stu-id="d37ad-127">The run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d37ad-128">注解</span><span class="sxs-lookup"><span data-stu-id="d37ad-128">Remarks</span></span>

<span data-ttu-id="d37ad-129">MAGNITUDE 按照以下公式计算：</span><span class="sxs-lookup"><span data-stu-id="d37ad-129">MAGNITUDE is calculated according to the following formula:</span></span>
  
<span data-ttu-id="d37ad-130">SQRT ((constantA \* A) ^2 + (constantB \* B) ^2)</span><span class="sxs-lookup"><span data-stu-id="d37ad-130">SQRT((constantA \* A)^2 + (constantB \* B)^2)</span></span>
  
## <a name="example"></a><span data-ttu-id="d37ad-131">示例</span><span class="sxs-lookup"><span data-stu-id="d37ad-131">Example</span></span>

<span data-ttu-id="d37ad-132">MAGNITUDE(1, 3, 1, 4)</span><span class="sxs-lookup"><span data-stu-id="d37ad-132">MAGNITUDE(1, 3, 1, 4)</span></span> 
  
<span data-ttu-id="d37ad-133">返回 5。</span><span class="sxs-lookup"><span data-stu-id="d37ad-133">Returns 5.</span></span> 
  

