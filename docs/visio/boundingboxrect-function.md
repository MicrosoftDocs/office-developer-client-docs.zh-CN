---
title: BOUNDINGBOXRECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1f66d2b2-ec9e-cd58-7642-96850fe4589e
description: 返回形状的边界框指定边缘的坐标。
ms.openlocfilehash: 0018118eb0991fe9dc1da0eb000566b69d8a4b4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418069"
---
# <a name="boundingboxrect-function"></a><span data-ttu-id="b8c5b-103">BOUNDINGBOXRECT 函数</span><span class="sxs-lookup"><span data-stu-id="b8c5b-103">BOUNDINGBOXRECT Function</span></span>

<span data-ttu-id="b8c5b-104">返回形状的边界框指定边缘的坐标。</span><span class="sxs-lookup"><span data-stu-id="b8c5b-104">Returns the coordinate of the specified edge of the shape's bounding box.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="b8c5b-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="b8c5b-105">Version Information</span></span>

<span data-ttu-id="b8c5b-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="b8c5b-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b8c5b-107">语法</span><span class="sxs-lookup"><span data-stu-id="b8c5b-107">Syntax</span></span>

<span data-ttu-id="b8c5b-108">BOUNDINGBOXRECT (\*\* *Index* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="b8c5b-108">BOUNDINGBOXRECT(\*\* *Index* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b8c5b-109">参数</span><span class="sxs-lookup"><span data-stu-id="b8c5b-109">Parameters</span></span>

|<span data-ttu-id="b8c5b-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-110">**Name**</span></span>|<span data-ttu-id="b8c5b-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-111">**Required/Optional**</span></span>|<span data-ttu-id="b8c5b-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-112">**Data Type**</span></span>|<span data-ttu-id="b8c5b-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b8c5b-114">_Index_</span><span class="sxs-lookup"><span data-stu-id="b8c5b-114">_Index_</span></span> <br/> |<span data-ttu-id="b8c5b-115">必需</span><span class="sxs-lookup"><span data-stu-id="b8c5b-115">Required</span></span>  <br/> |<span data-ttu-id="b8c5b-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-116">**Integer**</span></span> <br/> |<span data-ttu-id="b8c5b-p101">要获取坐标的形状的边界框边缘。请参阅“注解”以了解可能的值。</span><span class="sxs-lookup"><span data-stu-id="b8c5b-p101">The edge of the shape's bounding box for which to get the coordinate. See Remarks for possible values.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b8c5b-119">返回值</span><span class="sxs-lookup"><span data-stu-id="b8c5b-119">Return value</span></span>

 <span data-ttu-id="b8c5b-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-120">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b8c5b-121">备注</span><span class="sxs-lookup"><span data-stu-id="b8c5b-121">Remarks</span></span>

 <span data-ttu-id="b8c5b-122">*Index*  可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="b8c5b-122">*Index*  can be one of the following values.</span></span> 
  
|<span data-ttu-id="b8c5b-123">**项目**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-123">**Item**</span></span>|<span data-ttu-id="b8c5b-124">**值**</span><span class="sxs-lookup"><span data-stu-id="b8c5b-124">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8c5b-125">左边缘</span><span class="sxs-lookup"><span data-stu-id="b8c5b-125">Left edge</span></span>  <br/> |<span data-ttu-id="b8c5b-126">0</span><span class="sxs-lookup"><span data-stu-id="b8c5b-126">0</span></span>  <br/> |
|<span data-ttu-id="b8c5b-127">右边缘</span><span class="sxs-lookup"><span data-stu-id="b8c5b-127">Right edge</span></span>  <br/> |<span data-ttu-id="b8c5b-128">1</span><span class="sxs-lookup"><span data-stu-id="b8c5b-128">1</span></span>  <br/> |
|<span data-ttu-id="b8c5b-129">上边缘</span><span class="sxs-lookup"><span data-stu-id="b8c5b-129">Top edge</span></span>  <br/> |<span data-ttu-id="b8c5b-130">2</span><span class="sxs-lookup"><span data-stu-id="b8c5b-130">2</span></span>  <br/> |
|<span data-ttu-id="b8c5b-131">下边缘</span><span class="sxs-lookup"><span data-stu-id="b8c5b-131">Bottom edge</span></span>  <br/> |<span data-ttu-id="b8c5b-132">3</span><span class="sxs-lookup"><span data-stu-id="b8c5b-132">3</span></span>  <br/> |
   
<span data-ttu-id="b8c5b-133">如果形状有父形状，则返回值位于该父形状的坐标系中。</span><span class="sxs-lookup"><span data-stu-id="b8c5b-133">If the shape has a parent, the return value is in the coordinate system of that parent.</span></span>
  

