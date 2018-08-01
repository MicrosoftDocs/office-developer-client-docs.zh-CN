---
title: DISTTOPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2ba7d372-0c2a-9fa7-0af6-97da0aafdb12
description: 返回由指定坐标表示的点到路径上某一点的最短距离。
ms.openlocfilehash: 227fe860de2e3683b5d7d3e5f9313d1e2e31b2d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780124"
---
# <a name="disttopath-function"></a><span data-ttu-id="4c189-103">DISTTOPATH 函数</span><span class="sxs-lookup"><span data-stu-id="4c189-103">DISTTOPATH Function</span></span>

<span data-ttu-id="4c189-104">返回由指定坐标表示的点到路径上某一点的最短距离。</span><span class="sxs-lookup"><span data-stu-id="4c189-104">Returns the shortest distance from the point represented by the specified coordinates to a point on the path.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="4c189-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="4c189-105">Version Information</span></span>

<span data-ttu-id="4c189-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="4c189-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="4c189-107">语法</span><span class="sxs-lookup"><span data-stu-id="4c189-107">Syntax</span></span>

<span data-ttu-id="4c189-108">DISTTOPATH (* **部分** *，* * *x* * *，* * *y* * *)</span><span class="sxs-lookup"><span data-stu-id="4c189-108">DISTTOPATH(** *section* **, ** *x* **, ** *y* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="4c189-109">参数</span><span class="sxs-lookup"><span data-stu-id="4c189-109">Parameters</span></span>

|<span data-ttu-id="4c189-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="4c189-110">**Name**</span></span>|<span data-ttu-id="4c189-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="4c189-111">**Required/Optional**</span></span>|<span data-ttu-id="4c189-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4c189-112">**Data Type**</span></span>|<span data-ttu-id="4c189-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4c189-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4c189-114">_section_</span><span class="sxs-lookup"><span data-stu-id="4c189-114">_section_</span></span> <br/> |<span data-ttu-id="4c189-115">必需</span><span class="sxs-lookup"><span data-stu-id="4c189-115">Required</span></span>  <br/> |<span data-ttu-id="4c189-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="4c189-116">**String**</span></span> <br/> |<span data-ttu-id="4c189-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="4c189-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="4c189-118">_x_</span><span class="sxs-lookup"><span data-stu-id="4c189-118">_x_</span></span> <br/> |<span data-ttu-id="4c189-119">必需</span><span class="sxs-lookup"><span data-stu-id="4c189-119">Required</span></span>  <br/> |<span data-ttu-id="4c189-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="4c189-120">**Double**</span></span> <br/> |<span data-ttu-id="4c189-121">_X_-点的坐标。</span><span class="sxs-lookup"><span data-stu-id="4c189-121">The  _x_-coordinate of the point.</span></span>  <br/> |
| <span data-ttu-id="4c189-122">_y_</span><span class="sxs-lookup"><span data-stu-id="4c189-122">_y_</span></span> <br/> |<span data-ttu-id="4c189-123">必需</span><span class="sxs-lookup"><span data-stu-id="4c189-123">Required</span></span>  <br/> |<span data-ttu-id="4c189-124">**Double**</span><span class="sxs-lookup"><span data-stu-id="4c189-124">**Double**</span></span> <br/> |<span data-ttu-id="4c189-125">_Y_-点的坐标。</span><span class="sxs-lookup"><span data-stu-id="4c189-125">The  _y_-coordinate of the point.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="4c189-126">返回值</span><span class="sxs-lookup"><span data-stu-id="4c189-126">Return value</span></span>

 <span data-ttu-id="4c189-127">**Double**</span><span class="sxs-lookup"><span data-stu-id="4c189-127">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c189-128">注解</span><span class="sxs-lookup"><span data-stu-id="4c189-128">Remarks</span></span>

<span data-ttu-id="4c189-129">Microsoft Visio 将返回 #REF ！</span><span class="sxs-lookup"><span data-stu-id="4c189-129">Microsoft Visio returns #REF!</span></span> <span data-ttu-id="4c189-130">如果_section_不存在。</span><span class="sxs-lookup"><span data-stu-id="4c189-130">if  _section_ does not exist.</span></span> 
  
<span data-ttu-id="4c189-131">如果该点位于移动方向的左侧，则返回的值为正；如果该点位于移动方向的右侧，则返回的值为负。</span><span class="sxs-lookup"><span data-stu-id="4c189-131">The returned value is positive if the point is to the left of the direction of travel; it is negative if the point is to the right of the direction of travel.</span></span>
  

