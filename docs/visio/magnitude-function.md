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
description: 返回一个向量的大小, 该向量的升为, 其运行为 B, 乘以各自的常量 constantA 和 constantB。
ms.openlocfilehash: 6393c7827e2553ca4948c8b9c51075ca8e4783bd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420456"
---
# <a name="magnitude-function"></a><span data-ttu-id="df5f1-103">MAGNITUDE 函数</span><span class="sxs-lookup"><span data-stu-id="df5f1-103">MAGNITUDE Function</span></span>

<span data-ttu-id="df5f1-104">返回_一个_向量的大小, 该向量的升为, 其运行为_B_, 乘以各自的常量_constantA_和_constantB_。</span><span class="sxs-lookup"><span data-stu-id="df5f1-104">Returns the magnitude of the vector whose rise is  _A_ and whose run is  _B_, multiplied by the respective constants  _constantA_ and  _constantB_.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="df5f1-105">语法</span><span class="sxs-lookup"><span data-stu-id="df5f1-105">Syntax</span></span>

<span data-ttu-id="df5f1-106">数量级 (\* \* *constantA* \* \*, \* \* *A* \* \*, \* \* *constantB* \* \*, \* \* *B* \* \*)</span><span class="sxs-lookup"><span data-stu-id="df5f1-106">MAGNITUDE(\*\* *constantA* \*\*, \*\* *A* \*\*, \*\* *constantB* \*\*, \*\* *B* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="df5f1-107">参数</span><span class="sxs-lookup"><span data-stu-id="df5f1-107">Parameters</span></span>

|<span data-ttu-id="df5f1-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="df5f1-108">**Name**</span></span>|<span data-ttu-id="df5f1-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="df5f1-109">**Required/Optional**</span></span>|<span data-ttu-id="df5f1-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="df5f1-110">**Data Type**</span></span>|<span data-ttu-id="df5f1-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="df5f1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="df5f1-112">_constantA_</span><span class="sxs-lookup"><span data-stu-id="df5f1-112">_constantA_</span></span> <br/> |<span data-ttu-id="df5f1-113">必需</span><span class="sxs-lookup"><span data-stu-id="df5f1-113">Required</span></span>  <br/> |<span data-ttu-id="df5f1-114">**Number**</span><span class="sxs-lookup"><span data-stu-id="df5f1-114">**Number**</span></span> <br/> |<span data-ttu-id="df5f1-115">矢高要乘以的常量。</span><span class="sxs-lookup"><span data-stu-id="df5f1-115">The constant by which to multiply the rise.</span></span>  <br/> |
| <span data-ttu-id="df5f1-116">_A_</span><span class="sxs-lookup"><span data-stu-id="df5f1-116">_A_</span></span> <br/> |<span data-ttu-id="df5f1-117">必需</span><span class="sxs-lookup"><span data-stu-id="df5f1-117">Required</span></span>  <br/> |<span data-ttu-id="df5f1-118">**Number**</span><span class="sxs-lookup"><span data-stu-id="df5f1-118">**Number**</span></span> <br/> |<span data-ttu-id="df5f1-119">矢高。</span><span class="sxs-lookup"><span data-stu-id="df5f1-119">The rise.</span></span>  <br/> |
| <span data-ttu-id="df5f1-120">_constantB_</span><span class="sxs-lookup"><span data-stu-id="df5f1-120">_constantB_</span></span> <br/> |<span data-ttu-id="df5f1-121">必需</span><span class="sxs-lookup"><span data-stu-id="df5f1-121">Required</span></span>  <br/> |<span data-ttu-id="df5f1-122">**Number**</span><span class="sxs-lookup"><span data-stu-id="df5f1-122">**Number**</span></span> <br/> |<span data-ttu-id="df5f1-123">游程要乘以的常量。</span><span class="sxs-lookup"><span data-stu-id="df5f1-123">The constant by which to multiply the run.</span></span>  <br/> |
| <span data-ttu-id="df5f1-124">_黑白_</span><span class="sxs-lookup"><span data-stu-id="df5f1-124">_B_</span></span> <br/> |<span data-ttu-id="df5f1-125">必需</span><span class="sxs-lookup"><span data-stu-id="df5f1-125">Required</span></span>  <br/> |<span data-ttu-id="df5f1-126">**Number**</span><span class="sxs-lookup"><span data-stu-id="df5f1-126">**Number**</span></span> <br/> |<span data-ttu-id="df5f1-127">游程。</span><span class="sxs-lookup"><span data-stu-id="df5f1-127">The run.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="df5f1-128">说明</span><span class="sxs-lookup"><span data-stu-id="df5f1-128">Remarks</span></span>

<span data-ttu-id="df5f1-129">MAGNITUDE 按照以下公式计算：</span><span class="sxs-lookup"><span data-stu-id="df5f1-129">MAGNITUDE is calculated according to the following formula:</span></span>
  
<span data-ttu-id="df5f1-130">SQRT ((constantA \* A) ^ 2 + (constantB \* B) ^ 2)</span><span class="sxs-lookup"><span data-stu-id="df5f1-130">SQRT((constantA \* A)^2 + (constantB \* B)^2)</span></span>
  
## <a name="example"></a><span data-ttu-id="df5f1-131">示例</span><span class="sxs-lookup"><span data-stu-id="df5f1-131">Example</span></span>

<span data-ttu-id="df5f1-132">MAGNITUDE(1, 3, 1, 4)</span><span class="sxs-lookup"><span data-stu-id="df5f1-132">MAGNITUDE(1, 3, 1, 4)</span></span> 
  
<span data-ttu-id="df5f1-133">返回 5。</span><span class="sxs-lookup"><span data-stu-id="df5f1-133">Returns 5.</span></span> 
  

