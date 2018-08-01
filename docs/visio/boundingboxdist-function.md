---
title: BOUNDINGBOXDIST 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8a2490f2-48c4-5df3-a3b3-40e8e0c80479
description: 返回形状边界框的指定部分的度量。
ms.openlocfilehash: 94cad37c4a0d2c6c7e7c69d997af09a9d7f1d651
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779802"
---
# <a name="boundingboxdist-function"></a><span data-ttu-id="e8461-103">BOUNDINGBOXDIST 函数</span><span class="sxs-lookup"><span data-stu-id="e8461-103">BOUNDINGBOXDIST Function</span></span>

<span data-ttu-id="e8461-104">返回形状边界框的指定部分的度量。</span><span class="sxs-lookup"><span data-stu-id="e8461-104">Returns the measurement of the specified part of the shape's bounding box.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="e8461-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="e8461-105">Version Information</span></span>

<span data-ttu-id="e8461-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="e8461-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e8461-107">语法</span><span class="sxs-lookup"><span data-stu-id="e8461-107">Syntax</span></span>

<span data-ttu-id="e8461-108">BOUNDINGBOXDIST (* **索引** *)</span><span class="sxs-lookup"><span data-stu-id="e8461-108">BOUNDINGBOXDIST(** *Index* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e8461-109">参数</span><span class="sxs-lookup"><span data-stu-id="e8461-109">Parameters</span></span>

|<span data-ttu-id="e8461-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="e8461-110">**Name**</span></span>|<span data-ttu-id="e8461-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e8461-111">**Required/Optional**</span></span>|<span data-ttu-id="e8461-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e8461-112">**Data Type**</span></span>|<span data-ttu-id="e8461-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="e8461-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e8461-114">_Index_</span><span class="sxs-lookup"><span data-stu-id="e8461-114">_Index_</span></span> <br/> |<span data-ttu-id="e8461-115">必需</span><span class="sxs-lookup"><span data-stu-id="e8461-115">Required</span></span>  <br/> |<span data-ttu-id="e8461-116">**编号**</span><span class="sxs-lookup"><span data-stu-id="e8461-116">**Number**</span></span> <br/> |<span data-ttu-id="e8461-117">形状的一部分的边界框以测量并返回。</span><span class="sxs-lookup"><span data-stu-id="e8461-117">The part of the shape's bounding box to measure and return.</span></span> <span data-ttu-id="e8461-118">有关可能值，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="e8461-118">See Remarks for possible values.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="e8461-119">返回值</span><span class="sxs-lookup"><span data-stu-id="e8461-119">Return value</span></span>

 <span data-ttu-id="e8461-120">**编号**</span><span class="sxs-lookup"><span data-stu-id="e8461-120">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e8461-121">说明</span><span class="sxs-lookup"><span data-stu-id="e8461-121">Remarks</span></span>

 <span data-ttu-id="e8461-122">*Index*可为以下值之一。</span><span class="sxs-lookup"><span data-stu-id="e8461-122">*Index*  can be one of the following values.</span></span> 
  
|<span data-ttu-id="e8461-123">**Item**</span><span class="sxs-lookup"><span data-stu-id="e8461-123">**Item**</span></span>|<span data-ttu-id="e8461-124">**值**</span><span class="sxs-lookup"><span data-stu-id="e8461-124">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8461-125">Width</span><span class="sxs-lookup"><span data-stu-id="e8461-125">Width</span></span>  <br/> |<span data-ttu-id="e8461-126">0</span><span class="sxs-lookup"><span data-stu-id="e8461-126">0</span></span>  <br/> |
|<span data-ttu-id="e8461-127">Height</span><span class="sxs-lookup"><span data-stu-id="e8461-127">Height</span></span>  <br/> |<span data-ttu-id="e8461-128">1</span><span class="sxs-lookup"><span data-stu-id="e8461-128">1</span></span>  <br/> |
|<span data-ttu-id="e8461-129">左边缘到形状的旋转中心点</span><span class="sxs-lookup"><span data-stu-id="e8461-129">Left edge to shape pin</span></span>  <br/> |<span data-ttu-id="e8461-130">2</span><span class="sxs-lookup"><span data-stu-id="e8461-130">2</span></span>  <br/> |
|<span data-ttu-id="e8461-131">形状的旋转中心点到右边缘</span><span class="sxs-lookup"><span data-stu-id="e8461-131">Shape pin to right edge</span></span>  <br/> |<span data-ttu-id="e8461-132">3</span><span class="sxs-lookup"><span data-stu-id="e8461-132">3</span></span>  <br/> |
|<span data-ttu-id="e8461-133">形状的旋转中心点到上边缘</span><span class="sxs-lookup"><span data-stu-id="e8461-133">Shape pin to top edge</span></span>  <br/> |<span data-ttu-id="e8461-134">4</span><span class="sxs-lookup"><span data-stu-id="e8461-134">4</span></span>  <br/> |
|<span data-ttu-id="e8461-135">下边缘到形状的旋转中心点</span><span class="sxs-lookup"><span data-stu-id="e8461-135">Bottom edge to shape pin</span></span>  <br/> |<span data-ttu-id="e8461-136">5</span><span class="sxs-lookup"><span data-stu-id="e8461-136">5</span></span>  <br/> |
|<span data-ttu-id="e8461-137">边界框的中心到 PinX</span><span class="sxs-lookup"><span data-stu-id="e8461-137">Center of bounding box to PinX</span></span>  <br/> |<span data-ttu-id="e8461-138">6</span><span class="sxs-lookup"><span data-stu-id="e8461-138">6</span></span>  <br/> |
|<span data-ttu-id="e8461-139">边界框的中心到 PinY</span><span class="sxs-lookup"><span data-stu-id="e8461-139">Center of bounding box to PinY</span></span>  <br/> |<span data-ttu-id="e8461-140">7</span><span class="sxs-lookup"><span data-stu-id="e8461-140">7</span></span>  <br/> |
   

