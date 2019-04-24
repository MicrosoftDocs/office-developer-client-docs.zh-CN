---
title: MIN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251463
localization_priority: Normal
ms.assetid: b945b7c2-153f-2fc3-b768-1e975254ddf5
description: 返回列表中的最小数字。 最小表示最接近无穷大负数。
ms.openlocfilehash: 7c9eb1a8d4ce30e7ab9253c2864ecd38474e8ff6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360646"
---
# <a name="min-function"></a><span data-ttu-id="06a9a-104">MIN 函数</span><span class="sxs-lookup"><span data-stu-id="06a9a-104">MIN Function</span></span>

<span data-ttu-id="06a9a-105">返回列表中的最小数字。</span><span class="sxs-lookup"><span data-stu-id="06a9a-105">Returns the smallest number from a list.</span></span> <span data-ttu-id="06a9a-106">最小表示最接近无穷大负数。</span><span class="sxs-lookup"><span data-stu-id="06a9a-106">Smallest means closest to negative infinity.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="06a9a-107">语法</span><span class="sxs-lookup"><span data-stu-id="06a9a-107">Syntax</span></span>

<span data-ttu-id="06a9a-108">MIN (\* \* *1-1* \* \*, \* \**数字 2* \* \*,..., \* \* *numberN* \* \*)</span><span class="sxs-lookup"><span data-stu-id="06a9a-108">MIN(\*\* *number1* \*\*, \*\* *number2* \*\*,..., \*\* *numberN* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="06a9a-109">参数</span><span class="sxs-lookup"><span data-stu-id="06a9a-109">Parameters</span></span>

|<span data-ttu-id="06a9a-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="06a9a-110">**Name**</span></span>|<span data-ttu-id="06a9a-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="06a9a-111">**Required/Optional**</span></span>|<span data-ttu-id="06a9a-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="06a9a-112">**Data Type**</span></span>|<span data-ttu-id="06a9a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="06a9a-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="06a9a-114">_number1_</span><span class="sxs-lookup"><span data-stu-id="06a9a-114">_number1_</span></span> <br/> |<span data-ttu-id="06a9a-115">必需</span><span class="sxs-lookup"><span data-stu-id="06a9a-115">Required</span></span>  <br/> |<span data-ttu-id="06a9a-116">**相同**</span><span class="sxs-lookup"><span data-stu-id="06a9a-116">**Varies**</span></span> <br/> |<span data-ttu-id="06a9a-117">列表中的第一个数字。</span><span class="sxs-lookup"><span data-stu-id="06a9a-117">The first number in the list.</span></span>  <br/> |
| <span data-ttu-id="06a9a-118">_number2_</span><span class="sxs-lookup"><span data-stu-id="06a9a-118">_number2_</span></span> <br/> |<span data-ttu-id="06a9a-119">可选</span><span class="sxs-lookup"><span data-stu-id="06a9a-119">Optional</span></span>  <br/> |<span data-ttu-id="06a9a-120">**相同**</span><span class="sxs-lookup"><span data-stu-id="06a9a-120">**Varies**</span></span> <br/> | <span data-ttu-id="06a9a-121">列表中的第二个数字。</span><span class="sxs-lookup"><span data-stu-id="06a9a-121">The second number in the list.</span></span>  <br/> |
| <span data-ttu-id="06a9a-122">_numberN_</span><span class="sxs-lookup"><span data-stu-id="06a9a-122">_numberN_</span></span> <br/> |<span data-ttu-id="06a9a-123">可选</span><span class="sxs-lookup"><span data-stu-id="06a9a-123">Optional</span></span>  <br/> |<span data-ttu-id="06a9a-124">**相同**</span><span class="sxs-lookup"><span data-stu-id="06a9a-124">**Varies**</span></span> <br/> |<span data-ttu-id="06a9a-125">列表中的第 n 个数字。</span><span class="sxs-lookup"><span data-stu-id="06a9a-125">The nth number in the list.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="06a9a-126">返回值</span><span class="sxs-lookup"><span data-stu-id="06a9a-126">Return value</span></span>

<span data-ttu-id="06a9a-127">各不相同</span><span class="sxs-lookup"><span data-stu-id="06a9a-127">Varies</span></span>
  
## <a name="example"></a><span data-ttu-id="06a9a-128">示例</span><span class="sxs-lookup"><span data-stu-id="06a9a-128">Example</span></span>

<span data-ttu-id="06a9a-129">MIN (13 in, 1 英尺, 20 厘米)</span><span class="sxs-lookup"><span data-stu-id="06a9a-129">MIN(13 in,1 ft, 20 cm)</span></span> 
  
<span data-ttu-id="06a9a-130">返回20厘米。</span><span class="sxs-lookup"><span data-stu-id="06a9a-130">Returns 20 centimeters.</span></span> 
  

