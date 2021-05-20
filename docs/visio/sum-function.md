---
title: SUM 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251501
localization_priority: Normal
ms.assetid: fc97cef7-59c3-5be1-34fe-a40b4b33d1d6
description: 返回数字列表的总和。
ms.openlocfilehash: 749bf1620a26c6f4cf793a2f9e596d5720175be0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436312"
---
# <a name="sum-function"></a><span data-ttu-id="d3ec7-103">SUM 函数</span><span class="sxs-lookup"><span data-stu-id="d3ec7-103">SUM Function</span></span>

<span data-ttu-id="d3ec7-104">返回数字列表的总和。</span><span class="sxs-lookup"><span data-stu-id="d3ec7-104">Returns the sum of a list of numbers.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="d3ec7-105">语法</span><span class="sxs-lookup"><span data-stu-id="d3ec7-105">Syntax</span></span>

<span data-ttu-id="d3ec7-106">SUM (\*\* *number1* \*\*， \*\* *number2* \*\*,..., \*\* *[numberN]* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="d3ec7-106">SUM(\*\* *number1* \*\*, \*\* *number2* \*\*,..., \*\* *[numberN]* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="d3ec7-107">参数</span><span class="sxs-lookup"><span data-stu-id="d3ec7-107">Parameters</span></span>

|<span data-ttu-id="d3ec7-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-108">**Name**</span></span>|<span data-ttu-id="d3ec7-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-109">**Required/Optional**</span></span>|<span data-ttu-id="d3ec7-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-110">**Data Type**</span></span>|<span data-ttu-id="d3ec7-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d3ec7-112">_number1_</span><span class="sxs-lookup"><span data-stu-id="d3ec7-112">_number1_</span></span> <br/> |<span data-ttu-id="d3ec7-113">必需</span><span class="sxs-lookup"><span data-stu-id="d3ec7-113">Required</span></span>  <br/> |<span data-ttu-id="d3ec7-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-114">**Numeric**</span></span> <br/> |<span data-ttu-id="d3ec7-115">第一个数字。</span><span class="sxs-lookup"><span data-stu-id="d3ec7-115">The first number.</span></span>  <br/> |
| <span data-ttu-id="d3ec7-116">_number2_</span><span class="sxs-lookup"><span data-stu-id="d3ec7-116">_number2_</span></span> <br/> |<span data-ttu-id="d3ec7-117">必需</span><span class="sxs-lookup"><span data-stu-id="d3ec7-117">Required</span></span>  <br/> |<span data-ttu-id="d3ec7-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-118">**Numeric**</span></span> <br/> |<span data-ttu-id="d3ec7-119">第二个数字。</span><span class="sxs-lookup"><span data-stu-id="d3ec7-119">The second number.</span></span>  <br/> |
| <span data-ttu-id="d3ec7-120">_numberN_</span><span class="sxs-lookup"><span data-stu-id="d3ec7-120">_numberN_</span></span> <br/> |<span data-ttu-id="d3ec7-121">可选</span><span class="sxs-lookup"><span data-stu-id="d3ec7-121">Optional</span></span>  <br/> |<span data-ttu-id="d3ec7-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="d3ec7-122">**Numeric**</span></span> <br/> |<span data-ttu-id="d3ec7-123">第 n 个数字。</span><span class="sxs-lookup"><span data-stu-id="d3ec7-123">The nth number.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="d3ec7-124">返回值</span><span class="sxs-lookup"><span data-stu-id="d3ec7-124">Return value</span></span>

<span data-ttu-id="d3ec7-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="d3ec7-125">Numeric</span></span>
  
## <a name="example"></a><span data-ttu-id="d3ec7-126">示例</span><span class="sxs-lookup"><span data-stu-id="d3ec7-126">Example</span></span>

<span data-ttu-id="d3ec7-127">SUM (5，7，12) </span><span class="sxs-lookup"><span data-stu-id="d3ec7-127">SUM(5,7,12)</span></span>
  
<span data-ttu-id="d3ec7-128">返回 24。</span><span class="sxs-lookup"><span data-stu-id="d3ec7-128">Returns 24.</span></span>
  

