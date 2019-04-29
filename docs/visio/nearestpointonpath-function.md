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
# <a name="nearestpointonpath-function"></a><span data-ttu-id="09542-103">NEARESTPOINTONPATH 函数</span><span class="sxs-lookup"><span data-stu-id="09542-103">NEARESTPOINTONPATH Function</span></span>

<span data-ttu-id="09542-104">返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="09542-104">Returns the percentage of the distance along the path of the point that is nearest to the specified coordinates, as a value between 0 and 1.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="09542-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="09542-105">Version Information</span></span>

<span data-ttu-id="09542-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="09542-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="09542-107">语法</span><span class="sxs-lookup"><span data-stu-id="09542-107">Syntax</span></span>

<span data-ttu-id="09542-108">NEARESTPOINTONPATH (\* \* *section* \* \*, \* \* *x* \* \*, \* \* *y* \* \*)</span><span class="sxs-lookup"><span data-stu-id="09542-108">NEARESTPOINTONPATH(\*\* *section* \*\*, \*\* *x* \*\*, \*\* *y* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="09542-109">参数</span><span class="sxs-lookup"><span data-stu-id="09542-109">Parameters</span></span>

|<span data-ttu-id="09542-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="09542-110">**Name**</span></span>|<span data-ttu-id="09542-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="09542-111">**Required/Optional**</span></span>|<span data-ttu-id="09542-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="09542-112">**Data Type**</span></span>|<span data-ttu-id="09542-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="09542-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="09542-114">_section_</span><span class="sxs-lookup"><span data-stu-id="09542-114">_section_</span></span> <br/> |<span data-ttu-id="09542-115">必需</span><span class="sxs-lookup"><span data-stu-id="09542-115">Required</span></span>  <br/> |<span data-ttu-id="09542-116">**String**</span><span class="sxs-lookup"><span data-stu-id="09542-116">**String**</span></span> <br/> |<span data-ttu-id="09542-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="09542-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="09542-118">_x_</span><span class="sxs-lookup"><span data-stu-id="09542-118">_x_</span></span> <br/> |<span data-ttu-id="09542-119">必需</span><span class="sxs-lookup"><span data-stu-id="09542-119">Required</span></span>  <br/> |<span data-ttu-id="09542-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="09542-120">**Double**</span></span> <br/> |<span data-ttu-id="09542-121">指定点的_x_坐标。</span><span class="sxs-lookup"><span data-stu-id="09542-121">The  _x_-coordinate of the specified point.</span></span>  <br/> |
| <span data-ttu-id="09542-122">_y_</span><span class="sxs-lookup"><span data-stu-id="09542-122">_y_</span></span> <br/> |<span data-ttu-id="09542-123">必需</span><span class="sxs-lookup"><span data-stu-id="09542-123">Required</span></span>  <br/> |<span data-ttu-id="09542-124">**Double**</span><span class="sxs-lookup"><span data-stu-id="09542-124">**Double**</span></span> <br/> |<span data-ttu-id="09542-125">指定点的_y_坐标。</span><span class="sxs-lookup"><span data-stu-id="09542-125">The  _y_-coordinate of the specified point.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="09542-126">返回值</span><span class="sxs-lookup"><span data-stu-id="09542-126">Return value</span></span>

 <span data-ttu-id="09542-127">**Double**</span><span class="sxs-lookup"><span data-stu-id="09542-127">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="09542-128">备注</span><span class="sxs-lookup"><span data-stu-id="09542-128">Remarks</span></span>

<span data-ttu-id="09542-129">如果_section_不存在, Microsoft Visio 将返回 #REF!。</span><span class="sxs-lookup"><span data-stu-id="09542-129">If  _section_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  

