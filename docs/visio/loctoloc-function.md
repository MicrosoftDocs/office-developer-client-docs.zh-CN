---
title: LOCTOLOC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251586
localization_priority: Normal
ms.assetid: 1f09482a-0b1b-1bef-bc23-7f7793c4c65f
description: 返回目标坐标系中的本地坐标中转换的点。
ms.openlocfilehash: f08feb6137c3022027d19b45f06285fb8b6441a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427484"
---
# <a name="loctoloc-function"></a><span data-ttu-id="f22b9-103">LOCTOLOC 函数</span><span class="sxs-lookup"><span data-stu-id="f22b9-103">LOCTOLOC Function</span></span>

<span data-ttu-id="f22b9-104">返回目标坐标系中的本地坐标中转换的点。</span><span class="sxs-lookup"><span data-stu-id="f22b9-104">Returns a transformed point in local coordinates in the destination coordinate system.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f22b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="f22b9-105">Syntax</span></span>

<span data-ttu-id="f22b9-106">LOCTOLOC (\* \* *srcPoint* \* \*, \* \* *srcRef* \* \*, \* \* *dstRef* \* \*)</span><span class="sxs-lookup"><span data-stu-id="f22b9-106">LOCTOLOC(\*\* *srcPoint* \*\*, \*\* *srcRef* \*\*, \*\* *dstRef* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f22b9-107">参数</span><span class="sxs-lookup"><span data-stu-id="f22b9-107">Parameters</span></span>

|<span data-ttu-id="f22b9-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f22b9-108">**Name**</span></span>|<span data-ttu-id="f22b9-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f22b9-109">**Required/Optional**</span></span>|<span data-ttu-id="f22b9-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f22b9-110">**Data Type**</span></span>|<span data-ttu-id="f22b9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f22b9-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f22b9-112">_srcPoint_</span><span class="sxs-lookup"><span data-stu-id="f22b9-112">_srcPoint_</span></span> <br/> |<span data-ttu-id="f22b9-113">必需</span><span class="sxs-lookup"><span data-stu-id="f22b9-113">Required</span></span>  <br/> |<span data-ttu-id="f22b9-114">**String**</span><span class="sxs-lookup"><span data-stu-id="f22b9-114">**String**</span></span> <br/> | <span data-ttu-id="f22b9-115">用源坐标系中的本地坐标表示的点。</span><span class="sxs-lookup"><span data-stu-id="f22b9-115">A point in local coordinates in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="f22b9-116">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="f22b9-116">_srcRef_</span></span> <br/> |<span data-ttu-id="f22b9-117">必需</span><span class="sxs-lookup"><span data-stu-id="f22b9-117">Required</span></span>  <br/> |<span data-ttu-id="f22b9-118">**String**</span><span class="sxs-lookup"><span data-stu-id="f22b9-118">**String**</span></span> <br/> | <span data-ttu-id="f22b9-119">对源对象中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f22b9-119">A reference to a cell in the source object.</span></span>  <br/> |
| <span data-ttu-id="f22b9-120">_dstRef_</span><span class="sxs-lookup"><span data-stu-id="f22b9-120">_dstRef_</span></span> <br/> |<span data-ttu-id="f22b9-121">必需</span><span class="sxs-lookup"><span data-stu-id="f22b9-121">Required</span></span>  <br/> |<span data-ttu-id="f22b9-122">**String**</span><span class="sxs-lookup"><span data-stu-id="f22b9-122">**String**</span></span> <br/> | <span data-ttu-id="f22b9-123">对目标对象中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="f22b9-123">A reference to a cell in the destination object.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f22b9-124">返回值</span><span class="sxs-lookup"><span data-stu-id="f22b9-124">Return value</span></span>

<span data-ttu-id="f22b9-125">String</span><span class="sxs-lookup"><span data-stu-id="f22b9-125">String</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f22b9-126">说明</span><span class="sxs-lookup"><span data-stu-id="f22b9-126">Remarks</span></span>

<span data-ttu-id="f22b9-p101">LOCTOLOC 函数将用源形状中的本地坐标表示的点转换用目标形状中的本地坐标表示的点。您可以使用此函数构造一个形状，例如，依据距离另一个坐标空间的点。您还可以使用此函数将本地点转换为页坐标，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f22b9-p101">The LOCTOLOC function converts a point from local coordinates in a source shape to local coordinates in a destination shape. You can use this function to construct a shape, for example, in terms of a point from another coordinate space. You can also use this function to transform a local point to page coordinates, or vice versa.</span></span>
  
<span data-ttu-id="f22b9-p102">即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。</span><span class="sxs-lookup"><span data-stu-id="f22b9-p102">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span>
  
<span data-ttu-id="f22b9-132">源坐标和目标坐标必须位于同一页上。</span><span class="sxs-lookup"><span data-stu-id="f22b9-132">The source and destination coordinates must be on the same page.</span></span>
  
## <a name="example"></a><span data-ttu-id="f22b9-133">示例</span><span class="sxs-lookup"><span data-stu-id="f22b9-133">Example</span></span>

<span data-ttu-id="f22b9-134">下面的公式将与公式相关联的形状的本地旋转中心点转换为页上的点。</span><span class="sxs-lookup"><span data-stu-id="f22b9-134">The following formula converts the local pin of the shape associated with the formula to a point on the page.</span></span>
  
```vb
LOCTOLOC(PNT(LocPinX, LocPinY), Width, ThePage!PageWidth)
```


