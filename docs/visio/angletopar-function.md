---
title: ANGLETOPAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253218
localization_priority: Normal
ms.assetid: 4d87313a-c09a-582c-04f4-d95800e3e9f2
description: 目标形状的父坐标系统中返回已转换的角度。 将源形状中的本地坐标表示角度转换到目标形状中的父坐标。
ms.openlocfilehash: 3a739c55d568dc548f8175b56f22e6ec4c28e4c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779654"
---
# <a name="angletopar-function"></a><span data-ttu-id="c81b2-104">ANGLETOPAR 函数</span><span class="sxs-lookup"><span data-stu-id="c81b2-104">ANGLETOPAR Function</span></span>

<span data-ttu-id="c81b2-105">目标形状的父坐标系统中返回已转换的角度。</span><span class="sxs-lookup"><span data-stu-id="c81b2-105">Returns a transformed angle in the destination shape's parent coordinate system.</span></span> <span data-ttu-id="c81b2-106">将源形状中的本地坐标表示角度转换到目标形状中的父坐标。</span><span class="sxs-lookup"><span data-stu-id="c81b2-106">Converts an angle from local coordinates in a source shape to the parent coordinates in a destination shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c81b2-107">语法</span><span class="sxs-lookup"><span data-stu-id="c81b2-107">Syntax</span></span>

<span data-ttu-id="c81b2-108">ANGLETOPAR (* * *srcAngle* * *，* * *srcRef* * *，* * *dstRef* * *)</span><span class="sxs-lookup"><span data-stu-id="c81b2-108">ANGLETOPAR(** *srcAngle* **, ** *srcRef* **, ** *dstRef* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c81b2-109">参数</span><span class="sxs-lookup"><span data-stu-id="c81b2-109">Parameters</span></span>

|<span data-ttu-id="c81b2-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="c81b2-110">**Name**</span></span>|<span data-ttu-id="c81b2-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c81b2-111">**Required/Optional**</span></span>|<span data-ttu-id="c81b2-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c81b2-112">**Data Type**</span></span>|<span data-ttu-id="c81b2-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="c81b2-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c81b2-114">_srcAngle_</span><span class="sxs-lookup"><span data-stu-id="c81b2-114">_srcAngle_</span></span> <br/> |<span data-ttu-id="c81b2-115">必需</span><span class="sxs-lookup"><span data-stu-id="c81b2-115">Required</span></span>  <br/> |<span data-ttu-id="c81b2-116">**数字**</span><span class="sxs-lookup"><span data-stu-id="c81b2-116">**Numeric**</span></span> <br/> |<span data-ttu-id="c81b2-117">源坐标系中的角度。</span><span class="sxs-lookup"><span data-stu-id="c81b2-117">An angle in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="c81b2-118">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="c81b2-118">_srcRef_</span></span> <br/> |<span data-ttu-id="c81b2-119">必需</span><span class="sxs-lookup"><span data-stu-id="c81b2-119">Required</span></span>  <br/> |<span data-ttu-id="c81b2-120">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c81b2-120">**String**</span></span> <br/> | <span data-ttu-id="c81b2-121">对源对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c81b2-121">A reference to a cell in the source object, such as a shape, group, page, and so on.</span></span>  <br/> |
| <span data-ttu-id="c81b2-122">_dstRef_</span><span class="sxs-lookup"><span data-stu-id="c81b2-122">_dstRef_</span></span> <br/> |<span data-ttu-id="c81b2-123">必需</span><span class="sxs-lookup"><span data-stu-id="c81b2-123">Required</span></span>  <br/> |<span data-ttu-id="c81b2-124">**字符串**</span><span class="sxs-lookup"><span data-stu-id="c81b2-124">**String**</span></span> <br/> |<span data-ttu-id="c81b2-125">对目标对象（如形状、组合、页等）中的单元格的引用。</span><span class="sxs-lookup"><span data-stu-id="c81b2-125">A reference to a cell in the destination object, such as a shape, group, page, and so on.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c81b2-126">注解</span><span class="sxs-lookup"><span data-stu-id="c81b2-126">Remarks</span></span>

<span data-ttu-id="c81b2-p103">即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。</span><span class="sxs-lookup"><span data-stu-id="c81b2-p103">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span>
  
<span data-ttu-id="c81b2-129">源坐标和目标坐标必须位于同一页上。</span><span class="sxs-lookup"><span data-stu-id="c81b2-129">The source and destination coordinates must be on the same page.</span></span>
  
<span data-ttu-id="c81b2-130">如果目标是没有父级的页，则将用页的本地坐标表示结果。</span><span class="sxs-lookup"><span data-stu-id="c81b2-130">If the destination is a page, which has no parent, the result is expressed in page's local coordinates.</span></span>
  
