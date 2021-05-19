---
title: RECTSECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251486
localization_priority: Normal
ms.assetid: e83343c5-df5f-bf74-f854-6380176693a2
description: 计算与 x 和 y 相关联的矩形的扇区，并返回一个 0 到 4 的整数，指示扇区。
ms.openlocfilehash: 442ec0d614589c709a097ba314abad044d470df6
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160270"
---
# <a name="rectsect-function"></a><span data-ttu-id="ca298-103">RECTSECT 函数</span><span class="sxs-lookup"><span data-stu-id="ca298-103">RECTSECT Function</span></span>

<span data-ttu-id="ca298-104">计算与  *x*  和  *y*  相关联的矩形的扇区，并返回一个 0 到 4 的整数，指示扇区。</span><span class="sxs-lookup"><span data-stu-id="ca298-104">Calculates the sector of a rectangle associated with  *x*  and  *y*  and returns an integer 0 to 4, indicating the sector.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ca298-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca298-105">Syntax</span></span>

<span data-ttu-id="ca298-106">RECTSECT (***width***、 ***height***、 ***x***、 ***y***、 ***option )***</span><span class="sxs-lookup"><span data-stu-id="ca298-106">RECTSECT(***width***, ***height***, ***x***, ***y***, ***option*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ca298-107">参数</span><span class="sxs-lookup"><span data-stu-id="ca298-107">Parameters</span></span>

|<span data-ttu-id="ca298-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ca298-108">**Name**</span></span>|<span data-ttu-id="ca298-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ca298-109">**Required/Optional**</span></span>|<span data-ttu-id="ca298-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ca298-110">**Data Type**</span></span>|<span data-ttu-id="ca298-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ca298-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ca298-112">_width_</span><span class="sxs-lookup"><span data-stu-id="ca298-112">_width_</span></span> <br/> |<span data-ttu-id="ca298-113">必需</span><span class="sxs-lookup"><span data-stu-id="ca298-113">Required</span></span>  <br/> |<span data-ttu-id="ca298-114">**String**</span><span class="sxs-lookup"><span data-stu-id="ca298-114">**String**</span></span> <br/> |<span data-ttu-id="ca298-115">矩形的宽度。</span><span class="sxs-lookup"><span data-stu-id="ca298-115">Width of the rectangle.</span></span>  <br/> |
| <span data-ttu-id="ca298-116">_height_</span><span class="sxs-lookup"><span data-stu-id="ca298-116">_height_</span></span> <br/> |<span data-ttu-id="ca298-117">必需</span><span class="sxs-lookup"><span data-stu-id="ca298-117">Required</span></span>  <br/> |<span data-ttu-id="ca298-118">**String**</span><span class="sxs-lookup"><span data-stu-id="ca298-118">**String**</span></span> <br/> |<span data-ttu-id="ca298-119">矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="ca298-119">Height of the rectangle.</span></span>  <br/> |
| <span data-ttu-id="ca298-120">_x_</span><span class="sxs-lookup"><span data-stu-id="ca298-120">_x_</span></span> <br/> |<span data-ttu-id="ca298-121">必需</span><span class="sxs-lookup"><span data-stu-id="ca298-121">Required</span></span>  <br/> |<span data-ttu-id="ca298-122">**String**</span><span class="sxs-lookup"><span data-stu-id="ca298-122">**String**</span></span> <br/> |<span data-ttu-id="ca298-123">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="ca298-123">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="ca298-124">_y_</span><span class="sxs-lookup"><span data-stu-id="ca298-124">_y_</span></span> <br/> |<span data-ttu-id="ca298-125">必需</span><span class="sxs-lookup"><span data-stu-id="ca298-125">Required</span></span>  <br/> |<span data-ttu-id="ca298-126">**String**</span><span class="sxs-lookup"><span data-stu-id="ca298-126">**String**</span></span> <br/> |<span data-ttu-id="ca298-127">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="ca298-127">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="ca298-128">_option_</span><span class="sxs-lookup"><span data-stu-id="ca298-128">_option_</span></span> <br/> |<span data-ttu-id="ca298-129">必需</span><span class="sxs-lookup"><span data-stu-id="ca298-129">Required</span></span>  <br/> |<span data-ttu-id="ca298-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="ca298-130">**Boolean**</span></span> <br/> |<span data-ttu-id="ca298-p101">指定如何处理对角线上的点。将该值设置为 0，表示将左右部分用作对角线上的点。将该值设置为 1，表示将上下部分用作对角线上的点。</span><span class="sxs-lookup"><span data-stu-id="ca298-p101">Specifies how points that fall on the diagonals are treated. Set the value to 0 to use the left and right sectors for points on a diagonal. Set the value to 1 to use the top and bottom sectors for points on a diagonal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca298-134">备注</span><span class="sxs-lookup"><span data-stu-id="ca298-134">Remarks</span></span>

<span data-ttu-id="ca298-135">请考虑具有宽度和高度的矩形，以及 (*x，y*) 矩形中心点的点。</span><span class="sxs-lookup"><span data-stu-id="ca298-135">Consider a rectangle that has a  *width*  and a  *height*  , and a point (*x,y*) from the center point of the rectangle.</span></span> <span data-ttu-id="ca298-136">绘出矩形的对角线，从而将矩形划分为四个部分和一个中心点。</span><span class="sxs-lookup"><span data-stu-id="ca298-136">Draw diagonal lines through the corners of the rectangle to divide it into four sectors and a center point.</span></span> <span data-ttu-id="ca298-137">0 到 4 部分分别代表中心点、右、上、左和下。</span><span class="sxs-lookup"><span data-stu-id="ca298-137">The sectors 0 through 4 represent the center-point, right, top, left, and bottom respectively.</span></span> 
  
![扇区 0 到 4 分别表示中心点、右、上、左和下](media/ShpSheetRef_CA_03_ZA07645862.gif)
  
## <a name="example"></a><span data-ttu-id="ca298-139">示例</span><span class="sxs-lookup"><span data-stu-id="ca298-139">Example</span></span>

<span data-ttu-id="ca298-140">RECTSECT(1 in, 2 in, 1 in, -7 in, 0)</span><span class="sxs-lookup"><span data-stu-id="ca298-140">RECTSECT(1 in, 2 in, 1 in, -7 in, 0)</span></span> 
  
<span data-ttu-id="ca298-141">返回 4。</span><span class="sxs-lookup"><span data-stu-id="ca298-141">Returns 4.</span></span> 
  

