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
description: 使用目标形状的本地坐标系返回一个转换过的角度。 它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。
ms.openlocfilehash: e971613d4fc33cd991e7e9aeba49ac47871ebe8f
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160263"
---
# <a name="angletoloc-function"></a><span data-ttu-id="c67f8-104">ANGLETOLOC 函数</span><span class="sxs-lookup"><span data-stu-id="c67f8-104">ANGLETOLOC Function</span></span>

<span data-ttu-id="c67f8-105">使用目标形状的本地坐标系返回一个转换过的角度。</span><span class="sxs-lookup"><span data-stu-id="c67f8-105">Returns a transformed angle in the destination shape's local coordinate system.</span></span> <span data-ttu-id="c67f8-106">它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。</span><span class="sxs-lookup"><span data-stu-id="c67f8-106">Converts an angle from local coordinates in a source shape to the local coordinates in a destination shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c67f8-107">语法</span><span class="sxs-lookup"><span data-stu-id="c67f8-107">Syntax</span></span>

<span data-ttu-id="c67f8-108">ANGLETOLOC （***srcAngle***、 ***srcRef***、 ***dstRef*** ）</span><span class="sxs-lookup"><span data-stu-id="c67f8-108">ANGLETOLOC(***srcAngle***, ***srcRef***, ***dstRef*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c67f8-109">参数</span><span class="sxs-lookup"><span data-stu-id="c67f8-109">Parameters</span></span>

|<span data-ttu-id="c67f8-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="c67f8-110">**Name**</span></span>|<span data-ttu-id="c67f8-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c67f8-111">**Required/Optional**</span></span>|<span data-ttu-id="c67f8-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c67f8-112">**Data Type**</span></span>|<span data-ttu-id="c67f8-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="c67f8-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c67f8-114">_srcAngle_</span><span class="sxs-lookup"><span data-stu-id="c67f8-114">_srcAngle_</span></span> <br/> |<span data-ttu-id="c67f8-115">必需</span><span class="sxs-lookup"><span data-stu-id="c67f8-115">Required</span></span>  <br/> |<span data-ttu-id="c67f8-116">**数值**</span><span class="sxs-lookup"><span data-stu-id="c67f8-116">**Numeric**</span></span> <br/> |<span data-ttu-id="c67f8-117">源坐标系中的角度。</span><span class="sxs-lookup"><span data-stu-id="c67f8-117">An angle in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="c67f8-118">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="c67f8-118">_srcRef_</span></span> <br/> |<span data-ttu-id="c67f8-119">必需</span><span class="sxs-lookup"><span data-stu-id="c67f8-119">Required</span></span>  <br/> |<span data-ttu-id="c67f8-120">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c67f8-120">**String**</span></span> <br/> | <span data-ttu-id="c67f8-121">对源对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c67f8-121">A reference to a cell in the source object, such as a shape, group, page, and so on.</span></span>  <br/> |
| <span data-ttu-id="c67f8-122">_dstRef_</span><span class="sxs-lookup"><span data-stu-id="c67f8-122">_dstRef_</span></span> <br/> |<span data-ttu-id="c67f8-123">必需</span><span class="sxs-lookup"><span data-stu-id="c67f8-123">Required</span></span>  <br/> |<span data-ttu-id="c67f8-124">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c67f8-124">**String**</span></span> <br/> |<span data-ttu-id="c67f8-125">对目标对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c67f8-125">A reference to a cell in the destination object, such as a shape, group, page, and so on.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c67f8-126">注解</span><span class="sxs-lookup"><span data-stu-id="c67f8-126">Remarks</span></span>

<span data-ttu-id="c67f8-127">可以使用 ANGLETOLOC 函数来按照另一个坐标空间中的角度设置形状中的本地角度单元格。</span><span class="sxs-lookup"><span data-stu-id="c67f8-127">You can use the ANGLETOLOC function to set local angle cells in a shape in terms of an angle from another coordinate space.</span></span>
  
<span data-ttu-id="c67f8-p103">即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。</span><span class="sxs-lookup"><span data-stu-id="c67f8-p103">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span>
  
<span data-ttu-id="c67f8-130">源坐标和目标坐标必须位于同一页上。</span><span class="sxs-lookup"><span data-stu-id="c67f8-130">The source and destination coordinates must be on the same page.</span></span>
  

