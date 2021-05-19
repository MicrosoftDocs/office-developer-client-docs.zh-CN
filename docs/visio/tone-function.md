---
title: TONE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2d6a7dd-9f15-27bd-9623-2a047683ff98
description: 通过按 int 参数中指定的数量降低颜色饱和度来修改颜色。
ms.openlocfilehash: c3352d4c15671244d0fc4701f2c26b4e0c2ea54d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434373"
---
# <a name="tone-function"></a><span data-ttu-id="a2c01-103">TONE 函数</span><span class="sxs-lookup"><span data-stu-id="a2c01-103">TONE Function</span></span>

<span data-ttu-id="a2c01-104">通过按  _int_ 参数中指定的数量降低颜色饱和度来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="a2c01-104">Modifies the color by decreasing its saturation by the amount specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a2c01-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2c01-105">Syntax</span></span>

<span data-ttu-id="a2c01-106">TONE (\*\* *color* \*\*， \*\* *int* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="a2c01-106">TONE(\*\* *color* \*\*, \*\* *int* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a2c01-107">参数</span><span class="sxs-lookup"><span data-stu-id="a2c01-107">Parameters</span></span>

|<span data-ttu-id="a2c01-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a2c01-108">**Name**</span></span>|<span data-ttu-id="a2c01-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a2c01-109">**Required/Optional**</span></span>|<span data-ttu-id="a2c01-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a2c01-110">**Data Type**</span></span>|<span data-ttu-id="a2c01-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a2c01-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a2c01-112">_color_</span><span class="sxs-lookup"><span data-stu-id="a2c01-112">_color_</span></span> <br/> |<span data-ttu-id="a2c01-113">必需</span><span class="sxs-lookup"><span data-stu-id="a2c01-113">Required</span></span>  <br/> |<span data-ttu-id="a2c01-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="a2c01-114">**Numeric**</span></span> <br/> |<span data-ttu-id="a2c01-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="a2c01-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="a2c01-116">_int_</span><span class="sxs-lookup"><span data-stu-id="a2c01-116">_int_</span></span> <br/> |<span data-ttu-id="a2c01-117">必需</span><span class="sxs-lookup"><span data-stu-id="a2c01-117">Required</span></span>  <br/> |<span data-ttu-id="a2c01-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="a2c01-118">**Integer**</span></span> <br/> |<span data-ttu-id="a2c01-p101">颜色饱和度降低的数量。可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="a2c01-p101">The amount by which to decrease the saturation of the color. Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="a2c01-121">返回值</span><span class="sxs-lookup"><span data-stu-id="a2c01-121">Return value</span></span>

 <span data-ttu-id="a2c01-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="a2c01-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a2c01-123">备注</span><span class="sxs-lookup"><span data-stu-id="a2c01-123">Remarks</span></span>

<span data-ttu-id="a2c01-124">饱和度的上下限分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="a2c01-124">The upper and lower limits of saturation are 0 and 240 respectively.</span></span> <span data-ttu-id="a2c01-125">您可以为  _int_ 参数传递的整数大小没有限制，但饱和度永远不会超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="a2c01-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but saturation never exceeds these limits.</span></span> 
  

