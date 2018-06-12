---
title: SHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b4fbcb8-1ae4-c9fb-6337-b72f49aedd91
description: 修改颜色的发光度降低量 （正数或负数） int 参数中指定。
ms.openlocfilehash: 4a02aa41050c3cf36b567c238670b5f61074bd7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781248"
---
# <a name="shade-function"></a><span data-ttu-id="f5f75-103">SHADE 函数</span><span class="sxs-lookup"><span data-stu-id="f5f75-103">SHADE Function</span></span>

<span data-ttu-id="f5f75-104">修改颜色的发光度降低量 （正数或负数） _int_参数中指定。</span><span class="sxs-lookup"><span data-stu-id="f5f75-104">Modifies the color by decreasing its luminosity by the amount (positive or negative) specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f5f75-105">语法</span><span class="sxs-lookup"><span data-stu-id="f5f75-105">Syntax</span></span>

<span data-ttu-id="f5f75-106">%底纹 (* **颜色** *，* * *int* * *)</span><span class="sxs-lookup"><span data-stu-id="f5f75-106">SHADE(** *color* **, ** *int* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="f5f75-107">参数</span><span class="sxs-lookup"><span data-stu-id="f5f75-107">Parameters</span></span>

|<span data-ttu-id="f5f75-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="f5f75-108">**Name**</span></span>|<span data-ttu-id="f5f75-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f5f75-109">**Required/Optional**</span></span>|<span data-ttu-id="f5f75-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f5f75-110">**Data Type**</span></span>|<span data-ttu-id="f5f75-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5f75-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f5f75-112">_color_</span><span class="sxs-lookup"><span data-stu-id="f5f75-112">_color_</span></span> <br/> |<span data-ttu-id="f5f75-113">必需</span><span class="sxs-lookup"><span data-stu-id="f5f75-113">Required</span></span>  <br/> |<span data-ttu-id="f5f75-114">**数字**</span><span class="sxs-lookup"><span data-stu-id="f5f75-114">**Numeric**</span></span> <br/> |<span data-ttu-id="f5f75-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="f5f75-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="f5f75-116">_int_</span><span class="sxs-lookup"><span data-stu-id="f5f75-116">_int_</span></span> <br/> |<span data-ttu-id="f5f75-117">必需</span><span class="sxs-lookup"><span data-stu-id="f5f75-117">Required</span></span>  <br/> |<span data-ttu-id="f5f75-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="f5f75-118">**Integer**</span></span> <br/> |<span data-ttu-id="f5f75-p101">颜色发光度降低的数量。可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="f5f75-p101">The amount by which to decrease the luminosity of the color. Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="f5f75-121">返回值</span><span class="sxs-lookup"><span data-stu-id="f5f75-121">Return value</span></span>

 <span data-ttu-id="f5f75-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="f5f75-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f5f75-123">备注</span><span class="sxs-lookup"><span data-stu-id="f5f75-123">Remarks</span></span>

<span data-ttu-id="f5f75-124">发光度的上限和下限限制分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="f5f75-124">The upper and lower limits of luminosity are 0 and 240 respectively.</span></span> <span data-ttu-id="f5f75-125">您可以为_int_参数，传递的整数的大小没有限制，但发光度不能超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="f5f75-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but luminosity never exceeds these limits.</span></span> 
  
![](media/image199_ZA10173627.gif)
  

