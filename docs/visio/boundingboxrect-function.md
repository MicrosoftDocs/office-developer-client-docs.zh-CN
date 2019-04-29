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
# <a name="boundingboxrect-function"></a><span data-ttu-id="1f159-103">BOUNDINGBOXRECT 函数</span><span class="sxs-lookup"><span data-stu-id="1f159-103">BOUNDINGBOXRECT Function</span></span>

<span data-ttu-id="1f159-104">返回形状的边界框指定边缘的坐标。</span><span class="sxs-lookup"><span data-stu-id="1f159-104">Returns the coordinate of the specified edge of the shape's bounding box.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="1f159-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="1f159-105">Version Information</span></span>

<span data-ttu-id="1f159-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="1f159-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1f159-107">语法</span><span class="sxs-lookup"><span data-stu-id="1f159-107">Syntax</span></span>

<span data-ttu-id="1f159-108">BOUNDINGBOXRECT (\* **索引** \*)</span><span class="sxs-lookup"><span data-stu-id="1f159-108">BOUNDINGBOXRECT(\*\* *Index* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1f159-109">参数</span><span class="sxs-lookup"><span data-stu-id="1f159-109">Parameters</span></span>

|<span data-ttu-id="1f159-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1f159-110">**Name**</span></span>|<span data-ttu-id="1f159-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1f159-111">**Required/Optional**</span></span>|<span data-ttu-id="1f159-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1f159-112">**Data Type**</span></span>|<span data-ttu-id="1f159-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f159-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1f159-114">_Index_</span><span class="sxs-lookup"><span data-stu-id="1f159-114">_Index_</span></span> <br/> |<span data-ttu-id="1f159-115">必需</span><span class="sxs-lookup"><span data-stu-id="1f159-115">Required</span></span>  <br/> |<span data-ttu-id="1f159-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="1f159-116">**Integer**</span></span> <br/> |<span data-ttu-id="1f159-117">要获取坐标的形状的边界框边缘。</span><span class="sxs-lookup"><span data-stu-id="1f159-117">The edge of the shape's bounding box for which to get the coordinate.</span></span> <span data-ttu-id="1f159-118">请参阅“注解”以了解可能的值。</span><span class="sxs-lookup"><span data-stu-id="1f159-118">See Remarks for possible values.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1f159-119">返回值</span><span class="sxs-lookup"><span data-stu-id="1f159-119">Return value</span></span>

 <span data-ttu-id="1f159-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="1f159-120">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1f159-121">说明</span><span class="sxs-lookup"><span data-stu-id="1f159-121">Remarks</span></span>

 <span data-ttu-id="1f159-122">*索引*可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="1f159-122">*Index*  can be one of the following values.</span></span> 
  
|<span data-ttu-id="1f159-123">**项**</span><span class="sxs-lookup"><span data-stu-id="1f159-123">**Item**</span></span>|<span data-ttu-id="1f159-124">**值**</span><span class="sxs-lookup"><span data-stu-id="1f159-124">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f159-125">左边缘</span><span class="sxs-lookup"><span data-stu-id="1f159-125">Left edge</span></span>  <br/> |<span data-ttu-id="1f159-126">0</span><span class="sxs-lookup"><span data-stu-id="1f159-126">0</span></span>  <br/> |
|<span data-ttu-id="1f159-127">右边缘</span><span class="sxs-lookup"><span data-stu-id="1f159-127">Right edge</span></span>  <br/> |<span data-ttu-id="1f159-128">1</span><span class="sxs-lookup"><span data-stu-id="1f159-128">1</span></span>  <br/> |
|<span data-ttu-id="1f159-129">上边缘</span><span class="sxs-lookup"><span data-stu-id="1f159-129">Top edge</span></span>  <br/> |<span data-ttu-id="1f159-130">双面</span><span class="sxs-lookup"><span data-stu-id="1f159-130">2</span></span>  <br/> |
|<span data-ttu-id="1f159-131">下边缘</span><span class="sxs-lookup"><span data-stu-id="1f159-131">Bottom edge</span></span>  <br/> |<span data-ttu-id="1f159-132">第三章</span><span class="sxs-lookup"><span data-stu-id="1f159-132">3</span></span>  <br/> |
   
<span data-ttu-id="1f159-133">如果形状具有父级, 则返回值位于父项的坐标系统中。</span><span class="sxs-lookup"><span data-stu-id="1f159-133">If the shape has a parent, the return value is in the coordinate system of that parent.</span></span>
  

