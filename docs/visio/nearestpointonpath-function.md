---
title: NEARESTPOINTONPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 539bf79a-df09-2048-2aba-8c863dd26fc2
description: 返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
ms.openlocfilehash: ced20cdf1f3531eafaa03c2666b09334029fd3da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407331"
---
# <a name="nearestpointonpath-function"></a><span data-ttu-id="ee60e-103">NEARESTPOINTONPATH 函数</span><span class="sxs-lookup"><span data-stu-id="ee60e-103">NEARESTPOINTONPATH Function</span></span>

<span data-ttu-id="ee60e-104">返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="ee60e-104">Returns the percentage of the distance along the path of the point that is nearest to the specified coordinates, as a value between 0 and 1.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="ee60e-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="ee60e-105">Version Information</span></span>

<span data-ttu-id="ee60e-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="ee60e-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ee60e-107">语法</span><span class="sxs-lookup"><span data-stu-id="ee60e-107">Syntax</span></span>

<span data-ttu-id="ee60e-108">NEARESTPOINTONPATH (\*\* *section* \*\*， \*\* *x* \*\*， \*\* *y* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="ee60e-108">NEARESTPOINTONPATH(\*\* *section* \*\*, \*\* *x* \*\*, \*\* *y* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ee60e-109">参数</span><span class="sxs-lookup"><span data-stu-id="ee60e-109">Parameters</span></span>

|<span data-ttu-id="ee60e-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="ee60e-110">**Name**</span></span>|<span data-ttu-id="ee60e-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ee60e-111">**Required/Optional**</span></span>|<span data-ttu-id="ee60e-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ee60e-112">**Data Type**</span></span>|<span data-ttu-id="ee60e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee60e-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ee60e-114">_section_</span><span class="sxs-lookup"><span data-stu-id="ee60e-114">_section_</span></span> <br/> |<span data-ttu-id="ee60e-115">必需</span><span class="sxs-lookup"><span data-stu-id="ee60e-115">Required</span></span>  <br/> |<span data-ttu-id="ee60e-116">**String**</span><span class="sxs-lookup"><span data-stu-id="ee60e-116">**String**</span></span> <br/> |<span data-ttu-id="ee60e-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="ee60e-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="ee60e-118">_x_</span><span class="sxs-lookup"><span data-stu-id="ee60e-118">_x_</span></span> <br/> |<span data-ttu-id="ee60e-119">必需</span><span class="sxs-lookup"><span data-stu-id="ee60e-119">Required</span></span>  <br/> |<span data-ttu-id="ee60e-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="ee60e-120">**Double**</span></span> <br/> |<span data-ttu-id="ee60e-121">指定点的  _x_ 坐标。</span><span class="sxs-lookup"><span data-stu-id="ee60e-121">The  _x_-coordinate of the specified point.</span></span>  <br/> |
| <span data-ttu-id="ee60e-122">_y_</span><span class="sxs-lookup"><span data-stu-id="ee60e-122">_y_</span></span> <br/> |<span data-ttu-id="ee60e-123">必需</span><span class="sxs-lookup"><span data-stu-id="ee60e-123">Required</span></span>  <br/> |<span data-ttu-id="ee60e-124">**Double**</span><span class="sxs-lookup"><span data-stu-id="ee60e-124">**Double**</span></span> <br/> |<span data-ttu-id="ee60e-125">_指定点的 y_ 坐标。</span><span class="sxs-lookup"><span data-stu-id="ee60e-125">The  _y_-coordinate of the specified point.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="ee60e-126">返回值</span><span class="sxs-lookup"><span data-stu-id="ee60e-126">Return value</span></span>

 <span data-ttu-id="ee60e-127">**Double**</span><span class="sxs-lookup"><span data-stu-id="ee60e-127">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ee60e-128">备注</span><span class="sxs-lookup"><span data-stu-id="ee60e-128">Remarks</span></span>

<span data-ttu-id="ee60e-129">如果 _section_ 不存在，Microsoft Visio返回 #REF！。</span><span class="sxs-lookup"><span data-stu-id="ee60e-129">If  _section_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  

