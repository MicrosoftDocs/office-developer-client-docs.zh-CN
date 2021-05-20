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
description: 返回一个数字的反正弦值，例如，其正弦值是数字的角度。
ms.openlocfilehash: e66ed9ab3d01ac79bceb18f5c793afc928e5e4b4
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293504"
---
# <a name="asin-function"></a><span data-ttu-id="8fe83-103">ASIN 函数</span><span class="sxs-lookup"><span data-stu-id="8fe83-103">ASIN Function</span></span>

<span data-ttu-id="8fe83-104">返回一个数字的反正弦值，例如，其正弦值是  *数字的角度*  。</span><span class="sxs-lookup"><span data-stu-id="8fe83-104">Returns the arcsine of a number, for example, the angle whose sine is  *number*  .</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="8fe83-105">语法</span><span class="sxs-lookup"><span data-stu-id="8fe83-105">Syntax</span></span>

<span data-ttu-id="8fe83-106">ASIN (***号码*** ) </span><span class="sxs-lookup"><span data-stu-id="8fe83-106">ASIN(***number*** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="8fe83-107">参数</span><span class="sxs-lookup"><span data-stu-id="8fe83-107">Parameters</span></span>

|<span data-ttu-id="8fe83-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="8fe83-108">**Name**</span></span>|<span data-ttu-id="8fe83-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="8fe83-109">**Required/Optional**</span></span>|<span data-ttu-id="8fe83-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8fe83-110">**Data Type**</span></span>|<span data-ttu-id="8fe83-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="8fe83-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8fe83-112">_number_</span><span class="sxs-lookup"><span data-stu-id="8fe83-112">_number_</span></span> <br/> |<span data-ttu-id="8fe83-113">必需</span><span class="sxs-lookup"><span data-stu-id="8fe83-113">Required</span></span>  <br/> |<span data-ttu-id="8fe83-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="8fe83-114">**Numeric**</span></span> <br/> |<span data-ttu-id="8fe83-115">角度的正弦值。</span><span class="sxs-lookup"><span data-stu-id="8fe83-115">The sine of the angle.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8fe83-116">备注</span><span class="sxs-lookup"><span data-stu-id="8fe83-116">Remarks</span></span>

<span data-ttu-id="8fe83-117">输入值的范围必须为 -1 <=  *number*  <= 1，否则为 #NUM！</span><span class="sxs-lookup"><span data-stu-id="8fe83-117">The input value must be in the range -1 <=  *number*  <= 1, or a #NUM!</span></span> <span data-ttu-id="8fe83-118">错误。</span><span class="sxs-lookup"><span data-stu-id="8fe83-118">error is returned.</span></span> <span data-ttu-id="8fe83-119">结果角度的范围为 -PI/2 <=  *角度*  <= PI/2 弧度 (-90 < *=*  角度 <= 90 度) 。</span><span class="sxs-lookup"><span data-stu-id="8fe83-119">The resulting angle is in the range -PI/2 <=  *angle*  <= PI/2 radians (-90 <=  *angle*  <= 90 degrees).</span></span> 
  
## <a name="example"></a><span data-ttu-id="8fe83-120">示例</span><span class="sxs-lookup"><span data-stu-id="8fe83-120">Example</span></span>

<span data-ttu-id="8fe83-121">ASIN (1) </span><span class="sxs-lookup"><span data-stu-id="8fe83-121">ASIN(1)</span></span>
  
<span data-ttu-id="8fe83-122">返回 90 度</span><span class="sxs-lookup"><span data-stu-id="8fe83-122">Returns 90 deg</span></span>
  

