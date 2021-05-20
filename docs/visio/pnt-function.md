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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435710"
---
# <a name="pnt-function"></a><span data-ttu-id="b8cd0-103">PNT 函数</span><span class="sxs-lookup"><span data-stu-id="b8cd0-103">PNT Function</span></span>

<span data-ttu-id="b8cd0-104">以单个值返回坐标  _x_ 和  _y_ 表示的点。</span><span class="sxs-lookup"><span data-stu-id="b8cd0-104">Returns the point represented by the coordinates  _x_ and  _y_ as a single value.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b8cd0-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8cd0-105">Syntax</span></span>

<span data-ttu-id="b8cd0-106">PNT (\*\* *x，y* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="b8cd0-106">PNT(\*\* *x,y* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="b8cd0-107">参数</span><span class="sxs-lookup"><span data-stu-id="b8cd0-107">Parameters</span></span>

|<span data-ttu-id="b8cd0-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-108">**Name**</span></span>|<span data-ttu-id="b8cd0-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-109">**Required/Optional**</span></span>|<span data-ttu-id="b8cd0-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-110">**Data Type**</span></span>|<span data-ttu-id="b8cd0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b8cd0-112">_x，y_</span><span class="sxs-lookup"><span data-stu-id="b8cd0-112">_x,y_</span></span> <br/> |<span data-ttu-id="b8cd0-113">必需</span><span class="sxs-lookup"><span data-stu-id="b8cd0-113">Required</span></span>  <br/> |<span data-ttu-id="b8cd0-114">**Number, Number**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-114">**Number, Number**</span></span> <br/> |<span data-ttu-id="b8cd0-115">用当前形状的坐标系表示的点的坐标。</span><span class="sxs-lookup"><span data-stu-id="b8cd0-115">The coordinates of the point in the coordinate system of the current shape.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="b8cd0-116">返回值</span><span class="sxs-lookup"><span data-stu-id="b8cd0-116">Return value</span></span>

<span data-ttu-id="b8cd0-117">Point</span><span class="sxs-lookup"><span data-stu-id="b8cd0-117">Point</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b8cd0-118">备注</span><span class="sxs-lookup"><span data-stu-id="b8cd0-118">Remarks</span></span>

<span data-ttu-id="b8cd0-119">通过将坐标转换为点，可以更改形状的几何图形，而无需单独处理  *x*  坐标和  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="b8cd0-119">Converting coordinates to points allows you to change a shape's geometry without having to manipulate  *x*  - and  *y*  -coordinates separately.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b8cd0-120">示例</span><span class="sxs-lookup"><span data-stu-id="b8cd0-120">Example</span></span>

<span data-ttu-id="b8cd0-121">PNT (PinX，PinY) </span><span class="sxs-lookup"><span data-stu-id="b8cd0-121">PNT(PinX,PinY)</span></span> 
  
<span data-ttu-id="b8cd0-122">返回由 PinX 和 PinY 表示的点。</span><span class="sxs-lookup"><span data-stu-id="b8cd0-122">Returns the point represented by PinX and PinY.</span></span> 
  

