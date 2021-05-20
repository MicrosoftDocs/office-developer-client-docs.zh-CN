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
description: 返回 NURBS (非均匀有理 B 样) 。 此函数在 NURBSTo 几何图形行的 E 单元格中使用。
ms.openlocfilehash: af92374a829c0df8e71ac81e630abc4fa64988dc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438454"
---
# <a name="nurbs-function"></a><span data-ttu-id="897cc-104">NURBS 函数</span><span class="sxs-lookup"><span data-stu-id="897cc-104">NURBS Function</span></span>

<span data-ttu-id="897cc-105">返回 NURBS (非均匀有理 B 样) 。</span><span class="sxs-lookup"><span data-stu-id="897cc-105">Returns a nonuniform rational B-spline (NURBS).</span></span> <span data-ttu-id="897cc-106">此函数在 NURBSTo 几何图形行的 E 单元格中使用。</span><span class="sxs-lookup"><span data-stu-id="897cc-106">This function is used in the E cell in the NURBSTo geometry rows.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="897cc-107">语法</span><span class="sxs-lookup"><span data-stu-id="897cc-107">Syntax</span></span>

<span data-ttu-id="897cc-108">NURBS (\*\* *knotLast* \*\*， \*\* *degree* \*\*， \*\* *xType* \*\*， \*\* *yType* \*\*， \*\* *x1* \*\*， \*\* *y1* \*\*， \*\* *knot1* \*\*， \*\* *weight1* \*\*， ...) </span><span class="sxs-lookup"><span data-stu-id="897cc-108">NURBS(\*\* *knotLast* \*\*, \*\* *degree* \*\*, \*\* *xType* \*\*, \*\* *yType* \*\*, \*\* *x1* \*\*, \*\* *y1* \*\*, \*\* *knot1* \*\*, \*\* *weight1* \*\*, ...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="897cc-109">参数</span><span class="sxs-lookup"><span data-stu-id="897cc-109">Parameters</span></span>

|<span data-ttu-id="897cc-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="897cc-110">**Name**</span></span>|<span data-ttu-id="897cc-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="897cc-111">**Required/Optional**</span></span>|<span data-ttu-id="897cc-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="897cc-112">**Data Type**</span></span>|<span data-ttu-id="897cc-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="897cc-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="897cc-114">_knotLast_</span><span class="sxs-lookup"><span data-stu-id="897cc-114">_knotLast_</span></span> <br/> |<span data-ttu-id="897cc-115">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-115">Required</span></span>  <br/> |<span data-ttu-id="897cc-116">**string**</span><span class="sxs-lookup"><span data-stu-id="897cc-116">**string**</span></span> <br/> | <span data-ttu-id="897cc-117">最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="897cc-117">The last knot.</span></span>  <br/> |
| <span data-ttu-id="897cc-118">_degree_</span><span class="sxs-lookup"><span data-stu-id="897cc-118">_degree_</span></span> <br/> |<span data-ttu-id="897cc-119">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-119">Required</span></span>  <br/> |<span data-ttu-id="897cc-120">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="897cc-120">**Numeric**</span></span> <br/> |<span data-ttu-id="897cc-121">样条的度数。</span><span class="sxs-lookup"><span data-stu-id="897cc-121">The spline's degree.</span></span>  <br/> |
| <span data-ttu-id="897cc-122">_xType_</span><span class="sxs-lookup"><span data-stu-id="897cc-122">_xType_</span></span> <br/> |<span data-ttu-id="897cc-123">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-123">Required</span></span>  <br/> |<span data-ttu-id="897cc-124">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="897cc-124">**Numeric**</span></span> <br/> |<span data-ttu-id="897cc-125">指定如何解释 x  _输入_ 数据。</span><span class="sxs-lookup"><span data-stu-id="897cc-125">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="897cc-126">如果  _xType_ 为 0，则所有  _x_ 输入数据都将被解释为 Width 的百分比。</span><span class="sxs-lookup"><span data-stu-id="897cc-126">If  _xType_ is 0, all  _x_ input data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="897cc-127">如果  _xType_ 为 1，则所有  _x_ 输入数据都将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="897cc-127">If  _xType_ is 1, all  _x_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="897cc-128">_yType_</span><span class="sxs-lookup"><span data-stu-id="897cc-128">_yType_</span></span> <br/> |<span data-ttu-id="897cc-129">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-129">Required</span></span>  <br/> |<span data-ttu-id="897cc-130">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="897cc-130">**Numeric**</span></span> <br/> |<span data-ttu-id="897cc-131">指定如何解释  _y 输入_ 数据。</span><span class="sxs-lookup"><span data-stu-id="897cc-131">Specifies how to interpret the  _y_ input data.</span></span> <span data-ttu-id="897cc-132">如果  _yType_ 为 0，则  _所有 y_ 输入数据都将被解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="897cc-132">If  _yType_ is 0, all  _y_ input data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="897cc-133">如果  _yType_ 为 1，则  _所有 y_ 输入数据都将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="897cc-133">If  _yType_ is 1, all  _y_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="897cc-134">_x1_</span><span class="sxs-lookup"><span data-stu-id="897cc-134">_x1_</span></span> <br/> |<span data-ttu-id="897cc-135">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-135">Required</span></span>  <br/> |<span data-ttu-id="897cc-136">**String**</span><span class="sxs-lookup"><span data-stu-id="897cc-136">**String**</span></span> <br/> |<span data-ttu-id="897cc-137">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="897cc-137">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="897cc-138">_y1_</span><span class="sxs-lookup"><span data-stu-id="897cc-138">_y1_</span></span> <br/> |<span data-ttu-id="897cc-139">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-139">Required</span></span>  <br/> |<span data-ttu-id="897cc-140">**String**</span><span class="sxs-lookup"><span data-stu-id="897cc-140">**String**</span></span> <br/> |<span data-ttu-id="897cc-141">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="897cc-141">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="897cc-142">_knot1_</span><span class="sxs-lookup"><span data-stu-id="897cc-142">_knot1_</span></span> <br/> |<span data-ttu-id="897cc-143">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-143">Required</span></span>  <br/> |<span data-ttu-id="897cc-144">**String**</span><span class="sxs-lookup"><span data-stu-id="897cc-144">**String**</span></span> <br/> |<span data-ttu-id="897cc-145">B 样条上的节点。</span><span class="sxs-lookup"><span data-stu-id="897cc-145">A knot on the B-spline.</span></span>  <br/> |
| <span data-ttu-id="897cc-146">_weight1_</span><span class="sxs-lookup"><span data-stu-id="897cc-146">_weight1_</span></span> <br/> |<span data-ttu-id="897cc-147">必需</span><span class="sxs-lookup"><span data-stu-id="897cc-147">Required</span></span>  <br/> |<span data-ttu-id="897cc-148">**String**</span><span class="sxs-lookup"><span data-stu-id="897cc-148">**String**</span></span> <br/> |<span data-ttu-id="897cc-149">B 样条的粗细。</span><span class="sxs-lookup"><span data-stu-id="897cc-149">A weight on the B-spline.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="897cc-150">备注</span><span class="sxs-lookup"><span data-stu-id="897cc-150">Remarks</span></span>

<span data-ttu-id="897cc-151">对于每个  *x*  参数，都必须有  *一个 y*  参数;否则，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="897cc-151">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
<span data-ttu-id="897cc-152">必须至少指定一个 *x、y、knot* 和 *weight* 参数; 否则，Visio返回错误。</span><span class="sxs-lookup"><span data-stu-id="897cc-152">You must specify at least one  *x*, *y*, *knot*  , and  *weight*  argument; otherwise, Visio returns an error.</span></span> 
  

