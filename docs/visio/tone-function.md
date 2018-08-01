---
title: TONE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2d6a7dd-9f15-27bd-9623-2a047683ff98
description: 通过降低饱和度 int 参数中指定的数量来修改颜色。
ms.openlocfilehash: be89764c849299288963c272f8ffb2d5d728f270
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781544"
---
# <a name="tone-function"></a><span data-ttu-id="e2738-103">TONE 函数</span><span class="sxs-lookup"><span data-stu-id="e2738-103">TONE Function</span></span>

<span data-ttu-id="e2738-104">通过降低饱和度_int_参数中指定的数量来修改颜色。</span><span class="sxs-lookup"><span data-stu-id="e2738-104">Modifies the color by decreasing its saturation by the amount specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e2738-105">语法</span><span class="sxs-lookup"><span data-stu-id="e2738-105">Syntax</span></span>

<span data-ttu-id="e2738-106">音 (* **颜色** *，* * *int* * *)</span><span class="sxs-lookup"><span data-stu-id="e2738-106">TONE(** *color* **, ** *int* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="e2738-107">参数</span><span class="sxs-lookup"><span data-stu-id="e2738-107">Parameters</span></span>

|<span data-ttu-id="e2738-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="e2738-108">**Name**</span></span>|<span data-ttu-id="e2738-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="e2738-109">**Required/Optional**</span></span>|<span data-ttu-id="e2738-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e2738-110">**Data Type**</span></span>|<span data-ttu-id="e2738-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2738-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e2738-112">_color_</span><span class="sxs-lookup"><span data-stu-id="e2738-112">_color_</span></span> <br/> |<span data-ttu-id="e2738-113">必需</span><span class="sxs-lookup"><span data-stu-id="e2738-113">Required</span></span>  <br/> |<span data-ttu-id="e2738-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="e2738-114">**Numeric**</span></span> <br/> |<span data-ttu-id="e2738-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="e2738-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="e2738-116">_int_</span><span class="sxs-lookup"><span data-stu-id="e2738-116">_int_</span></span> <br/> |<span data-ttu-id="e2738-117">必需</span><span class="sxs-lookup"><span data-stu-id="e2738-117">Required</span></span>  <br/> |<span data-ttu-id="e2738-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="e2738-118">**Integer**</span></span> <br/> |<span data-ttu-id="e2738-p101">颜色饱和度降低的数量。可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="e2738-p101">The amount by which to decrease the saturation of the color. Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="e2738-121">返回值</span><span class="sxs-lookup"><span data-stu-id="e2738-121">Return value</span></span>

 <span data-ttu-id="e2738-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="e2738-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e2738-123">说明</span><span class="sxs-lookup"><span data-stu-id="e2738-123">Remarks</span></span>

<span data-ttu-id="e2738-124">饱和度上限和下限限制分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="e2738-124">The upper and lower limits of saturation are 0 and 240 respectively.</span></span> <span data-ttu-id="e2738-125">您可以为_int_参数，传递的整数的大小没有限制，但是饱和度不能超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="e2738-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but saturation never exceeds these limits.</span></span> 
  

