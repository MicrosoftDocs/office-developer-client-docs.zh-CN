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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406575"
---
# <a name="tint-function"></a><span data-ttu-id="1d4f2-103">TINT 函数</span><span class="sxs-lookup"><span data-stu-id="1d4f2-103">TINT Function</span></span>

<span data-ttu-id="1d4f2-104">通过按_int_参数中指定的量 (正数或负数) 增加亮度来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-104">Modifies the color by increasing its luminosity by the amount (positive or negative) specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1d4f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="1d4f2-105">Syntax</span></span>

<span data-ttu-id="1d4f2-106">淡色 (\* \* *color* \* \*, \* \* *int* \* \*)</span><span class="sxs-lookup"><span data-stu-id="1d4f2-106">TINT(\*\* *color* \*\*, \*\* *int* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="1d4f2-107">参数</span><span class="sxs-lookup"><span data-stu-id="1d4f2-107">Parameters</span></span>

|<span data-ttu-id="1d4f2-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-108">**Name**</span></span>|<span data-ttu-id="1d4f2-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-109">**Required/Optional**</span></span>|<span data-ttu-id="1d4f2-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-110">**Data Type**</span></span>|<span data-ttu-id="1d4f2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1d4f2-112">_color_</span><span class="sxs-lookup"><span data-stu-id="1d4f2-112">_color_</span></span> <br/> |<span data-ttu-id="1d4f2-113">必需</span><span class="sxs-lookup"><span data-stu-id="1d4f2-113">Required</span></span>  <br/> |<span data-ttu-id="1d4f2-114">**数值**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-114">**Numeric**</span></span> <br/> |<span data-ttu-id="1d4f2-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="1d4f2-116">_int_</span><span class="sxs-lookup"><span data-stu-id="1d4f2-116">_int_</span></span> <br/> |<span data-ttu-id="1d4f2-117">必需</span><span class="sxs-lookup"><span data-stu-id="1d4f2-117">Required</span></span>  <br/> |<span data-ttu-id="1d4f2-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-118">**Integer**</span></span> <br/> |<span data-ttu-id="1d4f2-119">颜色发光度降低的数量。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-119">The amount by which to increase the luminosity of the color.</span></span> <span data-ttu-id="1d4f2-120">可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-120">Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="1d4f2-121">返回值</span><span class="sxs-lookup"><span data-stu-id="1d4f2-121">Return value</span></span>

 <span data-ttu-id="1d4f2-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="1d4f2-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1d4f2-123">说明</span><span class="sxs-lookup"><span data-stu-id="1d4f2-123">Remarks</span></span>

<span data-ttu-id="1d4f2-124">发光度的上限和下限分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-124">The upper and lower limits of luminosity are 0 and 240 respectively.</span></span> <span data-ttu-id="1d4f2-125">对于可以传递给_int_参数的整数大小没有限制, 但发光度不会超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="1d4f2-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but luminosity never exceeds these limits.</span></span> 
  

