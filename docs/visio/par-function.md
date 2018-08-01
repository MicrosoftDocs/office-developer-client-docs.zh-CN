---
title: PAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251477
localization_priority: Normal
ms.assetid: 9caf424d-cb70-8f1a-b984-64cf776bdfb4
description: 返回形状的父级的坐标系统中的 x，某一点的 y 坐标。
ms.openlocfilehash: a3f7afd3f9bc988a20526451a6d7d7081d27a2d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780844"
---
# <a name="par-function"></a><span data-ttu-id="e17e8-103">PAR 函数</span><span class="sxs-lookup"><span data-stu-id="e17e8-103">PAR Function</span></span>

<span data-ttu-id="e17e8-104">返回形状的父级的坐标系统中的点的_x，y_坐标。</span><span class="sxs-lookup"><span data-stu-id="e17e8-104">Returns the  _x,y_ coordinates of a point in the coordinate system of the shape's parent.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e17e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="e17e8-105">Syntax</span></span>

<span data-ttu-id="e17e8-106">PAR (* **指向** *)</span><span class="sxs-lookup"><span data-stu-id="e17e8-106">PAR(** *point* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e17e8-107">参数</span><span class="sxs-lookup"><span data-stu-id="e17e8-107">Parameters</span></span>

|<span data-ttu-id="e17e8-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e17e8-108">**Name**</span></span>|<span data-ttu-id="e17e8-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e17e8-109">**Required/Optional**</span></span>|<span data-ttu-id="e17e8-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e17e8-110">**Data Type**</span></span>|<span data-ttu-id="e17e8-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e17e8-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e17e8-112">_磅_</span><span class="sxs-lookup"><span data-stu-id="e17e8-112">_point_</span></span> <br/> |<span data-ttu-id="e17e8-113">必需</span><span class="sxs-lookup"><span data-stu-id="e17e8-113">Required</span></span>  <br/> |<span data-ttu-id="e17e8-114">**Number, Number**</span><span class="sxs-lookup"><span data-stu-id="e17e8-114">**Number, Number**</span></span> <br/> |<span data-ttu-id="e17e8-115">用当前形状的坐标系表示的点的坐标。</span><span class="sxs-lookup"><span data-stu-id="e17e8-115">The coordinates of the point in the coordinate system of the current shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e17e8-116">说明</span><span class="sxs-lookup"><span data-stu-id="e17e8-116">Remarks</span></span>

<span data-ttu-id="e17e8-117">Microsoft Visio 中点是一个 single 值它来实现一对*x*和*y* -坐标。</span><span class="sxs-lookup"><span data-stu-id="e17e8-117">In Microsoft Visio, a point is a single value that embodies a pair of  *x*  - and  *y*  -coordinates.</span></span> <span data-ttu-id="e17e8-118">如果形状是组中，其父对象是组。</span><span class="sxs-lookup"><span data-stu-id="e17e8-118">If the shape is in a group, its parent is the group.</span></span> <span data-ttu-id="e17e8-119">如果形状不是组中，其父对象是页面。</span><span class="sxs-lookup"><span data-stu-id="e17e8-119">If the shape is not in a group, its parent is the page.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e17e8-120">示例</span><span class="sxs-lookup"><span data-stu-id="e17e8-120">Example</span></span>

<span data-ttu-id="e17e8-121">PAR(PNT(PinX,PinY))</span><span class="sxs-lookup"><span data-stu-id="e17e8-121">PAR(PNT(PinX,PinY))</span></span> 
  
<span data-ttu-id="e17e8-p102">在此表达式中，PNT 将当前形状中的一对坐标转换为一个点。然后，PAR 再将这个点转换为相对于包含当前形状的页或组合的左下角的一对坐标。</span><span class="sxs-lookup"><span data-stu-id="e17e8-p102">In this expression, PNT converts a pair of coordinates in the current shape into a point. PAR then converts the point into a pair of coordinates in relation to the lower-left corner of the page or group that contains the current shape.</span></span> 
  

