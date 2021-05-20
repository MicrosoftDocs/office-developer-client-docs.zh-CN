---
title: ANGLEALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d7f8ca9a-3a89-abab-9805-bd1e24075c3f
description: 返回给定点上路径的切线角度。
ms.openlocfilehash: a15e45ff6135972cd1cd78382147a493f8fc8d69
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160291"
---
# <a name="anglealongpath-function"></a><span data-ttu-id="2bd7e-103">ANGLEALONGPATH 函数</span><span class="sxs-lookup"><span data-stu-id="2bd7e-103">ANGLEALONGPATH Function</span></span>

<span data-ttu-id="2bd7e-104">返回给定点上路径的切线角度。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-104">Returns the angle of the tangent to the path at a given point.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="2bd7e-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="2bd7e-105">Version Information</span></span>

<span data-ttu-id="2bd7e-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="2bd7e-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2bd7e-107">语法</span><span class="sxs-lookup"><span data-stu-id="2bd7e-107">Syntax</span></span>

<span data-ttu-id="2bd7e-108">ANGLEALONGPATH (***section***， ***travel*** ***[，segment]*** ) </span><span class="sxs-lookup"><span data-stu-id="2bd7e-108">ANGLEALONGPATH(***section***, ***travel*** ***[,segment]*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="2bd7e-109">参数</span><span class="sxs-lookup"><span data-stu-id="2bd7e-109">Parameters</span></span>

|<span data-ttu-id="2bd7e-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-110">**Name**</span></span>|<span data-ttu-id="2bd7e-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-111">**Required/Optional**</span></span>|<span data-ttu-id="2bd7e-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-112">**Data Type**</span></span>|<span data-ttu-id="2bd7e-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2bd7e-114">_section_</span><span class="sxs-lookup"><span data-stu-id="2bd7e-114">_section_</span></span> <br/> |<span data-ttu-id="2bd7e-115">必需</span><span class="sxs-lookup"><span data-stu-id="2bd7e-115">Required</span></span>  <br/> |<span data-ttu-id="2bd7e-116">**String**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-116">**String**</span></span> <br/> |<span data-ttu-id="2bd7e-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="2bd7e-118">_travel_</span><span class="sxs-lookup"><span data-stu-id="2bd7e-118">_travel_</span></span> <br/> |<span data-ttu-id="2bd7e-119">必需</span><span class="sxs-lookup"><span data-stu-id="2bd7e-119">Required</span></span>  <br/> |<span data-ttu-id="2bd7e-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-120">**Double**</span></span> <br/> |<span data-ttu-id="2bd7e-p101">从起点到终点沿路径的百分比。必须介于 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-p101">The percentage along the path from begin point to end point. Must be between 0 and 1.</span></span>  <br/> |
| <span data-ttu-id="2bd7e-123">_segment_</span><span class="sxs-lookup"><span data-stu-id="2bd7e-123">_segment_</span></span> <br/> |<span data-ttu-id="2bd7e-124">可选</span><span class="sxs-lookup"><span data-stu-id="2bd7e-124">Optional</span></span>  <br/> |<span data-ttu-id="2bd7e-125">**Integer**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-125">**Integer**</span></span> <br/> |<span data-ttu-id="2bd7e-126">计算切线角度所用路径的从 1 开始的线段。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-126">The 1-based segment of the path at which to calculate the tangent angle.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="2bd7e-127">返回值</span><span class="sxs-lookup"><span data-stu-id="2bd7e-127">Return value</span></span>

 <span data-ttu-id="2bd7e-128">**Double**</span><span class="sxs-lookup"><span data-stu-id="2bd7e-128">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2bd7e-129">备注</span><span class="sxs-lookup"><span data-stu-id="2bd7e-129">Remarks</span></span>

<span data-ttu-id="2bd7e-130">如果  _包含段值_ ，ANGLEALONGPATH 将仅返回该段的值。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-130">If you include a  _segment_ value, ANGLEALONGPATH returns the value for that segment only.</span></span> 
  
<span data-ttu-id="2bd7e-131">如果包含线  _段_ 值，ANGLEALONGPATH 将通过使用  _travel_ 来计算线段的 percertage，确定切  _线点_。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-131">If you include a  _segment_ value, ANGLEALONGPATH determines the point of the tangent by using  _travel_ to calculate the percertage along  _segment_.</span></span>
  
<span data-ttu-id="2bd7e-132">如果任 _一节__或_ 段不存在，Microsoft Visio返回 #REF！。</span><span class="sxs-lookup"><span data-stu-id="2bd7e-132">If either  _section_ or  _segment_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  

