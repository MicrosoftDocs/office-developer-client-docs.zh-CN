---
title: TIME 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251506
localization_priority: Normal
ms.assetid: 2e662230-0760-5f43-52dc-927f499715f6
description: 返回以小时、分钟和秒表示的时间。
ms.openlocfilehash: f5be55d7e63a70d15da49c68b924cc5b03c5ca88
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280995"
---
# <a name="time-function-visioshapesheet"></a><span data-ttu-id="c583c-103">TIME 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="c583c-103">TIME Function (VisioShapeSheet)</span></span>

<span data-ttu-id="c583c-104">返回以_小时_、_分钟_和_秒_表示的时间。</span><span class="sxs-lookup"><span data-stu-id="c583c-104">Returns the time represented by  _hour_,  _minute_, and  _second_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c583c-105">语法</span><span class="sxs-lookup"><span data-stu-id="c583c-105">Syntax</span></span>

<span data-ttu-id="c583c-106">TIME (\* \* *hour* \* *、* \* *minute* \* *、* \* *second* \* \*)</span><span class="sxs-lookup"><span data-stu-id="c583c-106">TIME(\*\* *hour* \*\*, \*\* *minute* \*\*, \*\* *second* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="c583c-107">参数</span><span class="sxs-lookup"><span data-stu-id="c583c-107">Parameters</span></span>

|<span data-ttu-id="c583c-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="c583c-108">**Name**</span></span>|<span data-ttu-id="c583c-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="c583c-109">**Required/Optional**</span></span>|<span data-ttu-id="c583c-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c583c-110">**Data Type**</span></span>|<span data-ttu-id="c583c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c583c-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c583c-112">_七点_</span><span class="sxs-lookup"><span data-stu-id="c583c-112">_hour_</span></span> <br/> |<span data-ttu-id="c583c-113">必需</span><span class="sxs-lookup"><span data-stu-id="c583c-113">Required</span></span>  <br/> |<span data-ttu-id="c583c-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="c583c-114">**Numeric**</span></span> <br/> |<span data-ttu-id="c583c-115">小时成分。</span><span class="sxs-lookup"><span data-stu-id="c583c-115">The hour component.</span></span>  <br/> |
| <span data-ttu-id="c583c-116">_还要_</span><span class="sxs-lookup"><span data-stu-id="c583c-116">_minute_</span></span> <br/> |<span data-ttu-id="c583c-117">必需</span><span class="sxs-lookup"><span data-stu-id="c583c-117">Required</span></span>  <br/> |<span data-ttu-id="c583c-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="c583c-118">**Numeric**</span></span> <br/> |<span data-ttu-id="c583c-119">分钟成分。</span><span class="sxs-lookup"><span data-stu-id="c583c-119">The minute comonent.</span></span>  <br/> |
| <span data-ttu-id="c583c-120">_第二个_</span><span class="sxs-lookup"><span data-stu-id="c583c-120">_second_</span></span> <br/> |<span data-ttu-id="c583c-121">必需</span><span class="sxs-lookup"><span data-stu-id="c583c-121">Required</span></span>  <br/> |<span data-ttu-id="c583c-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="c583c-122">**Numeric**</span></span> <br/> |<span data-ttu-id="c583c-123">秒成分。</span><span class="sxs-lookup"><span data-stu-id="c583c-123">The second component.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="c583c-124">返回值</span><span class="sxs-lookup"><span data-stu-id="c583c-124">Return value</span></span>

<span data-ttu-id="c583c-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="c583c-125">Numeric</span></span>
  
## <a name="example-1"></a><span data-ttu-id="c583c-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="c583c-126">Example 1</span></span>

<span data-ttu-id="c583c-127">时间 (15、30、30)</span><span class="sxs-lookup"><span data-stu-id="c583c-127">TIME(15,30,30)</span></span>
  
<span data-ttu-id="c583c-128">返回表示下午 3:30:30 的值。</span><span class="sxs-lookup"><span data-stu-id="c583c-128">Returns the value representing 15:30:30.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="c583c-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="c583c-129">Example 2</span></span>

<span data-ttu-id="c583c-130">FORMAT (TIME (15, 30, 30), "HH: mm")</span><span class="sxs-lookup"><span data-stu-id="c583c-130">FORMAT(TIME(15,30,30),"HH:mm")</span></span>
  
<span data-ttu-id="c583c-131">返回表示 15:30 的值。</span><span class="sxs-lookup"><span data-stu-id="c583c-131">Returns the value representing 15:30.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="c583c-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="c583c-132">Example 3</span></span>

<span data-ttu-id="c583c-133">TIME(15,30,30) + 8 eh.</span><span class="sxs-lookup"><span data-stu-id="c583c-133">TIME(15,30,30) + 8 eh.</span></span>
  
<span data-ttu-id="c583c-134">返回表示午夜 11:30:30 的值。</span><span class="sxs-lookup"><span data-stu-id="c583c-134">Returns the value representing 23:30:30.</span></span>
  

