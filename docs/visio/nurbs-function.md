---
title: NURBS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251579
localization_priority: Normal
ms.assetid: f34db20d-6501-2026-a5e8-29c4d4cb2405
description: 返回一个非均匀有理 B 样条 (NURBS)。 此函数用于 NURBSTo 几何图形行中的 E 单元格。
ms.openlocfilehash: af92374a829c0df8e71ac81e630abc4fa64988dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340122"
---
# <a name="nurbs-function"></a><span data-ttu-id="e36b1-104">NURBS 函数</span><span class="sxs-lookup"><span data-stu-id="e36b1-104">NURBS Function</span></span>

<span data-ttu-id="e36b1-105">返回一个非均匀有理 B 样条 (NURBS)。</span><span class="sxs-lookup"><span data-stu-id="e36b1-105">Returns a nonuniform rational B-spline (NURBS).</span></span> <span data-ttu-id="e36b1-106">此函数用于 NURBSTo 几何图形行中的 E 单元格。</span><span class="sxs-lookup"><span data-stu-id="e36b1-106">This function is used in the E cell in the NURBSTo geometry rows.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e36b1-107">语法</span><span class="sxs-lookup"><span data-stu-id="e36b1-107">Syntax</span></span>

<span data-ttu-id="e36b1-108">NURBS (\* \* *knotLast* \* *、* **度** *、* \* *xType* \* *、* \* *yType* \* *、* \* *x1* \* *、* \* *y1* \* *、* \* *knot1* \* *、* \* *weight1* \* *、* \* \* *、* \* \* \*)</span><span class="sxs-lookup"><span data-stu-id="e36b1-108">NURBS(\*\* *knotLast* \*\*, \*\* *degree* \*\*, \*\* *xType* \*\*, \*\* *yType* \*\*, \*\* *x1* \*\*, \*\* *y1* \*\*, \*\* *knot1* \*\*, \*\* *weight1* \*\*, ...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e36b1-109">参数</span><span class="sxs-lookup"><span data-stu-id="e36b1-109">Parameters</span></span>

|<span data-ttu-id="e36b1-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="e36b1-110">**Name**</span></span>|<span data-ttu-id="e36b1-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e36b1-111">**Required/Optional**</span></span>|<span data-ttu-id="e36b1-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e36b1-112">**Data Type**</span></span>|<span data-ttu-id="e36b1-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="e36b1-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e36b1-114">_knotLast_</span><span class="sxs-lookup"><span data-stu-id="e36b1-114">_knotLast_</span></span> <br/> |<span data-ttu-id="e36b1-115">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-115">Required</span></span>  <br/> |<span data-ttu-id="e36b1-116">**string**</span><span class="sxs-lookup"><span data-stu-id="e36b1-116">**string**</span></span> <br/> | <span data-ttu-id="e36b1-117">最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="e36b1-117">The last knot.</span></span>  <br/> |
| <span data-ttu-id="e36b1-118">_°_</span><span class="sxs-lookup"><span data-stu-id="e36b1-118">_degree_</span></span> <br/> |<span data-ttu-id="e36b1-119">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-119">Required</span></span>  <br/> |<span data-ttu-id="e36b1-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="e36b1-120">**Numeric**</span></span> <br/> |<span data-ttu-id="e36b1-121">样条的度数。</span><span class="sxs-lookup"><span data-stu-id="e36b1-121">The spline's degree.</span></span>  <br/> |
| <span data-ttu-id="e36b1-122">_xType_</span><span class="sxs-lookup"><span data-stu-id="e36b1-122">_xType_</span></span> <br/> |<span data-ttu-id="e36b1-123">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-123">Required</span></span>  <br/> |<span data-ttu-id="e36b1-124">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="e36b1-124">**Numeric**</span></span> <br/> |<span data-ttu-id="e36b1-125">指定如何解释_x_输入数据。</span><span class="sxs-lookup"><span data-stu-id="e36b1-125">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="e36b1-126">如果_xType_为 0, 则所有_x_输入数据都被解释为宽度的百分比。</span><span class="sxs-lookup"><span data-stu-id="e36b1-126">If  _xType_ is 0, all  _x_ input data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="e36b1-127">如果_xType_为 1, 则所有_x_输入数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="e36b1-127">If  _xType_ is 1, all  _x_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="e36b1-128">_yType_</span><span class="sxs-lookup"><span data-stu-id="e36b1-128">_yType_</span></span> <br/> |<span data-ttu-id="e36b1-129">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-129">Required</span></span>  <br/> |<span data-ttu-id="e36b1-130">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="e36b1-130">**Numeric**</span></span> <br/> |<span data-ttu-id="e36b1-131">指定如何解释_y_输入数据。</span><span class="sxs-lookup"><span data-stu-id="e36b1-131">Specifies how to interpret the  _y_ input data.</span></span> <span data-ttu-id="e36b1-132">如果_yType_为 0, 则所有_y_输入数据将被解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="e36b1-132">If  _yType_ is 0, all  _y_ input data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="e36b1-133">如果_yType_为 1, 则所有_y_输入数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="e36b1-133">If  _yType_ is 1, all  _y_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="e36b1-134">_x1_</span><span class="sxs-lookup"><span data-stu-id="e36b1-134">_x1_</span></span> <br/> |<span data-ttu-id="e36b1-135">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-135">Required</span></span>  <br/> |<span data-ttu-id="e36b1-136">**String**</span><span class="sxs-lookup"><span data-stu-id="e36b1-136">**String**</span></span> <br/> |<span data-ttu-id="e36b1-137">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="e36b1-137">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="e36b1-138">_y1_</span><span class="sxs-lookup"><span data-stu-id="e36b1-138">_y1_</span></span> <br/> |<span data-ttu-id="e36b1-139">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-139">Required</span></span>  <br/> |<span data-ttu-id="e36b1-140">**String**</span><span class="sxs-lookup"><span data-stu-id="e36b1-140">**String**</span></span> <br/> |<span data-ttu-id="e36b1-141">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="e36b1-141">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="e36b1-142">_knot1_</span><span class="sxs-lookup"><span data-stu-id="e36b1-142">_knot1_</span></span> <br/> |<span data-ttu-id="e36b1-143">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-143">Required</span></span>  <br/> |<span data-ttu-id="e36b1-144">**String**</span><span class="sxs-lookup"><span data-stu-id="e36b1-144">**String**</span></span> <br/> |<span data-ttu-id="e36b1-145">B 样条上的节点。</span><span class="sxs-lookup"><span data-stu-id="e36b1-145">A knot on the B-spline.</span></span>  <br/> |
| <span data-ttu-id="e36b1-146">_weight1_</span><span class="sxs-lookup"><span data-stu-id="e36b1-146">_weight1_</span></span> <br/> |<span data-ttu-id="e36b1-147">必需</span><span class="sxs-lookup"><span data-stu-id="e36b1-147">Required</span></span>  <br/> |<span data-ttu-id="e36b1-148">**String**</span><span class="sxs-lookup"><span data-stu-id="e36b1-148">**String**</span></span> <br/> |<span data-ttu-id="e36b1-149">B 样条的粗细。</span><span class="sxs-lookup"><span data-stu-id="e36b1-149">A weight on the B-spline.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e36b1-150">注解</span><span class="sxs-lookup"><span data-stu-id="e36b1-150">Remarks</span></span>

<span data-ttu-id="e36b1-151">对于每个*x*参数, 必须有一个*y*参数;否则, 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="e36b1-151">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
<span data-ttu-id="e36b1-152">您必须指定至少一个*x*、 *y*、*节点*和*权重*参数;否则, Visio 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="e36b1-152">You must specify at least one  *x*, *y*, *knot*  , and  *weight*  argument; otherwise, Visio returns an error.</span></span> 
  

