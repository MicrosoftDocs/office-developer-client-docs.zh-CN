---
title: TIME Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251506
localization_priority: Normal
ms.assetid: 2e662230-0760-5f43-52dc-927f499715f6
description: 返回时间表示的小时、 分钟和秒。
ms.openlocfilehash: 4390e0cdccf0ae7798d5ada4329a28f72566ecac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781536"
---
# <a name="time-function-visioshapesheet"></a><span data-ttu-id="3eb40-103">TIME Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="3eb40-103">TIME Function (VisioShapeSheet)</span></span>

<span data-ttu-id="3eb40-104">返回由_小时_、_分钟_和_秒_的时间。</span><span class="sxs-lookup"><span data-stu-id="3eb40-104">Returns the time represented by  _hour_,  _minute_, and  _second_.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3eb40-105">语法</span><span class="sxs-lookup"><span data-stu-id="3eb40-105">Syntax</span></span>

<span data-ttu-id="3eb40-106">时间 (* **小时** *，* **分钟** *，* **第二个** *)</span><span class="sxs-lookup"><span data-stu-id="3eb40-106">TIME(** *hour* **, ** *minute* **, ** *second* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="3eb40-107">参数</span><span class="sxs-lookup"><span data-stu-id="3eb40-107">Parameters</span></span>

|<span data-ttu-id="3eb40-108">**名称**</span><span class="sxs-lookup"><span data-stu-id="3eb40-108">**Name**</span></span>|<span data-ttu-id="3eb40-109">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="3eb40-109">**Required/Optional**</span></span>|<span data-ttu-id="3eb40-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3eb40-110">**Data Type**</span></span>|<span data-ttu-id="3eb40-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="3eb40-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3eb40-112">_小时_</span><span class="sxs-lookup"><span data-stu-id="3eb40-112">_hour_</span></span> <br/> |<span data-ttu-id="3eb40-113">必需</span><span class="sxs-lookup"><span data-stu-id="3eb40-113">Required</span></span>  <br/> |<span data-ttu-id="3eb40-114">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="3eb40-114">**Numeric**</span></span> <br/> |<span data-ttu-id="3eb40-115">小时成分。</span><span class="sxs-lookup"><span data-stu-id="3eb40-115">The hour component.</span></span>  <br/> |
| <span data-ttu-id="3eb40-116">_分钟_</span><span class="sxs-lookup"><span data-stu-id="3eb40-116">_minute_</span></span> <br/> |<span data-ttu-id="3eb40-117">必需</span><span class="sxs-lookup"><span data-stu-id="3eb40-117">Required</span></span>  <br/> |<span data-ttu-id="3eb40-118">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="3eb40-118">**Numeric**</span></span> <br/> |<span data-ttu-id="3eb40-119">分钟成分。</span><span class="sxs-lookup"><span data-stu-id="3eb40-119">The minute comonent.</span></span>  <br/> |
| <span data-ttu-id="3eb40-120">_第二个_</span><span class="sxs-lookup"><span data-stu-id="3eb40-120">_second_</span></span> <br/> |<span data-ttu-id="3eb40-121">必需</span><span class="sxs-lookup"><span data-stu-id="3eb40-121">Required</span></span>  <br/> |<span data-ttu-id="3eb40-122">**Numeric**</span><span class="sxs-lookup"><span data-stu-id="3eb40-122">**Numeric**</span></span> <br/> |<span data-ttu-id="3eb40-123">秒成分。</span><span class="sxs-lookup"><span data-stu-id="3eb40-123">The second component.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="3eb40-124">返回值</span><span class="sxs-lookup"><span data-stu-id="3eb40-124">Return value</span></span>

<span data-ttu-id="3eb40-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="3eb40-125">Numeric</span></span>
  
## <a name="example-1"></a><span data-ttu-id="3eb40-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="3eb40-126">Example 1</span></span>

<span data-ttu-id="3eb40-127">TIME(15,30,30)</span><span class="sxs-lookup"><span data-stu-id="3eb40-127">TIME(15,30,30)</span></span>
  
<span data-ttu-id="3eb40-128">返回表示下午 3:30:30 的值。</span><span class="sxs-lookup"><span data-stu-id="3eb40-128">Returns the value representing 15:30:30.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="3eb40-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="3eb40-129">Example 2</span></span>

<span data-ttu-id="3eb40-130">FORMAT(TIME(15,30,30),"HH:mm")</span><span class="sxs-lookup"><span data-stu-id="3eb40-130">FORMAT(TIME(15,30,30),"HH:mm")</span></span>
  
<span data-ttu-id="3eb40-131">返回表示 15:30 的值。</span><span class="sxs-lookup"><span data-stu-id="3eb40-131">Returns the value representing 15:30.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="3eb40-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="3eb40-132">Example 3</span></span>

<span data-ttu-id="3eb40-133">TIME(15,30,30) + 8 eh.</span><span class="sxs-lookup"><span data-stu-id="3eb40-133">TIME(15,30,30) + 8 eh.</span></span>
  
<span data-ttu-id="3eb40-134">返回表示午夜 11:30:30 的值。</span><span class="sxs-lookup"><span data-stu-id="3eb40-134">Returns the value representing 23:30:30.</span></span>
  

