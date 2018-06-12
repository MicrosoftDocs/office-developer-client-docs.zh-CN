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
description: 计算 x 相关联的矩形的扇区和 y，并返回一个整数 0 到 4，指示扇区。
ms.openlocfilehash: 1f35704cdb827c9c751f11593436c110755d7777
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781018"
---
# <a name="rectsect-function"></a><span data-ttu-id="6d7ec-103">RECTSECT 函数</span><span class="sxs-lookup"><span data-stu-id="6d7ec-103">RECTSECT Function</span></span>

<span data-ttu-id="6d7ec-104">计算矩形*x*和*y*相关联的扇区并返回一个指示扇区的整数 0 到 4。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-104">Calculates the sector of a rectangle associated with  *x*  and  *y*  and returns an integer 0 to 4, indicating the sector.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6d7ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="6d7ec-105">Syntax</span></span>

<span data-ttu-id="6d7ec-106">RECTSECT (* **宽度** *，* **高度** *，* * *x* * *，* * *y* * *，* **选项** *)</span><span class="sxs-lookup"><span data-stu-id="6d7ec-106">RECTSECT(** *width* **, ** *height* **, ** *x* **, ** *y* **, ** *option* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="6d7ec-107">参数</span><span class="sxs-lookup"><span data-stu-id="6d7ec-107">Parameters</span></span>

|<span data-ttu-id="6d7ec-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-108">**Name**</span></span>|<span data-ttu-id="6d7ec-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-109">**Required/Optional**</span></span>|<span data-ttu-id="6d7ec-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-110">**Data Type**</span></span>|<span data-ttu-id="6d7ec-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6d7ec-112">_width_</span><span class="sxs-lookup"><span data-stu-id="6d7ec-112">_width_</span></span> <br/> |<span data-ttu-id="6d7ec-113">必需</span><span class="sxs-lookup"><span data-stu-id="6d7ec-113">Required</span></span>  <br/> |<span data-ttu-id="6d7ec-114">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-114">**String**</span></span> <br/> |<span data-ttu-id="6d7ec-115">矩形的宽度。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-115">Width of the rectangle.</span></span>  <br/> |
| <span data-ttu-id="6d7ec-116">_height_</span><span class="sxs-lookup"><span data-stu-id="6d7ec-116">_height_</span></span> <br/> |<span data-ttu-id="6d7ec-117">必需</span><span class="sxs-lookup"><span data-stu-id="6d7ec-117">Required</span></span>  <br/> |<span data-ttu-id="6d7ec-118">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-118">**String**</span></span> <br/> |<span data-ttu-id="6d7ec-119">矩形的高度。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-119">Height of the rectangle.</span></span>  <br/> |
| <span data-ttu-id="6d7ec-120">_x_</span><span class="sxs-lookup"><span data-stu-id="6d7ec-120">_x_</span></span> <br/> |<span data-ttu-id="6d7ec-121">必需</span><span class="sxs-lookup"><span data-stu-id="6d7ec-121">Required</span></span>  <br/> |<span data-ttu-id="6d7ec-122">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-122">**String**</span></span> <br/> |<span data-ttu-id="6d7ec-123">x 坐标。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-123">An x-coordinate.</span></span>  <br/> |
| <span data-ttu-id="6d7ec-124">_y_</span><span class="sxs-lookup"><span data-stu-id="6d7ec-124">_y_</span></span> <br/> |<span data-ttu-id="6d7ec-125">必需</span><span class="sxs-lookup"><span data-stu-id="6d7ec-125">Required</span></span>  <br/> |<span data-ttu-id="6d7ec-126">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-126">**String**</span></span> <br/> |<span data-ttu-id="6d7ec-127">y 坐标。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-127">A y-coordinate.</span></span>  <br/> |
| <span data-ttu-id="6d7ec-128">_选项_</span><span class="sxs-lookup"><span data-stu-id="6d7ec-128">_option_</span></span> <br/> |<span data-ttu-id="6d7ec-129">必需</span><span class="sxs-lookup"><span data-stu-id="6d7ec-129">Required</span></span>  <br/> |<span data-ttu-id="6d7ec-130">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="6d7ec-130">**Boolean**</span></span> <br/> |<span data-ttu-id="6d7ec-p101">指定如何处理对角线上的点。将该值设置为 0，表示将左右部分用作对角线上的点。将该值设置为 1，表示将上下部分用作对角线上的点。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-p101">Specifies how points that fall on the diagonals are treated. Set the value to 0 to use the left and right sectors for points on a diagonal. Set the value to 1 to use the top and bottom sectors for points on a diagonal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6d7ec-134">注解</span><span class="sxs-lookup"><span data-stu-id="6d7ec-134">Remarks</span></span>

<span data-ttu-id="6d7ec-135">请考虑矩形的*宽度*和*高度*，从该矩形的中心点点 （*x，y*）。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-135">Consider a rectangle that has a  *width*  and a  *height*  , and a point (*x,y*) from the center point of the rectangle.</span></span> <span data-ttu-id="6d7ec-136">绘制通过要划分为四个部分和中心点的矩形的对角线。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-136">Draw diagonal lines through the corners of the rectangle to divide it into four sectors and a center point.</span></span> <span data-ttu-id="6d7ec-137">扇区 0 到 4 表示中心点、 右、 top、 左，并分别下。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-137">The sectors 0 through 4 represent the center-point, right, top, left, and bottom respectively.</span></span> 
  
![](media/ShpSheetRef_CA_03_ZA07645862.gif)
  
## <a name="example"></a><span data-ttu-id="6d7ec-138">示例</span><span class="sxs-lookup"><span data-stu-id="6d7ec-138">Example</span></span>

<span data-ttu-id="6d7ec-139">RECTSECT(1 in, 2 in, 1 in, -7 in, 0)</span><span class="sxs-lookup"><span data-stu-id="6d7ec-139">RECTSECT(1 in, 2 in, 1 in, -7 in, 0)</span></span> 
  
<span data-ttu-id="6d7ec-140">返回 4。</span><span class="sxs-lookup"><span data-stu-id="6d7ec-140">Returns 4.</span></span> 
  

