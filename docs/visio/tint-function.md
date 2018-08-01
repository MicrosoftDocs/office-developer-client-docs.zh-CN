---
title: TINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c4f176d6-4af0-282d-5640-7d98e84dfb55
description: 修改颜色的发光度增加量 （正数或负数） int 参数中指定。
ms.openlocfilehash: a4b15596a4742edb4f9e4746929f19d2eafe94d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781534"
---
# <a name="tint-function"></a><span data-ttu-id="a8fb7-103">TINT 函数</span><span class="sxs-lookup"><span data-stu-id="a8fb7-103">TINT Function</span></span>

<span data-ttu-id="a8fb7-104">修改颜色的发光度增加量 （正数或负数） _int_参数中指定。</span><span class="sxs-lookup"><span data-stu-id="a8fb7-104">Modifies the color by increasing its luminosity by the amount (positive or negative) specified in the  _int_ parameter.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a8fb7-105">语法</span><span class="sxs-lookup"><span data-stu-id="a8fb7-105">Syntax</span></span>

<span data-ttu-id="a8fb7-106">TINT (* **颜色** *，* * *int* * *)</span><span class="sxs-lookup"><span data-stu-id="a8fb7-106">TINT(** *color* **, ** *int* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="a8fb7-107">参数</span><span class="sxs-lookup"><span data-stu-id="a8fb7-107">Parameters</span></span>

|<span data-ttu-id="a8fb7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-108">**Name**</span></span>|<span data-ttu-id="a8fb7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-109">**Required/Optional**</span></span>|<span data-ttu-id="a8fb7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-110">**Data Type**</span></span>|<span data-ttu-id="a8fb7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="a8fb7-112">_color_</span><span class="sxs-lookup"><span data-stu-id="a8fb7-112">_color_</span></span> <br/> |<span data-ttu-id="a8fb7-113">必需</span><span class="sxs-lookup"><span data-stu-id="a8fb7-113">Required</span></span>  <br/> |<span data-ttu-id="a8fb7-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-114">**Numeric**</span></span> <br/> |<span data-ttu-id="a8fb7-115">Microsoft Visio 颜色的颜色索引或 RGB 值。</span><span class="sxs-lookup"><span data-stu-id="a8fb7-115">The Microsoft Visio color index or RGB value of the color.</span></span>  <br/> |
| <span data-ttu-id="a8fb7-116">_int_</span><span class="sxs-lookup"><span data-stu-id="a8fb7-116">_int_</span></span> <br/> |<span data-ttu-id="a8fb7-117">必需</span><span class="sxs-lookup"><span data-stu-id="a8fb7-117">Required</span></span>  <br/> |<span data-ttu-id="a8fb7-118">**Integer**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-118">**Integer**</span></span> <br/> |<span data-ttu-id="a8fb7-p101">颜色发光度降低的数量。可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="a8fb7-p101">The amount by which to increase the luminosity of the color. Can be positive or negative.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="a8fb7-121">返回值</span><span class="sxs-lookup"><span data-stu-id="a8fb7-121">Return value</span></span>

 <span data-ttu-id="a8fb7-122">**RGB**</span><span class="sxs-lookup"><span data-stu-id="a8fb7-122">**RGB**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a8fb7-123">说明</span><span class="sxs-lookup"><span data-stu-id="a8fb7-123">Remarks</span></span>

<span data-ttu-id="a8fb7-124">发光度的上限和下限限制分别为 0 和 240。</span><span class="sxs-lookup"><span data-stu-id="a8fb7-124">The upper and lower limits of luminosity are 0 and 240 respectively.</span></span> <span data-ttu-id="a8fb7-125">您可以为_int_参数，传递的整数的大小没有限制，但发光度不能超过这些限制。</span><span class="sxs-lookup"><span data-stu-id="a8fb7-125">There is no limit on the size of the integer you can pass for the  _int_ parameter, but luminosity never exceeds these limits.</span></span> 
  

