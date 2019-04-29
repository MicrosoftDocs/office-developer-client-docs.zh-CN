---
title: BOUNDINGBOXDIST 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8a2490f2-48c4-5df3-a3b3-40e8e0c80479
description: 返回形状边界框的指定部分的度量。
ms.openlocfilehash: a62d5b82c310e7b99e16b70982b75a68172b7fd8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428275"
---
# <a name="boundingboxdist-function"></a><span data-ttu-id="5cdf2-103">BOUNDINGBOXDIST 函数</span><span class="sxs-lookup"><span data-stu-id="5cdf2-103">BOUNDINGBOXDIST Function</span></span>

<span data-ttu-id="5cdf2-104">返回形状边界框的指定部分的度量。</span><span class="sxs-lookup"><span data-stu-id="5cdf2-104">Returns the measurement of the specified part of the shape's bounding box.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="5cdf2-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="5cdf2-105">Version Information</span></span>

<span data-ttu-id="5cdf2-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="5cdf2-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5cdf2-107">语法</span><span class="sxs-lookup"><span data-stu-id="5cdf2-107">Syntax</span></span>

<span data-ttu-id="5cdf2-108">BOUNDINGBOXDIST (\* **索引** \*)</span><span class="sxs-lookup"><span data-stu-id="5cdf2-108">BOUNDINGBOXDIST(\*\* *Index* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5cdf2-109">参数</span><span class="sxs-lookup"><span data-stu-id="5cdf2-109">Parameters</span></span>

|<span data-ttu-id="5cdf2-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-110">**Name**</span></span>|<span data-ttu-id="5cdf2-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-111">**Required/Optional**</span></span>|<span data-ttu-id="5cdf2-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-112">**Data Type**</span></span>|<span data-ttu-id="5cdf2-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5cdf2-114">_Index_</span><span class="sxs-lookup"><span data-stu-id="5cdf2-114">_Index_</span></span> <br/> |<span data-ttu-id="5cdf2-115">必需</span><span class="sxs-lookup"><span data-stu-id="5cdf2-115">Required</span></span>  <br/> |<span data-ttu-id="5cdf2-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-116">**Number**</span></span> <br/> |<span data-ttu-id="5cdf2-117">要测量和返回的形状边界框的一部分。</span><span class="sxs-lookup"><span data-stu-id="5cdf2-117">The part of the shape's bounding box to measure and return.</span></span> <span data-ttu-id="5cdf2-118">有关可能值，请参见备注。</span><span class="sxs-lookup"><span data-stu-id="5cdf2-118">See Remarks for possible values.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="5cdf2-119">返回值</span><span class="sxs-lookup"><span data-stu-id="5cdf2-119">Return value</span></span>

 <span data-ttu-id="5cdf2-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-120">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5cdf2-121">说明</span><span class="sxs-lookup"><span data-stu-id="5cdf2-121">Remarks</span></span>

 <span data-ttu-id="5cdf2-122">*索引*可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="5cdf2-122">*Index*  can be one of the following values.</span></span> 
  
|<span data-ttu-id="5cdf2-123">**项**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-123">**Item**</span></span>|<span data-ttu-id="5cdf2-124">**值**</span><span class="sxs-lookup"><span data-stu-id="5cdf2-124">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5cdf2-125">Width</span><span class="sxs-lookup"><span data-stu-id="5cdf2-125">Width</span></span>  <br/> |<span data-ttu-id="5cdf2-126">0</span><span class="sxs-lookup"><span data-stu-id="5cdf2-126">0</span></span>  <br/> |
|<span data-ttu-id="5cdf2-127">Height</span><span class="sxs-lookup"><span data-stu-id="5cdf2-127">Height</span></span>  <br/> |<span data-ttu-id="5cdf2-128">1</span><span class="sxs-lookup"><span data-stu-id="5cdf2-128">1</span></span>  <br/> |
|<span data-ttu-id="5cdf2-129">左边缘到形状的旋转中心点</span><span class="sxs-lookup"><span data-stu-id="5cdf2-129">Left edge to shape pin</span></span>  <br/> |<span data-ttu-id="5cdf2-130">双面</span><span class="sxs-lookup"><span data-stu-id="5cdf2-130">2</span></span>  <br/> |
|<span data-ttu-id="5cdf2-131">形状的旋转中心点到右边缘</span><span class="sxs-lookup"><span data-stu-id="5cdf2-131">Shape pin to right edge</span></span>  <br/> |<span data-ttu-id="5cdf2-132">第三章</span><span class="sxs-lookup"><span data-stu-id="5cdf2-132">3</span></span>  <br/> |
|<span data-ttu-id="5cdf2-133">形状的旋转中心点到上边缘</span><span class="sxs-lookup"><span data-stu-id="5cdf2-133">Shape pin to top edge</span></span>  <br/> |<span data-ttu-id="5cdf2-134">4</span><span class="sxs-lookup"><span data-stu-id="5cdf2-134">4</span></span>  <br/> |
|<span data-ttu-id="5cdf2-135">下边缘到形状的旋转中心点</span><span class="sxs-lookup"><span data-stu-id="5cdf2-135">Bottom edge to shape pin</span></span>  <br/> |<span data-ttu-id="5cdf2-136">5</span><span class="sxs-lookup"><span data-stu-id="5cdf2-136">5</span></span>  <br/> |
|<span data-ttu-id="5cdf2-137">边界框的中心到 PinX</span><span class="sxs-lookup"><span data-stu-id="5cdf2-137">Center of bounding box to PinX</span></span>  <br/> |<span data-ttu-id="5cdf2-138">型</span><span class="sxs-lookup"><span data-stu-id="5cdf2-138">6</span></span>  <br/> |
|<span data-ttu-id="5cdf2-139">边界框的中心到 PinY</span><span class="sxs-lookup"><span data-stu-id="5cdf2-139">Center of bounding box to PinY</span></span>  <br/> |<span data-ttu-id="5cdf2-140">步</span><span class="sxs-lookup"><span data-stu-id="5cdf2-140">7</span></span>  <br/> |
   

