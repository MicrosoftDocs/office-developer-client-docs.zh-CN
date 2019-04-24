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
ms.openlocfilehash: c0a12aa18f4c766ea1f5b0fa1d827804d766713c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322349"
---
# <a name="pnt-function"></a><span data-ttu-id="60d03-103">PNT 函数</span><span class="sxs-lookup"><span data-stu-id="60d03-103">PNT Function</span></span>

<span data-ttu-id="60d03-104">以单个值的形式返回以_x_轴和_y 轴_坐标表示的点。</span><span class="sxs-lookup"><span data-stu-id="60d03-104">Returns the point represented by the coordinates  _x_ and  _y_ as a single value.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="60d03-105">语法</span><span class="sxs-lookup"><span data-stu-id="60d03-105">Syntax</span></span>

<span data-ttu-id="60d03-106">PNT (\* \* *x, y* \* \*)</span><span class="sxs-lookup"><span data-stu-id="60d03-106">PNT(\*\* *x,y* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="60d03-107">参数</span><span class="sxs-lookup"><span data-stu-id="60d03-107">Parameters</span></span>

|<span data-ttu-id="60d03-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="60d03-108">**Name**</span></span>|<span data-ttu-id="60d03-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="60d03-109">**Required/Optional**</span></span>|<span data-ttu-id="60d03-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="60d03-110">**Data Type**</span></span>|<span data-ttu-id="60d03-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="60d03-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="60d03-112">_x、y_</span><span class="sxs-lookup"><span data-stu-id="60d03-112">_x,y_</span></span> <br/> |<span data-ttu-id="60d03-113">必需</span><span class="sxs-lookup"><span data-stu-id="60d03-113">Required</span></span>  <br/> |<span data-ttu-id="60d03-114">**Number, Number**</span><span class="sxs-lookup"><span data-stu-id="60d03-114">**Number, Number**</span></span> <br/> |<span data-ttu-id="60d03-115">用当前形状的坐标系表示的点的坐标。</span><span class="sxs-lookup"><span data-stu-id="60d03-115">The coordinates of the point in the coordinate system of the current shape.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="60d03-116">返回值</span><span class="sxs-lookup"><span data-stu-id="60d03-116">Return value</span></span>

<span data-ttu-id="60d03-117">Point</span><span class="sxs-lookup"><span data-stu-id="60d03-117">Point</span></span>
  
## <a name="remarks"></a><span data-ttu-id="60d03-118">注解</span><span class="sxs-lookup"><span data-stu-id="60d03-118">Remarks</span></span>

<span data-ttu-id="60d03-119">将坐标转换为磅使您可以更改形状的几何图形, 而无需分别处理*x*坐标和*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="60d03-119">Converting coordinates to points allows you to change a shape's geometry without having to manipulate  *x*  - and  *y*  -coordinates separately.</span></span> 
  
## <a name="example"></a><span data-ttu-id="60d03-120">示例</span><span class="sxs-lookup"><span data-stu-id="60d03-120">Example</span></span>

<span data-ttu-id="60d03-121">PNT (PinX, PinY)</span><span class="sxs-lookup"><span data-stu-id="60d03-121">PNT(PinX,PinY)</span></span> 
  
<span data-ttu-id="60d03-122">返回由 PinX 和 PinY 表示的点。</span><span class="sxs-lookup"><span data-stu-id="60d03-122">Returns the point represented by PinX and PinY.</span></span> 
  

