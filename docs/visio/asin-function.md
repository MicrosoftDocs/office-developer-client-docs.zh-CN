---
title: ASIN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251395
localization_priority: Normal
ms.assetid: 7d917be4-65b1-002f-48cc-6d81916a1157
description: 返回一个数字，例如，正弦值为 number 的角度的反正弦。
ms.openlocfilehash: e5ed8f9fc8c85ac4816fede03bfe6f6af5cbf5f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779677"
---
# <a name="asin-function"></a><span data-ttu-id="62fd8-103">ASIN 函数</span><span class="sxs-lookup"><span data-stu-id="62fd8-103">ASIN Function</span></span>

<span data-ttu-id="62fd8-104">返回一个数字，例如，正弦为*数字*的角度的反正弦。</span><span class="sxs-lookup"><span data-stu-id="62fd8-104">Returns the arcsine of a number, for example, the angle whose sine is  *number*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="62fd8-105">语法</span><span class="sxs-lookup"><span data-stu-id="62fd8-105">Syntax</span></span>

<span data-ttu-id="62fd8-106">ASIN (* **数量** *)</span><span class="sxs-lookup"><span data-stu-id="62fd8-106">ASIN(** *number* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="62fd8-107">参数</span><span class="sxs-lookup"><span data-stu-id="62fd8-107">Parameters</span></span>

|<span data-ttu-id="62fd8-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="62fd8-108">**Name**</span></span>|<span data-ttu-id="62fd8-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="62fd8-109">**Required/Optional**</span></span>|<span data-ttu-id="62fd8-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="62fd8-110">**Data Type**</span></span>|<span data-ttu-id="62fd8-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="62fd8-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="62fd8-112">_number_</span><span class="sxs-lookup"><span data-stu-id="62fd8-112">_number_</span></span> <br/> |<span data-ttu-id="62fd8-113">必需</span><span class="sxs-lookup"><span data-stu-id="62fd8-113">Required</span></span>  <br/> |<span data-ttu-id="62fd8-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="62fd8-114">**Numeric**</span></span> <br/> |<span data-ttu-id="62fd8-115">角度的正弦值。</span><span class="sxs-lookup"><span data-stu-id="62fd8-115">The sine of the angle.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="62fd8-116">注解</span><span class="sxs-lookup"><span data-stu-id="62fd8-116">Remarks</span></span>

<span data-ttu-id="62fd8-117">输入的值必须位于范围介于-1 < =*号码*< = 1 或 #NUM ！</span><span class="sxs-lookup"><span data-stu-id="62fd8-117">The input value must be in the range -1 <=  *number*  <= 1, or a #NUM!</span></span> <span data-ttu-id="62fd8-118">将返回错误。</span><span class="sxs-lookup"><span data-stu-id="62fd8-118">error is returned.</span></span> <span data-ttu-id="62fd8-119">生成的角度位于范围-PI/2 < =*角度*< = PI/2 弧度 (-90 < =*角度*< = 90 度)。</span><span class="sxs-lookup"><span data-stu-id="62fd8-119">The resulting angle is in the range -PI/2 <=  *angle*  <= PI/2 radians (-90 <=  *angle*  <= 90 degrees).</span></span> 
  
## <a name="example"></a><span data-ttu-id="62fd8-120">示例</span><span class="sxs-lookup"><span data-stu-id="62fd8-120">Example</span></span>

<span data-ttu-id="62fd8-121">ASIN(1)</span><span class="sxs-lookup"><span data-stu-id="62fd8-121">ASIN(1)</span></span>
  
<span data-ttu-id="62fd8-122">返回 90 度</span><span class="sxs-lookup"><span data-stu-id="62fd8-122">Returns 90 deg</span></span>
  

