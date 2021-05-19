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
description: 返回形状父级坐标系中点的 x，y 坐标。
ms.openlocfilehash: 4e7517c4210db31f1c3f5dc8bf98185b6f4104aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414506"
---
# <a name="par-function"></a><span data-ttu-id="0aba3-103">PAR 函数</span><span class="sxs-lookup"><span data-stu-id="0aba3-103">PAR Function</span></span>

<span data-ttu-id="0aba3-104">返回形状父级坐标系中点的  _x，y_ 坐标。</span><span class="sxs-lookup"><span data-stu-id="0aba3-104">Returns the  _x,y_ coordinates of a point in the coordinate system of the shape's parent.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="0aba3-105">语法</span><span class="sxs-lookup"><span data-stu-id="0aba3-105">Syntax</span></span>

<span data-ttu-id="0aba3-106">PAR (\*\* *point* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="0aba3-106">PAR(\*\* *point* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0aba3-107">参数</span><span class="sxs-lookup"><span data-stu-id="0aba3-107">Parameters</span></span>

|<span data-ttu-id="0aba3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="0aba3-108">**Name**</span></span>|<span data-ttu-id="0aba3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0aba3-109">**Required/Optional**</span></span>|<span data-ttu-id="0aba3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0aba3-110">**Data Type**</span></span>|<span data-ttu-id="0aba3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="0aba3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0aba3-112">_point_</span><span class="sxs-lookup"><span data-stu-id="0aba3-112">_point_</span></span> <br/> |<span data-ttu-id="0aba3-113">必需</span><span class="sxs-lookup"><span data-stu-id="0aba3-113">Required</span></span>  <br/> |<span data-ttu-id="0aba3-114">**Number, Number**</span><span class="sxs-lookup"><span data-stu-id="0aba3-114">**Number, Number**</span></span> <br/> |<span data-ttu-id="0aba3-115">用当前形状的坐标系表示的点的坐标。</span><span class="sxs-lookup"><span data-stu-id="0aba3-115">The coordinates of the point in the coordinate system of the current shape.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0aba3-116">备注</span><span class="sxs-lookup"><span data-stu-id="0aba3-116">Remarks</span></span>

<span data-ttu-id="0aba3-117">在 Microsoft Visio 中，点是包含 *一对 x* 坐标和 *y* 坐标的单个值。</span><span class="sxs-lookup"><span data-stu-id="0aba3-117">In Microsoft Visio, a point is a single value that embodies a pair of  *x*  - and  *y*  -coordinates.</span></span> <span data-ttu-id="0aba3-118">如果形状在一个组合中，则它的父级就是该组合。</span><span class="sxs-lookup"><span data-stu-id="0aba3-118">If the shape is in a group, its parent is the group.</span></span> <span data-ttu-id="0aba3-119">如果形状不在一个组合中，则它的父级是页。</span><span class="sxs-lookup"><span data-stu-id="0aba3-119">If the shape is not in a group, its parent is the page.</span></span> 
  
## <a name="example"></a><span data-ttu-id="0aba3-120">示例</span><span class="sxs-lookup"><span data-stu-id="0aba3-120">Example</span></span>

<span data-ttu-id="0aba3-121">PAR (PNT (PinX，PinY) ) </span><span class="sxs-lookup"><span data-stu-id="0aba3-121">PAR(PNT(PinX,PinY))</span></span> 
  
<span data-ttu-id="0aba3-p102">在此表达式中，PNT 将当前形状中的一对坐标转换为一个点。然后，PAR 再将这个点转换为相对于包含当前形状的页或组合的左下角的一对坐标。</span><span class="sxs-lookup"><span data-stu-id="0aba3-p102">In this expression, PNT converts a pair of coordinates in the current shape into a point. PAR then converts the point into a pair of coordinates in relation to the lower-left corner of the page or group that contains the current shape.</span></span> 
  

