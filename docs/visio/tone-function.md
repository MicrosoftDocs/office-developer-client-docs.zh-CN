---
title: TONE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2d6a7dd-9f15-27bd-9623-2a047683ff98
description: 通过将其饱和度降低为 int 参数中指定的数量来修改颜色。
ms.openlocfilehash: c3352d4c15671244d0fc4701f2c26b4e0c2ea54d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335684"
---
# <a name="tone-function"></a><span data-ttu-id="8c573-103">TONE 函数</span><span class="sxs-lookup"><span data-stu-id="8c573-103">TONE Function</span></span>

<span data-ttu-id="8c573-104">通过将其饱和度降低为_int_参数中指定的数量来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="8c573-104">Modifies the color by decreasing its saturation by the amount specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8c573-105">语法</span><span class="sxs-lookup"><span data-stu-id="8c573-105">Syntax</span></span>

<span data-ttu-id="8c573-106">音调 (\* \* *color* \* \*, \* \* *int* \* \*)</span><span class="sxs-lookup"><span data-stu-id="8c573-106">TONE(\*\* *color* \*\*, \*\* *int* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8c573-107">参数</span><span class="sxs-lookup"><span data-stu-id="8c573-107">Parameters</span></span>

|<span data-ttu-id="8c573-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c573-108">**Name**</span></span>|<span data-ttu-id="8c573-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8c573-109">**Required/Optional**</span></span>|<span data-ttu-id="8c573-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8c573-110">**Data Type**</span></span>|<span data-ttu-id="8c573-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c573-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8c573-112">_color_</span><span class="sxs-lookup"><span data-stu-id="8c573-112">_color_</span></span> <br/> |<span data-ttu-id="8c573-113">必需</span><span class="sxs-lookup"><span data-stu-id="8c573-113">Required</span></span>  <br/> |<span data-ttu-id="8c573-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="8c573-114">**Numeric**</span></span> <br/> |<span data-ttu-id="8c573-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="8c573-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="8c573-116">_int_</span><span class="sxs-lookup"><span data-stu-id="8c573-116">_int_</span></span> <br/> |<span data-ttu-id="8c573-117">必需</span><span class="sxs-lookup"><span data-stu-id="8c573-117">Required</span></span>  <br/> |<span data-ttu-id="8c573-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="8c573-118">**Integer**</span></span> <br/> |<span data-ttu-id="8c573-119">颜色饱和度降低的数量。</span><span class="sxs-lookup"><span data-stu-id="8c573-119">The amount by which to decrease the saturation of the color.</span></span> <span data-ttu-id="8c573-120">可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="8c573-120">Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="8c573-121">返回值</span><span class="sxs-lookup"><span data-stu-id="8c573-121">Return value</span></span>

 <span data-ttu-id="8c573-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="8c573-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8c573-123">注解</span><span class="sxs-lookup"><span data-stu-id="8c573-123">Remarks</span></span>

<span data-ttu-id="8c573-124">饱和度的上下限分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="8c573-124">The upper and lower limits of saturation are 0 and 240 respectively.</span></span> <span data-ttu-id="8c573-125">对于可以传递给_int_参数的整数大小没有限制, 但饱和度不会超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="8c573-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but saturation never exceeds these limits.</span></span> 
  

