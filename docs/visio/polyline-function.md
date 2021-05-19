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
description: 返回折线。 此函数用于 PolyLineTo 几何图形行的 A 单元格。
ms.openlocfilehash: d801c6f2c1a81cc5cc99b3517c4d86784421d7e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426294"
---
# <a name="polyline-function"></a><span data-ttu-id="f00a6-104">POLYLINE 函数</span><span class="sxs-lookup"><span data-stu-id="f00a6-104">POLYLINE Function</span></span>

<span data-ttu-id="f00a6-105">返回折线。</span><span class="sxs-lookup"><span data-stu-id="f00a6-105">Returns a polyline.</span></span> <span data-ttu-id="f00a6-106">此函数用于 PolyLineTo 几何图形行的 A 单元格。</span><span class="sxs-lookup"><span data-stu-id="f00a6-106">This function is used in the A cell of PolyLineTo geometry rows.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f00a6-107">语法</span><span class="sxs-lookup"><span data-stu-id="f00a6-107">Syntax</span></span>

<span data-ttu-id="f00a6-108">POLYLINE (\*\* *xType* \*\*， \*\* *yType* \*\*， \*\* *x1* \*\*， \*\* *y1* \*\*...) </span><span class="sxs-lookup"><span data-stu-id="f00a6-108">POLYLINE(\*\* *xType* \*\*, \*\* *yType* \*\*, \*\* *x1* \*\*, \*\* *y1* \*\*...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f00a6-109">参数</span><span class="sxs-lookup"><span data-stu-id="f00a6-109">Parameters</span></span>

|<span data-ttu-id="f00a6-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="f00a6-110">**Name**</span></span>|<span data-ttu-id="f00a6-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f00a6-111">**Required/Optional**</span></span>|<span data-ttu-id="f00a6-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f00a6-112">**Data Type**</span></span>|<span data-ttu-id="f00a6-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="f00a6-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f00a6-114">_xType_</span><span class="sxs-lookup"><span data-stu-id="f00a6-114">_xType_</span></span> <br/> |<span data-ttu-id="f00a6-115">必需</span><span class="sxs-lookup"><span data-stu-id="f00a6-115">Required</span></span>  <br/> |<span data-ttu-id="f00a6-116">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="f00a6-116">**Boolean**</span></span> <br/> |<span data-ttu-id="f00a6-117">指定如何解释 x  _输入_ 数据。</span><span class="sxs-lookup"><span data-stu-id="f00a6-117">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="f00a6-118">如果  _xType_ 为 0，则  _输入 x_-data 将被解释为 Width 的百分比。</span><span class="sxs-lookup"><span data-stu-id="f00a6-118">If  _xType_ is 0, the input  _x_-data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="f00a6-119">如果  _xType_ 为 1，则  _输入 x_-data 将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="f00a6-119">If  _xType_ is 1, the input  _x_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="f00a6-120">_yType_</span><span class="sxs-lookup"><span data-stu-id="f00a6-120">_yType_</span></span> <br/> |<span data-ttu-id="f00a6-121">必需</span><span class="sxs-lookup"><span data-stu-id="f00a6-121">Required</span></span>  <br/> |<span data-ttu-id="f00a6-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="f00a6-122">**Boolean**</span></span> <br/> |<span data-ttu-id="f00a6-123">指定如何解释  _y_-input 数据。</span><span class="sxs-lookup"><span data-stu-id="f00a6-123">Specifies how to interpret the  _y_-input data.</span></span> <span data-ttu-id="f00a6-124">如果  _yType_ 为 0，则  _输入的 y_-data 将被解释为 Height 的百分比。</span><span class="sxs-lookup"><span data-stu-id="f00a6-124">If  _yType_ is 0, the input  _y_-data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="f00a6-125">如果  _yType_ 为 1，则  _输入的 y_-data 将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="f00a6-125">If  _yType_ is 1, the input  _y_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="f00a6-126">_x1_</span><span class="sxs-lookup"><span data-stu-id="f00a6-126">_x1_</span></span> <br/> |<span data-ttu-id="f00a6-127">必需</span><span class="sxs-lookup"><span data-stu-id="f00a6-127">Required</span></span>  <br/> |<span data-ttu-id="f00a6-128">**Number**</span><span class="sxs-lookup"><span data-stu-id="f00a6-128">**Number**</span></span> <br/> | <span data-ttu-id="f00a6-129">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="f00a6-129">An  _x_-coordinate.</span></span>  <br/> |
| <span data-ttu-id="f00a6-130">_y1_</span><span class="sxs-lookup"><span data-stu-id="f00a6-130">_y1_</span></span> <br/> |<span data-ttu-id="f00a6-131">必需</span><span class="sxs-lookup"><span data-stu-id="f00a6-131">Required</span></span>  <br/> |<span data-ttu-id="f00a6-132">**Number**</span><span class="sxs-lookup"><span data-stu-id="f00a6-132">**Number**</span></span> <br/> |<span data-ttu-id="f00a6-133">_y_ 坐标。</span><span class="sxs-lookup"><span data-stu-id="f00a6-133">A  _y_-coordinate.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f00a6-134">备注</span><span class="sxs-lookup"><span data-stu-id="f00a6-134">Remarks</span></span>

<span data-ttu-id="f00a6-135">对于每个  *x*  参数，都必须有  *一个 y*  参数;否则，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="f00a6-135">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f00a6-136">示例</span><span class="sxs-lookup"><span data-stu-id="f00a6-136">Example</span></span>

<span data-ttu-id="f00a6-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="f00a6-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span></span> 
  
<span data-ttu-id="f00a6-138">返回大小为宽 x 高的矩形。</span><span class="sxs-lookup"><span data-stu-id="f00a6-138">Returns a rectangle of dimensions Width x Height.</span></span> 
  

