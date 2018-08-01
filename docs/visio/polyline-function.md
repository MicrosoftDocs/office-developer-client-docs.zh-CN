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
description: 返回折线。 PolyLineTo geometry 行的一个单元格中使用此函数。
ms.openlocfilehash: afe31b3963cca03d0273b8768f6cc5538d1850ee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780881"
---
# <a name="polyline-function"></a><span data-ttu-id="0f0cf-104">POLYLINE 函数</span><span class="sxs-lookup"><span data-stu-id="0f0cf-104">POLYLINE Function</span></span>

<span data-ttu-id="0f0cf-105">返回折线。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-105">Returns a polyline.</span></span> <span data-ttu-id="0f0cf-106">PolyLineTo geometry 行的一个单元格中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-106">This function is used in the A cell of PolyLineTo geometry rows.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0f0cf-107">语法</span><span class="sxs-lookup"><span data-stu-id="0f0cf-107">Syntax</span></span>

<span data-ttu-id="0f0cf-108">折线 (* * *xType* * *，* * *yType* * *，* * *x1* * *，* * *y1* * *...)</span><span class="sxs-lookup"><span data-stu-id="0f0cf-108">POLYLINE(** *xType* **, ** *yType* **, ** *x1* **, ** *y1* **...)</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0f0cf-109">参数</span><span class="sxs-lookup"><span data-stu-id="0f0cf-109">Parameters</span></span>

|<span data-ttu-id="0f0cf-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-110">**Name**</span></span>|<span data-ttu-id="0f0cf-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-111">**Required/Optional**</span></span>|<span data-ttu-id="0f0cf-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-112">**Data Type**</span></span>|<span data-ttu-id="0f0cf-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0f0cf-114">_xType_</span><span class="sxs-lookup"><span data-stu-id="0f0cf-114">_xType_</span></span> <br/> |<span data-ttu-id="0f0cf-115">必需</span><span class="sxs-lookup"><span data-stu-id="0f0cf-115">Required</span></span>  <br/> |<span data-ttu-id="0f0cf-116">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-116">**Boolean**</span></span> <br/> |<span data-ttu-id="0f0cf-117">指定如何解释_x_输入的数据。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-117">Specifies how to interpret the  _x_ input data.</span></span> <span data-ttu-id="0f0cf-118">如果_xType_是 0，则输入的_x_-数据被解释为宽度的百分比。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-118">If  _xType_ is 0, the input  _x_-data is interpreted as a percentage of Width.</span></span> <span data-ttu-id="0f0cf-119">如果_xType_是 1，则输入的_x_的数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-119">If  _xType_ is 1, the input  _x_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="0f0cf-120">_yType_</span><span class="sxs-lookup"><span data-stu-id="0f0cf-120">_yType_</span></span> <br/> |<span data-ttu-id="0f0cf-121">必需</span><span class="sxs-lookup"><span data-stu-id="0f0cf-121">Required</span></span>  <br/> |<span data-ttu-id="0f0cf-122">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-122">**Boolean**</span></span> <br/> |<span data-ttu-id="0f0cf-123">指定如何解释_y_-输入数据。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-123">Specifies how to interpret the  _y_-input data.</span></span> <span data-ttu-id="0f0cf-124">如果_yType_为 0，输入_y_-数据被解释为高度的百分比。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-124">If  _yType_ is 0, the input  _y_-data is interpreted as a percentage of Height.</span></span> <span data-ttu-id="0f0cf-125">如果_yType_是 1，则输入_y_-数据将被解释为本地坐标。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-125">If  _yType_ is 1, the input  _y_-data is interpreted as a local coordinate.</span></span>  <br/> |
| <span data-ttu-id="0f0cf-126">_x1_</span><span class="sxs-lookup"><span data-stu-id="0f0cf-126">_x1_</span></span> <br/> |<span data-ttu-id="0f0cf-127">必需</span><span class="sxs-lookup"><span data-stu-id="0f0cf-127">Required</span></span>  <br/> |<span data-ttu-id="0f0cf-128">**编号**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-128">**Number**</span></span> <br/> | <span data-ttu-id="0f0cf-129">_X_-协调。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-129">An  _x_-coordinate.</span></span>  <br/> |
| <span data-ttu-id="0f0cf-130">_y1_</span><span class="sxs-lookup"><span data-stu-id="0f0cf-130">_y1_</span></span> <br/> |<span data-ttu-id="0f0cf-131">必需</span><span class="sxs-lookup"><span data-stu-id="0f0cf-131">Required</span></span>  <br/> |<span data-ttu-id="0f0cf-132">**编号**</span><span class="sxs-lookup"><span data-stu-id="0f0cf-132">**Number**</span></span> <br/> |<span data-ttu-id="0f0cf-133">_Y_-协调。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-133">A  _y_-coordinate.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0f0cf-134">说明</span><span class="sxs-lookup"><span data-stu-id="0f0cf-134">Remarks</span></span>

<span data-ttu-id="0f0cf-135">对于每一个*x*参数，必须有一个*y*参数;否则，将返回错误。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-135">For every  *x*  argument, there must be a  *y*  argument; otherwise, an error is returned.</span></span> 
  
## <a name="example"></a><span data-ttu-id="0f0cf-136">示例</span><span class="sxs-lookup"><span data-stu-id="0f0cf-136">Example</span></span>

<span data-ttu-id="0f0cf-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="0f0cf-137">POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0)</span></span> 
  
<span data-ttu-id="0f0cf-138">返回大小为宽 x 高的矩形。</span><span class="sxs-lookup"><span data-stu-id="0f0cf-138">Returns a rectangle of dimensions Width x Height.</span></span> 
  

