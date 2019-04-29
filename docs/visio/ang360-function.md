---
title: ANG360 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251392
localization_priority: Normal
ms.assetid: 23e6899d-0a94-a7d8-8de2-091e0531f163
description: 规范化角度的范围。
ms.openlocfilehash: 017dd89bd3b814c10422cd32eea1ee7e343eaf50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417194"
---
# <a name="ang360-function"></a><span data-ttu-id="0bb01-103">ANG360 函数</span><span class="sxs-lookup"><span data-stu-id="0bb01-103">ANG360 Function</span></span>

<span data-ttu-id="0bb01-104">将角度\<的范围规范化为 0 = result \< 2PI 弧度 (0 \<= 结果\< 360 度)。</span><span class="sxs-lookup"><span data-stu-id="0bb01-104">Normalizes an angle's range to be 0 \<= result \< 2PI radians (0 \<= result \< 360 degrees).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0bb01-105">语法</span><span class="sxs-lookup"><span data-stu-id="0bb01-105">Syntax</span></span>

<span data-ttu-id="0bb01-106">ANG360 (\* \* *angle* \* \*)</span><span class="sxs-lookup"><span data-stu-id="0bb01-106">ANG360(\*\* *angle* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0bb01-107">参数</span><span class="sxs-lookup"><span data-stu-id="0bb01-107">Parameters</span></span>

|<span data-ttu-id="0bb01-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="0bb01-108">**Name**</span></span>|<span data-ttu-id="0bb01-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="0bb01-109">**Required/Optional**</span></span>|<span data-ttu-id="0bb01-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0bb01-110">**Data Type**</span></span>|<span data-ttu-id="0bb01-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bb01-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0bb01-112">_angle_</span><span class="sxs-lookup"><span data-stu-id="0bb01-112">_angle_</span></span> <br/> |<span data-ttu-id="0bb01-113">必需</span><span class="sxs-lookup"><span data-stu-id="0bb01-113">Required</span></span>  <br/> |<span data-ttu-id="0bb01-114">**数值**</span><span class="sxs-lookup"><span data-stu-id="0bb01-114">**Numeric**</span></span> <br/> |<span data-ttu-id="0bb01-115">待规范化的角度。</span><span class="sxs-lookup"><span data-stu-id="0bb01-115">The angle to be normalized.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0bb01-116">说明</span><span class="sxs-lookup"><span data-stu-id="0bb01-116">Remarks</span></span>

<span data-ttu-id="0bb01-117">如果不使用角度单位指定*angle* , 则将其解释为弧度。</span><span class="sxs-lookup"><span data-stu-id="0bb01-117">If  *angle*  is not specified by using angular units, it is interpreted as radians.</span></span> <span data-ttu-id="0bb01-118">如果*angle*无法转换为值, #VALUE!</span><span class="sxs-lookup"><span data-stu-id="0bb01-118">If  *angle*  cannot be converted to a value, a #VALUE!</span></span> <span data-ttu-id="0bb01-119">错误。</span><span class="sxs-lookup"><span data-stu-id="0bb01-119">error is returned.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="0bb01-120">示例 1</span><span class="sxs-lookup"><span data-stu-id="0bb01-120">Example 1</span></span>

<span data-ttu-id="0bb01-121">ANG360(395 deg)</span><span class="sxs-lookup"><span data-stu-id="0bb01-121">ANG360(395 deg)</span></span>
  
<span data-ttu-id="0bb01-122">返回 35 度</span><span class="sxs-lookup"><span data-stu-id="0bb01-122">Returns 35 deg</span></span>
  
## <a name="example-2"></a><span data-ttu-id="0bb01-123">示例 2</span><span class="sxs-lookup"><span data-stu-id="0bb01-123">Example 2</span></span>

<span data-ttu-id="0bb01-124">ANG360(-9.8 rad)</span><span class="sxs-lookup"><span data-stu-id="0bb01-124">ANG360(-9.8 rad)</span></span>
  
<span data-ttu-id="0bb01-125">返回 2.7664 弧度</span><span class="sxs-lookup"><span data-stu-id="0bb01-125">Returns 2.7664 rad</span></span>
  
## <a name="example-3"></a><span data-ttu-id="0bb01-126">示例 3</span><span class="sxs-lookup"><span data-stu-id="0bb01-126">Example 3</span></span>

<span data-ttu-id="0bb01-127">ANG360 (45)</span><span class="sxs-lookup"><span data-stu-id="0bb01-127">ANG360(45)</span></span>
  
<span data-ttu-id="0bb01-128">返回 58.31 度（1.0177 弧度）</span><span class="sxs-lookup"><span data-stu-id="0bb01-128">Returns 58.31 deg (1.0177 rad)</span></span>
  

