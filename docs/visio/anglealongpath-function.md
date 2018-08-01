---
title: ANGLEALONGPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d7f8ca9a-3a89-abab-9805-bd1e24075c3f
description: 返回给定点上路径的切线角度。
ms.openlocfilehash: ec5529037275fc8661972cc7403886cd33150b38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779666"
---
# <a name="anglealongpath-function"></a><span data-ttu-id="323c5-103">ANGLEALONGPATH 函数</span><span class="sxs-lookup"><span data-stu-id="323c5-103">ANGLEALONGPATH Function</span></span>

<span data-ttu-id="323c5-104">返回给定点上路径的切线角度。</span><span class="sxs-lookup"><span data-stu-id="323c5-104">Returns the angle of the tangent to the path at a given point.</span></span>
  
## <a name="version-information"></a><span data-ttu-id="323c5-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="323c5-105">Version Information</span></span>

<span data-ttu-id="323c5-106">添加的版本： Visio 2010
</span><span class="sxs-lookup"><span data-stu-id="323c5-106">Version Added: Visio 2010</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="323c5-107">语法</span><span class="sxs-lookup"><span data-stu-id="323c5-107">Syntax</span></span>

<span data-ttu-id="323c5-108">ANGLEALONGPATH (* **部分** *，* **差旅** * * * *[、 段]* * *)</span><span class="sxs-lookup"><span data-stu-id="323c5-108">ANGLEALONGPATH(** *section* **, ** *travel* ** ** *[,segment]* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="323c5-109">参数</span><span class="sxs-lookup"><span data-stu-id="323c5-109">Parameters</span></span>

|<span data-ttu-id="323c5-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="323c5-110">**Name**</span></span>|<span data-ttu-id="323c5-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="323c5-111">**Required/Optional**</span></span>|<span data-ttu-id="323c5-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="323c5-112">**Data Type**</span></span>|<span data-ttu-id="323c5-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="323c5-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="323c5-114">_section_</span><span class="sxs-lookup"><span data-stu-id="323c5-114">_section_</span></span> <br/> |<span data-ttu-id="323c5-115">必需</span><span class="sxs-lookup"><span data-stu-id="323c5-115">Required</span></span>  <br/> |<span data-ttu-id="323c5-116">**字符串**</span><span class="sxs-lookup"><span data-stu-id="323c5-116">**String**</span></span> <br/> |<span data-ttu-id="323c5-117">Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。</span><span class="sxs-lookup"><span data-stu-id="323c5-117">The Geometry section that represents the path, specified by a reference to its Path cell (for example, Geometry1.Path).</span></span>  <br/> |
| <span data-ttu-id="323c5-118">_出差_</span><span class="sxs-lookup"><span data-stu-id="323c5-118">_travel_</span></span> <br/> |<span data-ttu-id="323c5-119">必需</span><span class="sxs-lookup"><span data-stu-id="323c5-119">Required</span></span>  <br/> |<span data-ttu-id="323c5-120">**Double**</span><span class="sxs-lookup"><span data-stu-id="323c5-120">**Double**</span></span> <br/> |<span data-ttu-id="323c5-p101">从起点到终点沿路径的百分比。必须介于 0 到 1 之间。</span><span class="sxs-lookup"><span data-stu-id="323c5-p101">The percentage along the path from begin point to end point. Must be between 0 and 1.</span></span>  <br/> |
| <span data-ttu-id="323c5-123">_段_</span><span class="sxs-lookup"><span data-stu-id="323c5-123">_segment_</span></span> <br/> |<span data-ttu-id="323c5-124">可选</span><span class="sxs-lookup"><span data-stu-id="323c5-124">Optional</span></span>  <br/> |<span data-ttu-id="323c5-125">**Integer**</span><span class="sxs-lookup"><span data-stu-id="323c5-125">**Integer**</span></span> <br/> |<span data-ttu-id="323c5-126">计算切线角度所用路径的从 1 开始的线段。</span><span class="sxs-lookup"><span data-stu-id="323c5-126">The 1-based segment of the path at which to calculate the tangent angle.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="323c5-127">返回值</span><span class="sxs-lookup"><span data-stu-id="323c5-127">Return value</span></span>

 <span data-ttu-id="323c5-128">**Double**</span><span class="sxs-lookup"><span data-stu-id="323c5-128">**Double**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="323c5-129">注解</span><span class="sxs-lookup"><span data-stu-id="323c5-129">Remarks</span></span>

<span data-ttu-id="323c5-130">如果包含_segment_值，ANGLEALONGPATH 会返回该线段仅的值。</span><span class="sxs-lookup"><span data-stu-id="323c5-130">If you include a  _segment_ value, ANGLEALONGPATH returns the value for that segment only.</span></span> 
  
<span data-ttu-id="323c5-131">如果包含_segment_值，ANGLEALONGPATH 通过使用_差旅_计算_segment_来确定切线点。</span><span class="sxs-lookup"><span data-stu-id="323c5-131">If you include a  _segment_ value, ANGLEALONGPATH determines the point of the tangent by using  _travel_ to calculate the percertage along  _segment_.</span></span>
  
<span data-ttu-id="323c5-132">如果_section_或_segment_不存在，Microsoft Visio 将返回 #REF ！。</span><span class="sxs-lookup"><span data-stu-id="323c5-132">If either  _section_ or  _segment_ does not exist, Microsoft Visio returns #REF!.</span></span> 
  

