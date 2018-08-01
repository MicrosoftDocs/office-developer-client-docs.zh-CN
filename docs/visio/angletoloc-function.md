---
title: ANGLETOLOC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253217
localization_priority: Normal
ms.assetid: ee5e3898-bb49-57c6-0ebe-12e1fe388e55
description: 使用目标形状的本地坐标系返回一个转换过的角度。它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。
ms.openlocfilehash: 09ab0a4a55446dd74729f1da0bcf022d8376909b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779646"
---
# <a name="angletoloc-function"></a><span data-ttu-id="f5ff5-104">ANGLETOLOC 函数</span><span class="sxs-lookup"><span data-stu-id="f5ff5-104">ANGLETOLOC Function</span></span>

<span data-ttu-id="f5ff5-p102">使用目标形状的本地坐标系返回一个转换过的角度。它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。
    
</span><span class="sxs-lookup"><span data-stu-id="f5ff5-p102">Returns a transformed angle in the destination shape's local coordinate system. Converts an angle from local coordinates in a source shape to the local coordinates in a destination shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f5ff5-107">语法</span><span class="sxs-lookup"><span data-stu-id="f5ff5-107">Syntax</span></span>

<span data-ttu-id="f5ff5-108">ANGLETOLOC (* * *srcAngle* * *，* * *srcRef* * *，* * *dstRef* * *)</span><span class="sxs-lookup"><span data-stu-id="f5ff5-108">ANGLETOLOC(** *srcAngle* **, ** *srcRef* **, ** *dstRef* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f5ff5-109">参数</span><span class="sxs-lookup"><span data-stu-id="f5ff5-109">Parameters</span></span>

|<span data-ttu-id="f5ff5-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-110">**Name**</span></span>|<span data-ttu-id="f5ff5-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-111">**Required/Optional**</span></span>|<span data-ttu-id="f5ff5-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-112">**Data Type**</span></span>|<span data-ttu-id="f5ff5-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f5ff5-114">_srcAngle_</span><span class="sxs-lookup"><span data-stu-id="f5ff5-114">_srcAngle_</span></span> <br/> |<span data-ttu-id="f5ff5-115">必需</span><span class="sxs-lookup"><span data-stu-id="f5ff5-115">Required</span></span>  <br/> |<span data-ttu-id="f5ff5-116">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-116">**Numeric**</span></span> <br/> |<span data-ttu-id="f5ff5-117">源坐标系中的角度。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-117">An angle in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="f5ff5-118">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="f5ff5-118">_srcRef_</span></span> <br/> |<span data-ttu-id="f5ff5-119">必需</span><span class="sxs-lookup"><span data-stu-id="f5ff5-119">Required</span></span>  <br/> |<span data-ttu-id="f5ff5-120">**字符串**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-120">**String**</span></span> <br/> | <span data-ttu-id="f5ff5-121">对源对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-121">A reference to a cell in the source object, such as a shape, group, page, and so on.</span></span>  <br/> |
| <span data-ttu-id="f5ff5-122">_dstRef_</span><span class="sxs-lookup"><span data-stu-id="f5ff5-122">_dstRef_</span></span> <br/> |<span data-ttu-id="f5ff5-123">必需</span><span class="sxs-lookup"><span data-stu-id="f5ff5-123">Required</span></span>  <br/> |<span data-ttu-id="f5ff5-124">**字符串**</span><span class="sxs-lookup"><span data-stu-id="f5ff5-124">**String**</span></span> <br/> |<span data-ttu-id="f5ff5-125">对目标对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-125">A reference to a cell in the destination object, such as a shape, group, page, and so on.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f5ff5-126">注解</span><span class="sxs-lookup"><span data-stu-id="f5ff5-126">Remarks</span></span>

<span data-ttu-id="f5ff5-127">可以使用 ANGLETOLOC 函数来按照另一个坐标空间中的角度设置形状中的本地角度单元格。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-127">You can use the ANGLETOLOC function to set local angle cells in a shape in terms of an angle from another coordinate space.</span></span>
  
<span data-ttu-id="f5ff5-p103">即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-p103">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span>
  
<span data-ttu-id="f5ff5-130">源坐标和目标坐标必须位于同一页上。</span><span class="sxs-lookup"><span data-stu-id="f5ff5-130">The source and destination coordinates must be on the same page.</span></span>
  

