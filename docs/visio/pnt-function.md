---
title: PNT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251480
localization_priority: Normal
ms.assetid: d14a735c-0278-922f-7823-79adf6cb1e64
description: 以单个值的形式返回使用坐标 x 和 y 表示的点。
ms.openlocfilehash: be00f7d5ae55f70407e35eca43881a6d3f70ec13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780934"
---
# <a name="pnt-function"></a><span data-ttu-id="11311-103">PNT 函数</span><span class="sxs-lookup"><span data-stu-id="11311-103">PNT Function</span></span>

<span data-ttu-id="11311-104">返回由坐标_x_和_y_作为单个值表示的点。</span><span class="sxs-lookup"><span data-stu-id="11311-104">Returns the point represented by the coordinates  _x_ and  _y_ as a single value.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="11311-105">语法</span><span class="sxs-lookup"><span data-stu-id="11311-105">Syntax</span></span>

<span data-ttu-id="11311-106">PNT (* * *x、 y* * *)</span><span class="sxs-lookup"><span data-stu-id="11311-106">PNT(** *x,y* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="11311-107">参数</span><span class="sxs-lookup"><span data-stu-id="11311-107">Parameters</span></span>

|<span data-ttu-id="11311-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="11311-108">**Name**</span></span>|<span data-ttu-id="11311-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="11311-109">**Required/Optional**</span></span>|<span data-ttu-id="11311-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="11311-110">**Data Type**</span></span>|<span data-ttu-id="11311-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="11311-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="11311-112">_x y_</span><span class="sxs-lookup"><span data-stu-id="11311-112">_x,y_</span></span> <br/> |<span data-ttu-id="11311-113">必需</span><span class="sxs-lookup"><span data-stu-id="11311-113">Required</span></span>  <br/> |<span data-ttu-id="11311-114">**Number, Number**</span><span class="sxs-lookup"><span data-stu-id="11311-114">**Number, Number**</span></span> <br/> |<span data-ttu-id="11311-115">用当前形状的坐标系表示的点的坐标。</span><span class="sxs-lookup"><span data-stu-id="11311-115">The coordinates of the point in the coordinate system of the current shape.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="11311-116">返回值</span><span class="sxs-lookup"><span data-stu-id="11311-116">Return value</span></span>

<span data-ttu-id="11311-117">Point</span><span class="sxs-lookup"><span data-stu-id="11311-117">Point</span></span>
  
## <a name="remarks"></a><span data-ttu-id="11311-118">注解</span><span class="sxs-lookup"><span data-stu-id="11311-118">Remarks</span></span>

<span data-ttu-id="11311-119">将坐标转换为磅允许您更改形状的几何图形，而无需处理*x*和*y* -单独坐标。</span><span class="sxs-lookup"><span data-stu-id="11311-119">Converting coordinates to points allows you to change a shape's geometry without having to manipulate  *x*  - and  *y*  -coordinates separately.</span></span> 
  
## <a name="example"></a><span data-ttu-id="11311-120">示例</span><span class="sxs-lookup"><span data-stu-id="11311-120">Example</span></span>

<span data-ttu-id="11311-121">PNT(PinX,PinY)</span><span class="sxs-lookup"><span data-stu-id="11311-121">PNT(PinX,PinY)</span></span> 
  
<span data-ttu-id="11311-122">返回由 PinX 和 PinY 表示的点。</span><span class="sxs-lookup"><span data-stu-id="11311-122">Returns the point represented by PinX and PinY.</span></span> 
  

