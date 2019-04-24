---
title: SHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b4fbcb8-1ae4-c9fb-6337-b72f49aedd91
description: 通过按 int 参数中指定的量 (正数或负数) 降低亮度来修改颜色。
ms.openlocfilehash: b31b4c49a823ace3f6474b94ba3737791928520d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326593"
---
# <a name="shade-function"></a><span data-ttu-id="c758d-103">SHADE 函数</span><span class="sxs-lookup"><span data-stu-id="c758d-103">SHADE Function</span></span>

<span data-ttu-id="c758d-104">通过按_int_参数中指定的量 (正数或负数) 降低亮度来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="c758d-104">Modifies the color by decreasing its luminosity by the amount (positive or negative) specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="c758d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c758d-105">Syntax</span></span>

<span data-ttu-id="c758d-106">底纹 (\* **颜色** \*, \* \* *int* \* \*)</span><span class="sxs-lookup"><span data-stu-id="c758d-106">SHADE(\*\* *color* \*\*, \*\* *int* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c758d-107">参数</span><span class="sxs-lookup"><span data-stu-id="c758d-107">Parameters</span></span>

|<span data-ttu-id="c758d-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c758d-108">**Name**</span></span>|<span data-ttu-id="c758d-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c758d-109">**Required/Optional**</span></span>|<span data-ttu-id="c758d-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c758d-110">**Data Type**</span></span>|<span data-ttu-id="c758d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c758d-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c758d-112">_color_</span><span class="sxs-lookup"><span data-stu-id="c758d-112">_color_</span></span> <br/> |<span data-ttu-id="c758d-113">必需</span><span class="sxs-lookup"><span data-stu-id="c758d-113">Required</span></span>  <br/> |<span data-ttu-id="c758d-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="c758d-114">**Numeric**</span></span> <br/> |<span data-ttu-id="c758d-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="c758d-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="c758d-116">_int_</span><span class="sxs-lookup"><span data-stu-id="c758d-116">_int_</span></span> <br/> |<span data-ttu-id="c758d-117">必需</span><span class="sxs-lookup"><span data-stu-id="c758d-117">Required</span></span>  <br/> |<span data-ttu-id="c758d-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="c758d-118">**Integer**</span></span> <br/> |<span data-ttu-id="c758d-119">颜色发光度降低的数量。</span><span class="sxs-lookup"><span data-stu-id="c758d-119">The amount by which to decrease the luminosity of the color.</span></span> <span data-ttu-id="c758d-120">可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="c758d-120">Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c758d-121">返回值</span><span class="sxs-lookup"><span data-stu-id="c758d-121">Return value</span></span>

 <span data-ttu-id="c758d-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="c758d-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c758d-123">注解</span><span class="sxs-lookup"><span data-stu-id="c758d-123">Remarks</span></span>

<span data-ttu-id="c758d-124">发光度的上限和下限分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="c758d-124">The upper and lower limits of luminosity are 0 and 240 respectively.</span></span> <span data-ttu-id="c758d-125">对于可以传递给_int_参数的整数大小没有限制, 但发光度不会超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="c758d-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but luminosity never exceeds these limits.</span></span> 
  
![亮度上限和下限](media/image199_ZA10173627.gif)
  

