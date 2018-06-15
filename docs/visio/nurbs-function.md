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
description: 返回非均匀有理 B 样条 (NURBS)。 NURBSTo geometry 行中的 E 单元格中使用此函数。
ms.openlocfilehash: 005a66b9da2425beaf416ec2273c10446c183add
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19780834"
---
# <a name="nurbs-function"></a><span data-ttu-id="1376b-104">NURBS 函数</span><span class="sxs-lookup"><span data-stu-id="1376b-104">NURBS Function</span></span>

<span data-ttu-id="1376b-105">返回非均匀有理 B 样条 (NURBS)。</span><span class="sxs-lookup"><span data-stu-id="1376b-105">Returns a nonuniform rational B-spline (NURBS).</span></span> <span data-ttu-id="1376b-106">NURBSTo geometry 行中的 E 单元格中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="1376b-106">This function is used in the E cell in the NURBSTo geometry rows.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1376b-107">语法</span><span class="sxs-lookup"><span data-stu-id="1376b-107">Syntax</span></span>

<span data-ttu-id="1376b-108">NURBS (* * *knotLast* * *，* **度** *，* * *xType* * *，* * *yType* * *，* * *x1* * *，* * *y1* * *，* * *knot1* * *，* * *weight1* * *，...)</span><span class="sxs-lookup"><span data-stu-id="1376b-108">NURBS(** *knotLast* **, ** *degree* **, ** *xType* **, ** *yType* **, ** *x1* **, ** *y1* **, ** *knot1* **, ** *weight1* **, ...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1376b-109">参数</span><span class="sxs-lookup"><span data-stu-id="1376b-109">Parameters</span></span>

|<span data-ttu-id="1376b-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1376b-110">**Name**</span></span>|<span data-ttu-id="1376b-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1376b-111">**Required/Optional**</span></span>|<span data-ttu-id="1376b-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1376b-112">**Data Type**</span></span>|<span data-ttu-id="1376b-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1376b-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1376b-114">_knotLast_</span><span class="sxs-lookup"><span data-stu-id="1376b-114">_knotLast_</span></span> <br/> |<span data-ttu-id="1376b-115">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-115">Required</span></span>  <br/> |<span data-ttu-id="1376b-116">**string**</span><span class="sxs-lookup"><span data-stu-id="1376b-116">**string**</span></span> <br/> | <span data-ttu-id="1376b-117">最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="1376b-117">The last knot.</span></span>  <br/> |
| <span data-ttu-id="1376b-118">_度_</span><span class="sxs-lookup"><span data-stu-id="1376b-118">_degree_</span></span> <br/> |<span data-ttu-id="1376b-119">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-119">Required</span></span>  <br/> |<span data-ttu-id="1376b-120">**数字**</span><span class="sxs-lookup"><span data-stu-id="1376b-120">**Numeric**</span></span> <br/> |<span data-ttu-id="1376b-121">样条的度数。</span><span class="sxs-lookup"><span data-stu-id="1376b-121">The spline's degree.</span></span>  <br/> |
| <span data-ttu-id="1376b-122">_xType_</span><span class="sxs-lookup"><span data-stu-id="1376b-122">_xType_</span></span> <br/> |<span data-ttu-id="1376b-123">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-123">Required</span></span>  <br/> |<span data-ttu-id="1376b-124">**数字**</span><span class="sxs-lookup"><span data-stu-id="1376b-124">**Numeric**</span></span> <br/> |<span data-ttu-id="1376b-125">指定如何解释_x_输入的数据。</span><span class="sxs-lookup"><span data-stu-id="1376b-125">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="1376b-126">如果_xType_为 0，所有_x_输入的数据被都解释为宽度的百分比。</span><span class="sxs-lookup"><span data-stu-id="1376b-126">If  _xType_ is 0, all  _x_ input data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="1376b-127">如果_xType_为 1 时，所有_x_输入的数据被都解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="1376b-127">If  _xType_ is 1, all  _x_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="1376b-128">_yType_</span><span class="sxs-lookup"><span data-stu-id="1376b-128">_yType_</span></span> <br/> |<span data-ttu-id="1376b-129">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-129">Required</span></span>  <br/> |<span data-ttu-id="1376b-130">**数字**</span><span class="sxs-lookup"><span data-stu-id="1376b-130">**Numeric**</span></span> <br/> |<span data-ttu-id="1376b-131">指定如何解释_y_输入的数据。</span><span class="sxs-lookup"><span data-stu-id="1376b-131">Specifies how to interpret the  _y_ input data.</span></span> <span data-ttu-id="1376b-132">如果_yType_为 0，所有_y_输入的数据被都解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="1376b-132">If  _yType_ is 0, all  _y_ input data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="1376b-133">如果_yType_为 1 时，所有_y_输入的数据被都解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="1376b-133">If  _yType_ is 1, all  _y_ input data is interpreted as local coordinates.</span></span>  <br/> |
| <span data-ttu-id="1376b-134">_x1_</span><span class="sxs-lookup"><span data-stu-id="1376b-134">_x1_</span></span> <br/> |<span data-ttu-id="1376b-135">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-135">Required</span></span>  <br/> |<span data-ttu-id="1376b-136">**字符串**</span><span class="sxs-lookup"><span data-stu-id="1376b-136">**String**</span></span> <br/> |<span data-ttu-id="1376b-137">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="1376b-137">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="1376b-138">_y1_</span><span class="sxs-lookup"><span data-stu-id="1376b-138">_y1_</span></span> <br/> |<span data-ttu-id="1376b-139">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-139">Required</span></span>  <br/> |<span data-ttu-id="1376b-140">**字符串**</span><span class="sxs-lookup"><span data-stu-id="1376b-140">**String**</span></span> <br/> |<span data-ttu-id="1376b-141">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="1376b-141">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="1376b-142">_knot1_</span><span class="sxs-lookup"><span data-stu-id="1376b-142">_knot1_</span></span> <br/> |<span data-ttu-id="1376b-143">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-143">Required</span></span>  <br/> |<span data-ttu-id="1376b-144">**字符串**</span><span class="sxs-lookup"><span data-stu-id="1376b-144">**String**</span></span> <br/> |<span data-ttu-id="1376b-145">B 样条上的节点。</span><span class="sxs-lookup"><span data-stu-id="1376b-145">A knot on the B-spline.</span></span>  <br/> |
| <span data-ttu-id="1376b-146">_weight1_</span><span class="sxs-lookup"><span data-stu-id="1376b-146">_weight1_</span></span> <br/> |<span data-ttu-id="1376b-147">必需</span><span class="sxs-lookup"><span data-stu-id="1376b-147">Required</span></span>  <br/> |<span data-ttu-id="1376b-148">**字符串**</span><span class="sxs-lookup"><span data-stu-id="1376b-148">**String**</span></span> <br/> |<span data-ttu-id="1376b-149">B 样条的粗细。</span><span class="sxs-lookup"><span data-stu-id="1376b-149">A weight on the B-spline.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1376b-150">注解</span><span class="sxs-lookup"><span data-stu-id="1376b-150">Remarks</span></span>

<span data-ttu-id="1376b-151">对于每一个*x*参数，必须有一个*y*参数;否则，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1376b-151">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
<span data-ttu-id="1376b-152">必须指定至少一个*x*、 *y*、*节点*和*weight*参数;否则，Visio 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="1376b-152">You must specify at least one  *x*, *y*, *knot*  , and  *weight*  argument; otherwise, Visio returns an error.</span></span> 
  

