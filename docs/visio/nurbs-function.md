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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438454"
---
# <a name="nurbs-function"></a><span data-ttu-id="5ae2f-104">NURBS 函数</span><span class="sxs-lookup"><span data-stu-id="5ae2f-104">NURBS Function</span></span>

<span data-ttu-id="5ae2f-105">返回一个非均匀有理 B 样条 (NURBS)。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-105">Returns a nonuniform rational B-spline (NURBS).</span></span> <span data-ttu-id="5ae2f-106">此函数用于 NURBSTo 几何图形行中的 E 单元格。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-106">This function is used in the E cell in the NURBSTo geometry rows.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="5ae2f-107">语法</span><span class="sxs-lookup"><span data-stu-id="5ae2f-107">Syntax</span></span>

<span data-ttu-id="5ae2f-108">NURBS (\* \* *knotLast* \* *、* **度** *、* \* *xType* \* *、* \* *yType* \* *、* \* *x1* \* *、* \* *y1* \* *、* \* *knot1* \* *、* \* *weight1* \* *、* \* \* *、* \* \* \*)</span><span class="sxs-lookup"><span data-stu-id="5ae2f-108">NURBS(\*\* *knotLast* \*\*, \*\* *degree* \*\*, \*\* *xType* \*\*, \*\* *yType* \*\*, \*\* *x1* \*\*, \*\* *y1* \*\*, \*\* *knot1* \*\*, \*\* *weight1* \*\*, ...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="5ae2f-109">参数</span><span class="sxs-lookup"><span data-stu-id="5ae2f-109">Parameters</span></span>

|<span data-ttu-id="5ae2f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-110">**Name**</span></span>|<span data-ttu-id="5ae2f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-111">**Required/Optional**</span></span>|<span data-ttu-id="5ae2f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-112">**Data Type**</span></span>|<span data-ttu-id="5ae2f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5ae2f-114">_knotLast_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-114">_knotLast_</span></span> <br/> |<span data-ttu-id="5ae2f-115">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-115">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-116">**string**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-116">**string**</span></span> <br/> | <span data-ttu-id="5ae2f-117">最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-117">The last knot.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-118">_°_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-118">_degree_</span></span> <br/> |<span data-ttu-id="5ae2f-119">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-119">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-120">**数值**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-120">**Numeric**</span></span> <br/> |<span data-ttu-id="5ae2f-121">样条的度数。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-121">The spline's degree.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-122">_xType_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-122">_xType_</span></span> <br/> |<span data-ttu-id="5ae2f-123">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-123">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-124">**数值**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-124">**Numeric**</span></span> <br/> |<span data-ttu-id="5ae2f-125">指定如何解释_x_输入数据。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-125">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="5ae2f-126">如果_xType_为 0, 则所有_x_输入数据都被解释为宽度的百分比。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-126">If  _xType_ is 0, all  _x_ input data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="5ae2f-127">如果_xType_为 1, 则所有_x_输入数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-127">If  _xType_ is 1, all  _x_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-128">_yType_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-128">_yType_</span></span> <br/> |<span data-ttu-id="5ae2f-129">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-129">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-130">**数值**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-130">**Numeric**</span></span> <br/> |<span data-ttu-id="5ae2f-131">指定如何解释_y_输入数据。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-131">Specifies how to interpret the  _y_ input data.</span></span> <span data-ttu-id="5ae2f-132">如果_yType_为 0, 则所有_y_输入数据将被解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-132">If  _yType_ is 0, all  _y_ input data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="5ae2f-133">如果_yType_为 1, 则所有_y_输入数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-133">If  _yType_ is 1, all  _y_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-134">_x1_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-134">_x1_</span></span> <br/> |<span data-ttu-id="5ae2f-135">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-135">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-136">**String**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-136">**String**</span></span> <br/> |<span data-ttu-id="5ae2f-137">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-137">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-138">_y1_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-138">_y1_</span></span> <br/> |<span data-ttu-id="5ae2f-139">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-139">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-140">**String**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-140">**String**</span></span> <br/> |<span data-ttu-id="5ae2f-141">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-141">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-142">_knot1_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-142">_knot1_</span></span> <br/> |<span data-ttu-id="5ae2f-143">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-143">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-144">**String**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-144">**String**</span></span> <br/> |<span data-ttu-id="5ae2f-145">B 样条上的节点。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-145">A knot on the B-spline.</span></span>  <br/> |
| <span data-ttu-id="5ae2f-146">_weight1_</span><span class="sxs-lookup"><span data-stu-id="5ae2f-146">_weight1_</span></span> <br/> |<span data-ttu-id="5ae2f-147">必需</span><span class="sxs-lookup"><span data-stu-id="5ae2f-147">Required</span></span>  <br/> |<span data-ttu-id="5ae2f-148">**String**</span><span class="sxs-lookup"><span data-stu-id="5ae2f-148">**String**</span></span> <br/> |<span data-ttu-id="5ae2f-149">B 样条的粗细。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-149">A weight on the B-spline.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5ae2f-150">说明</span><span class="sxs-lookup"><span data-stu-id="5ae2f-150">Remarks</span></span>

<span data-ttu-id="5ae2f-151">对于每个*x*参数, 必须有一个*y*参数;否则, 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-151">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
<span data-ttu-id="5ae2f-152">您必须指定至少一个*x*、 *y*、*节点*和*权重*参数;否则, Visio 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="5ae2f-152">You must specify at least one  *x*, *y*, *knot*  , and  *weight*  argument; otherwise, Visio returns an error.</span></span> 
  

