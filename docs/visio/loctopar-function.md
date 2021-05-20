---
title: LOCTOPAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251585
localization_priority: Normal
ms.assetid: ce1028d6-0293-e8dd-b79d-3f02c50f6250
description: 返回目标坐标系中父坐标中的转换点。
ms.openlocfilehash: 65a08837d7d026836ebc8d5e35938ea049d005e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439980"
---
# <a name="loctopar-function"></a><span data-ttu-id="ec1a0-103">LOCTOPAR 函数</span><span class="sxs-lookup"><span data-stu-id="ec1a0-103">LOCTOPAR Function</span></span>

<span data-ttu-id="ec1a0-104">返回目标坐标系中父坐标中的转换点。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-104">Returns a transformed point in parent coordinates in the destination coordinate system.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="ec1a0-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec1a0-105">Syntax</span></span>

<span data-ttu-id="ec1a0-106">LOCTOPAR (\*\* *srcPoint* \*\*， \*\* *srcRef* \*\*， \*\* *dstRef* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="ec1a0-106">LOCTOPAR(\*\* *srcPoint* \*\*, \*\* *srcRef* \*\*, \*\* *dstRef* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ec1a0-107">参数</span><span class="sxs-lookup"><span data-stu-id="ec1a0-107">Parameters</span></span>

|<span data-ttu-id="ec1a0-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-108">**Name**</span></span>|<span data-ttu-id="ec1a0-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-109">**Required/Optional**</span></span>|<span data-ttu-id="ec1a0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-110">**Data Type**</span></span>|<span data-ttu-id="ec1a0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ec1a0-112">_srcPoint_</span><span class="sxs-lookup"><span data-stu-id="ec1a0-112">_srcPoint_</span></span> <br/> |<span data-ttu-id="ec1a0-113">必需</span><span class="sxs-lookup"><span data-stu-id="ec1a0-113">Required</span></span>  <br/> |<span data-ttu-id="ec1a0-114">**String**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-114">**String**</span></span> <br/> | <span data-ttu-id="ec1a0-115">用源坐标系中的本地坐标表示的点。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-115">A point in local coordinates in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="ec1a0-116">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="ec1a0-116">_srcRef_</span></span> <br/> |<span data-ttu-id="ec1a0-117">必需</span><span class="sxs-lookup"><span data-stu-id="ec1a0-117">Required</span></span>  <br/> |<span data-ttu-id="ec1a0-118">**String**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-118">**String**</span></span> <br/> | <span data-ttu-id="ec1a0-119">对源对象中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-119">A reference to a cell in the source object.</span></span>  <br/> |
| <span data-ttu-id="ec1a0-120">_dstRef_</span><span class="sxs-lookup"><span data-stu-id="ec1a0-120">_dstRef_</span></span> <br/> |<span data-ttu-id="ec1a0-121">必需</span><span class="sxs-lookup"><span data-stu-id="ec1a0-121">Required</span></span>  <br/> |<span data-ttu-id="ec1a0-122">**String**</span><span class="sxs-lookup"><span data-stu-id="ec1a0-122">**String**</span></span> <br/> | <span data-ttu-id="ec1a0-123">对目标对象中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-123">A reference to a cell in the destination object.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="ec1a0-124">返回值</span><span class="sxs-lookup"><span data-stu-id="ec1a0-124">Return value</span></span>

<span data-ttu-id="ec1a0-125">String</span><span class="sxs-lookup"><span data-stu-id="ec1a0-125">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ec1a0-126">备注</span><span class="sxs-lookup"><span data-stu-id="ec1a0-126">Remarks</span></span>

<span data-ttu-id="ec1a0-p101">将用源形状中的本地坐标表示的点转换为用目标形状中的父坐标表示的点。您可以使用另一个坐标系中的另一个点，通过 LOCTOPAR 函数在单元格中设置父坐标，如形状中的 PinX、PinY、BeginX 和 BeginY。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-p101">Converts a point from local coordinates in a source shape to parent coordinates in a destination shape. You can use the LOCTOPAR function to set parent coordinates in cells, such as PinX, PinY, BeginX, and BeginY in a shape using another point from another coordinate system.</span></span> 
  
<span data-ttu-id="ec1a0-p102">即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-p102">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span> 
  
<span data-ttu-id="ec1a0-131">源坐标和目标坐标必须位于同一页上。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-131">The source and destination coordinates must be on the same page.</span></span> 
  
<span data-ttu-id="ec1a0-132">如果目标是没有父项的页，则将用该页的本地坐标表示结果。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-132">If the destination is a page, which has no parent, the result is expressed in the page's local coordinates.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ec1a0-133">示例</span><span class="sxs-lookup"><span data-stu-id="ec1a0-133">Example</span></span>

<span data-ttu-id="ec1a0-134">LOCTOPAR(PNT(LocPinX, LocPinY), Width, Sheet.4!Width)</span><span class="sxs-lookup"><span data-stu-id="ec1a0-134">LOCTOPAR(PNT(LocPinX, LocPinY), Width, Sheet.4!Width)</span></span> 
  
<span data-ttu-id="ec1a0-135">将与公式相关联的形状的本地旋转中心点转换为 Sheet.4 的父坐标。</span><span class="sxs-lookup"><span data-stu-id="ec1a0-135">Converts the local pin of the shape associated with the formula to parent coordinates of Sheet.4.</span></span> 
  

