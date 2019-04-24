---
title: TINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c4f176d6-4af0-282d-5640-7d98e84dfb55
description: 通过按 int 参数中指定的量 (正数或负数) 增加亮度来修改颜色。
ms.openlocfilehash: 8924bc0662814e14d01b4bd5332f5fadeb0a1082
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280929"
---
# <a name="tint-function"></a><span data-ttu-id="13ab3-103">TINT 函数</span><span class="sxs-lookup"><span data-stu-id="13ab3-103">TINT Function</span></span>

<span data-ttu-id="13ab3-104">通过按_int_参数中指定的量 (正数或负数) 增加亮度来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="13ab3-104">Modifies the color by increasing its luminosity by the amount (positive or negative) specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="13ab3-105">语法</span><span class="sxs-lookup"><span data-stu-id="13ab3-105">Syntax</span></span>

<span data-ttu-id="13ab3-106">淡色 (\* \* *color* \* \*, \* \* *int* \* \*)</span><span class="sxs-lookup"><span data-stu-id="13ab3-106">TINT(\*\* *color* \*\*, \*\* *int* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="13ab3-107">参数</span><span class="sxs-lookup"><span data-stu-id="13ab3-107">Parameters</span></span>

|<span data-ttu-id="13ab3-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="13ab3-108">**Name**</span></span>|<span data-ttu-id="13ab3-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="13ab3-109">**Required/Optional**</span></span>|<span data-ttu-id="13ab3-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="13ab3-110">**Data Type**</span></span>|<span data-ttu-id="13ab3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="13ab3-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="13ab3-112">_color_</span><span class="sxs-lookup"><span data-stu-id="13ab3-112">_color_</span></span> <br/> |<span data-ttu-id="13ab3-113">必需</span><span class="sxs-lookup"><span data-stu-id="13ab3-113">Required</span></span>  <br/> |<span data-ttu-id="13ab3-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="13ab3-114">**Numeric**</span></span> <br/> |<span data-ttu-id="13ab3-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="13ab3-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="13ab3-116">_int_</span><span class="sxs-lookup"><span data-stu-id="13ab3-116">_int_</span></span> <br/> |<span data-ttu-id="13ab3-117">必需</span><span class="sxs-lookup"><span data-stu-id="13ab3-117">Required</span></span>  <br/> |<span data-ttu-id="13ab3-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="13ab3-118">**Integer**</span></span> <br/> |<span data-ttu-id="13ab3-119">颜色发光度降低的数量。</span><span class="sxs-lookup"><span data-stu-id="13ab3-119">The amount by which to increase the luminosity of the color.</span></span> <span data-ttu-id="13ab3-120">可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="13ab3-120">Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="13ab3-121">返回值</span><span class="sxs-lookup"><span data-stu-id="13ab3-121">Return value</span></span>

 <span data-ttu-id="13ab3-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="13ab3-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="13ab3-123">注解</span><span class="sxs-lookup"><span data-stu-id="13ab3-123">Remarks</span></span>

<span data-ttu-id="13ab3-124">发光度的上限和下限分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="13ab3-124">The upper and lower limits of luminosity are 0 and 240 respectively.</span></span> <span data-ttu-id="13ab3-125">对于可以传递给_int_参数的整数大小没有限制, 但发光度不会超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="13ab3-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but luminosity never exceeds these limits.</span></span> 
  

