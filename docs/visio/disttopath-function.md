---
title: DISTTOPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2ba7d372-0c2a-9fa7-0af6-97da0aafdb12
description: 返回由指定坐标表示的点到路径上某一点的最短距离。
ms.openlocfilehash: 5727b24739705d3e562150c48fe77f7ad6eedb57
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332688"
---
# <a name="disttopath-function"></a><span data-ttu-id="26102-103">DISTTOPATH 函数</span><span class="sxs-lookup"><span data-stu-id="26102-103">DISTTOPATH Function</span></span>

<span data-ttu-id="26102-104">返回由指定坐标表示的点到路径上某一点的最短距离。</span><span class="sxs-lookup"><span data-stu-id="26102-104">Returns the shortest distance from the point represented by the specified coordinates to a point on the path.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="26102-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="26102-105">Version Information</span></span>

<span data-ttu-id="26102-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="26102-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="26102-107">语法</span><span class="sxs-lookup"><span data-stu-id="26102-107">Syntax</span></span>

<span data-ttu-id="26102-108">DISTTOPATH (\* \* *section* \* \*, \* \* *x* \* \*, \* \* *y* \* \*)</span><span class="sxs-lookup"><span data-stu-id="26102-108">DISTTOPATH(\*\* *section* \*\*, \*\* *x* \*\*, \*\* *y* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="26102-109">参数</span><span class="sxs-lookup"><span data-stu-id="26102-109">Parameters</span></span>

|<span data-ttu-id="26102-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="26102-110">**Name**</span></span>|<span data-ttu-id="26102-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="26102-111">**Required/Optional**</span></span>|<span data-ttu-id="26102-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="26102-112">**Data Type**</span></span>|<span data-ttu-id="26102-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="26102-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="26102-114">_section_</span><span class="sxs-lookup"><span data-stu-id="26102-114">_section_</span></span> <br/> |<span data-ttu-id="26102-115">必需</span><span class="sxs-lookup"><span data-stu-id="26102-115">Required</span></span>  <br/> |<span data-ttu-id="26102-116">**String**</span><span class="sxs-lookup"><span data-stu-id="26102-116">**String**</span></span> <br/> |<span data-ttu-id="26102-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="26102-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="26102-118">_x_</span><span class="sxs-lookup"><span data-stu-id="26102-118">_x_</span></span> <br/> |<span data-ttu-id="26102-119">必需</span><span class="sxs-lookup"><span data-stu-id="26102-119">Required</span></span>  <br/> |<span data-ttu-id="26102-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="26102-120">**Double**</span></span> <br/> |<span data-ttu-id="26102-121">点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="26102-121">The  _x_-coordinate of the point.</span></span>  <br/> |
| <span data-ttu-id="26102-122">_y_</span><span class="sxs-lookup"><span data-stu-id="26102-122">_y_</span></span> <br/> |<span data-ttu-id="26102-123">必需</span><span class="sxs-lookup"><span data-stu-id="26102-123">Required</span></span>  <br/> |<span data-ttu-id="26102-124">**Double**</span><span class="sxs-lookup"><span data-stu-id="26102-124">**Double**</span></span> <br/> |<span data-ttu-id="26102-125">点的_y_坐标。</span><span class="sxs-lookup"><span data-stu-id="26102-125">The  _y_-coordinate of the point.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="26102-126">返回值</span><span class="sxs-lookup"><span data-stu-id="26102-126">Return value</span></span>

 <span data-ttu-id="26102-127">**Double**</span><span class="sxs-lookup"><span data-stu-id="26102-127">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="26102-128">备注</span><span class="sxs-lookup"><span data-stu-id="26102-128">Remarks</span></span>

<span data-ttu-id="26102-129">Microsoft Visio 将返回 #REF!</span><span class="sxs-lookup"><span data-stu-id="26102-129">Microsoft Visio returns #REF!</span></span> <span data-ttu-id="26102-130">如果_section_不存在。</span><span class="sxs-lookup"><span data-stu-id="26102-130">if  _section_ does not exist.</span></span> 
  
<span data-ttu-id="26102-131">如果该点位于移动方向的左侧，则返回的值为正；如果该点位于移动方向的右侧，则返回的值为负。</span><span class="sxs-lookup"><span data-stu-id="26102-131">The returned value is positive if the point is to the left of the direction of travel; it is negative if the point is to the right of the direction of travel.</span></span>
  

