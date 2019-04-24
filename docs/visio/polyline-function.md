---
title: POLYLINE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251576
localization_priority: Normal
ms.assetid: 10baeec9-6c9b-b4ba-3138-7d1156a9e056
description: 返回一个折线。 此函数用于 PolyLineTo 几何图形行的的一个单元格。
ms.openlocfilehash: d801c6f2c1a81cc5cc99b3517c4d86784421d7e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348276"
---
# <a name="polyline-function"></a><span data-ttu-id="f4e31-104">POLYLINE 函数</span><span class="sxs-lookup"><span data-stu-id="f4e31-104">POLYLINE Function</span></span>

<span data-ttu-id="f4e31-105">返回一个折线。</span><span class="sxs-lookup"><span data-stu-id="f4e31-105">Returns a polyline.</span></span> <span data-ttu-id="f4e31-106">此函数用于 PolyLineTo 几何图形行的的一个单元格。</span><span class="sxs-lookup"><span data-stu-id="f4e31-106">This function is used in the A cell of PolyLineTo geometry rows.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f4e31-107">语法</span><span class="sxs-lookup"><span data-stu-id="f4e31-107">Syntax</span></span>

<span data-ttu-id="f4e31-108">折线 (\* \* *xType* \* \*, \* \* *yType* \* \*, \* \* \*\* , \* \*, \* \* *y1* \* \* ...)</span><span class="sxs-lookup"><span data-stu-id="f4e31-108">POLYLINE(\*\* *xType* \*\*, \*\* *yType* \*\*, \*\* *x1* \*\*, \*\* *y1* \*\*...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f4e31-109">参数</span><span class="sxs-lookup"><span data-stu-id="f4e31-109">Parameters</span></span>

|<span data-ttu-id="f4e31-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="f4e31-110">**Name**</span></span>|<span data-ttu-id="f4e31-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f4e31-111">**Required/Optional**</span></span>|<span data-ttu-id="f4e31-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f4e31-112">**Data Type**</span></span>|<span data-ttu-id="f4e31-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4e31-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f4e31-114">_xType_</span><span class="sxs-lookup"><span data-stu-id="f4e31-114">_xType_</span></span> <br/> |<span data-ttu-id="f4e31-115">必需</span><span class="sxs-lookup"><span data-stu-id="f4e31-115">Required</span></span>  <br/> |<span data-ttu-id="f4e31-116">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="f4e31-116">**Boolean**</span></span> <br/> |<span data-ttu-id="f4e31-117">指定如何解释_x_输入数据。</span><span class="sxs-lookup"><span data-stu-id="f4e31-117">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="f4e31-118">如果_xType_为 0, 则输入的_x_数据将被解释为宽度的百分比。</span><span class="sxs-lookup"><span data-stu-id="f4e31-118">If  _xType_ is 0, the input  _x_-data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="f4e31-119">如果_xType_为 1, 则输入的_x_数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="f4e31-119">If  _xType_ is 1, the input  _x_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="f4e31-120">_yType_</span><span class="sxs-lookup"><span data-stu-id="f4e31-120">_yType_</span></span> <br/> |<span data-ttu-id="f4e31-121">必需</span><span class="sxs-lookup"><span data-stu-id="f4e31-121">Required</span></span>  <br/> |<span data-ttu-id="f4e31-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="f4e31-122">**Boolean**</span></span> <br/> |<span data-ttu-id="f4e31-123">指定如何解释_y_输入数据。</span><span class="sxs-lookup"><span data-stu-id="f4e31-123">Specifies how to interpret the  _y_-input data.</span></span> <span data-ttu-id="f4e31-124">如果_yType_为 0, 则输入的_y_数据将被解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="f4e31-124">If  _yType_ is 0, the input  _y_-data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="f4e31-125">如果_yType_为 1, 则输入的_y_数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="f4e31-125">If  _yType_ is 1, the input  _y_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="f4e31-126">_x1_</span><span class="sxs-lookup"><span data-stu-id="f4e31-126">_x1_</span></span> <br/> |<span data-ttu-id="f4e31-127">必需</span><span class="sxs-lookup"><span data-stu-id="f4e31-127">Required</span></span>  <br/> |<span data-ttu-id="f4e31-128">**Number**</span><span class="sxs-lookup"><span data-stu-id="f4e31-128">**Number**</span></span> <br/> | <span data-ttu-id="f4e31-129">_x_轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="f4e31-129">An  _x_-coordinate.</span></span>  <br/> |
| <span data-ttu-id="f4e31-130">_y1_</span><span class="sxs-lookup"><span data-stu-id="f4e31-130">_y1_</span></span> <br/> |<span data-ttu-id="f4e31-131">必需</span><span class="sxs-lookup"><span data-stu-id="f4e31-131">Required</span></span>  <br/> |<span data-ttu-id="f4e31-132">**Number**</span><span class="sxs-lookup"><span data-stu-id="f4e31-132">**Number**</span></span> <br/> |<span data-ttu-id="f4e31-133">_y_轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="f4e31-133">A  _y_-coordinate.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f4e31-134">注解</span><span class="sxs-lookup"><span data-stu-id="f4e31-134">Remarks</span></span>

<span data-ttu-id="f4e31-135">对于每个*x*参数, 必须有一个*y*参数;否则, 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="f4e31-135">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f4e31-136">示例</span><span class="sxs-lookup"><span data-stu-id="f4e31-136">Example</span></span>

<span data-ttu-id="f4e31-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="f4e31-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span></span> 
  
<span data-ttu-id="f4e31-138">返回大小为宽 x 高的矩形。</span><span class="sxs-lookup"><span data-stu-id="f4e31-138">Returns a rectangle of dimensions Width x Height.</span></span> 
  

