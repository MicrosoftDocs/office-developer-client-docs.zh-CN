---
title: BOUNDINGBOXRECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1f66d2b2-ec9e-cd58-7642-96850fe4589e
description: 返回形状的边界框指定边缘的坐标。
ms.openlocfilehash: 2c850cb213ec0093ead53cd860f92e38da46f27e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779797"
---
# <a name="boundingboxrect-function"></a><span data-ttu-id="11c8d-103">BOUNDINGBOXRECT 函数</span><span class="sxs-lookup"><span data-stu-id="11c8d-103">BOUNDINGBOXRECT Function</span></span>

<span data-ttu-id="11c8d-104">返回形状的边界框指定边缘的坐标。</span><span class="sxs-lookup"><span data-stu-id="11c8d-104">Returns the coordinate of the specified edge of the shape's bounding box.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="11c8d-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="11c8d-105">Version Information</span></span>

<span data-ttu-id="11c8d-106">添加的版本： Visio 2010</span><span class="sxs-lookup"><span data-stu-id="11c8d-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="11c8d-107">语法</span><span class="sxs-lookup"><span data-stu-id="11c8d-107">Syntax</span></span>

<span data-ttu-id="11c8d-108">BOUNDINGBOXRECT (* **索引** *)</span><span class="sxs-lookup"><span data-stu-id="11c8d-108">BOUNDINGBOXRECT(** *Index* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="11c8d-109">参数</span><span class="sxs-lookup"><span data-stu-id="11c8d-109">Parameters</span></span>

|<span data-ttu-id="11c8d-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="11c8d-110">**Name**</span></span>|<span data-ttu-id="11c8d-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="11c8d-111">**Required/Optional**</span></span>|<span data-ttu-id="11c8d-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="11c8d-112">**Data Type**</span></span>|<span data-ttu-id="11c8d-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="11c8d-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="11c8d-114">_Index_</span><span class="sxs-lookup"><span data-stu-id="11c8d-114">_Index_</span></span> <br/> |<span data-ttu-id="11c8d-115">必需</span><span class="sxs-lookup"><span data-stu-id="11c8d-115">Required</span></span>  <br/> |<span data-ttu-id="11c8d-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="11c8d-116">**Integer**</span></span> <br/> |<span data-ttu-id="11c8d-p101">要获取坐标的形状的边界框边缘。请参阅“注解”以了解可能的值。</span><span class="sxs-lookup"><span data-stu-id="11c8d-p101">The edge of the shape's bounding box for which to get the coordinate. See Remarks for possible values.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="11c8d-119">返回值</span><span class="sxs-lookup"><span data-stu-id="11c8d-119">Return value</span></span>

 <span data-ttu-id="11c8d-120">**编号**</span><span class="sxs-lookup"><span data-stu-id="11c8d-120">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="11c8d-121">备注</span><span class="sxs-lookup"><span data-stu-id="11c8d-121">Remarks</span></span>

 <span data-ttu-id="11c8d-122">*Index*可为以下值之一。</span><span class="sxs-lookup"><span data-stu-id="11c8d-122">*Index*  can be one of the following values.</span></span> 
  
|<span data-ttu-id="11c8d-123">**Item**</span><span class="sxs-lookup"><span data-stu-id="11c8d-123">**Item**</span></span>|<span data-ttu-id="11c8d-124">**值**</span><span class="sxs-lookup"><span data-stu-id="11c8d-124">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11c8d-125">左边缘</span><span class="sxs-lookup"><span data-stu-id="11c8d-125">Left edge</span></span>  <br/> |<span data-ttu-id="11c8d-126">0</span><span class="sxs-lookup"><span data-stu-id="11c8d-126">0</span></span>  <br/> |
|<span data-ttu-id="11c8d-127">右边缘</span><span class="sxs-lookup"><span data-stu-id="11c8d-127">Right edge</span></span>  <br/> |<span data-ttu-id="11c8d-128">1</span><span class="sxs-lookup"><span data-stu-id="11c8d-128">1</span></span>  <br/> |
|<span data-ttu-id="11c8d-129">上边缘</span><span class="sxs-lookup"><span data-stu-id="11c8d-129">Top edge</span></span>  <br/> |<span data-ttu-id="11c8d-130">2</span><span class="sxs-lookup"><span data-stu-id="11c8d-130">2</span></span>  <br/> |
|<span data-ttu-id="11c8d-131">下边缘</span><span class="sxs-lookup"><span data-stu-id="11c8d-131">Bottom edge</span></span>  <br/> |<span data-ttu-id="11c8d-132">3</span><span class="sxs-lookup"><span data-stu-id="11c8d-132">3</span></span>  <br/> |
   
<span data-ttu-id="11c8d-133">如果该形状具有父项，返回值位于该父坐标系统。</span><span class="sxs-lookup"><span data-stu-id="11c8d-133">If the shape has a parent, the return value is in the coordinate system of that parent.</span></span>
  

