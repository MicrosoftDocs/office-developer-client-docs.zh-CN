---
title: DATE Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251412
localization_priority: Normal
ms.assetid: 2b6c5375-c543-ff2f-f20a-6d92fd65717a
description: 返回表示由年、 月和日的日期根据系统的区域设置中的短日期样式设置格式。 为年、 月和日值反映公历。
ms.openlocfilehash: 7a19d97f70f9314ecdbd2228078e1e18b1ac9146
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780058"
---
# <a name="date-function-visioshapesheet"></a><span data-ttu-id="6aeca-104">DATE Function (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="6aeca-104">DATE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="6aeca-105">返回表示*年、 月*和*日*的日期根据系统的区域设置中的短日期样式设置格式。</span><span class="sxs-lookup"><span data-stu-id="6aeca-105">Returns the date represented by  *year, month,*  and  *day*  formatted according to the short date style in the system's Regional Settings.</span></span> <span data-ttu-id="6aeca-106">为*年*、*月*和*日*值反映公历。</span><span class="sxs-lookup"><span data-stu-id="6aeca-106">The values for  *year*, *month*  , and  *day*  reflect the Gregorian calendar.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="6aeca-107">语法</span><span class="sxs-lookup"><span data-stu-id="6aeca-107">Syntax</span></span>

<span data-ttu-id="6aeca-108">日期 (* **年** *，* **月** *，* **天** *)</span><span class="sxs-lookup"><span data-stu-id="6aeca-108">DATE(** *year* **, ** *month* **, ** *day* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="6aeca-109">参数</span><span class="sxs-lookup"><span data-stu-id="6aeca-109">Parameters</span></span>

|<span data-ttu-id="6aeca-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="6aeca-110">**Name**</span></span>|<span data-ttu-id="6aeca-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="6aeca-111">**Required/Optional**</span></span>|<span data-ttu-id="6aeca-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6aeca-112">**Data Type**</span></span>|<span data-ttu-id="6aeca-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="6aeca-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="6aeca-114">_year_</span><span class="sxs-lookup"><span data-stu-id="6aeca-114">_year_</span></span> <br/> |<span data-ttu-id="6aeca-115">必需</span><span class="sxs-lookup"><span data-stu-id="6aeca-115">Required</span></span>  <br/> |<span data-ttu-id="6aeca-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6aeca-116">**Integer**</span></span> <br/> |<span data-ttu-id="6aeca-117">年份。</span><span class="sxs-lookup"><span data-stu-id="6aeca-117">The year.</span></span>  <br/> |
| <span data-ttu-id="6aeca-118">_month_</span><span class="sxs-lookup"><span data-stu-id="6aeca-118">_month_</span></span> <br/> |<span data-ttu-id="6aeca-119">必需</span><span class="sxs-lookup"><span data-stu-id="6aeca-119">Required</span></span>  <br/> |<span data-ttu-id="6aeca-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6aeca-120">**Integer**</span></span> <br/> |<span data-ttu-id="6aeca-121">月份。</span><span class="sxs-lookup"><span data-stu-id="6aeca-121">The month.</span></span>  <br/> |
| <span data-ttu-id="6aeca-122">_一天_</span><span class="sxs-lookup"><span data-stu-id="6aeca-122">_day_</span></span> <br/> |<span data-ttu-id="6aeca-123">必需</span><span class="sxs-lookup"><span data-stu-id="6aeca-123">Required</span></span>  <br/> |<span data-ttu-id="6aeca-124">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6aeca-124">**Integer**</span></span> <br/> |<span data-ttu-id="6aeca-125">日期。</span><span class="sxs-lookup"><span data-stu-id="6aeca-125">The day.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="6aeca-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="6aeca-126">Example 1</span></span>

<span data-ttu-id="6aeca-127">DATE(1999,6,7)</span><span class="sxs-lookup"><span data-stu-id="6aeca-127">DATE(1999,6,7)</span></span>
  
<span data-ttu-id="6aeca-128">返回表示 6/7/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="6aeca-128">Returns the value representing 6/7/1999.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="6aeca-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="6aeca-129">Example 2</span></span>

<span data-ttu-id="6aeca-130">DATE(1999,6,7) + 4 ed.</span><span class="sxs-lookup"><span data-stu-id="6aeca-130">DATE(1999,6,7) + 4 ed.</span></span>
  
<span data-ttu-id="6aeca-131">返回表示 6/11/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="6aeca-131">Returns the value representing 6/11/1999.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="6aeca-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="6aeca-132">Example 3</span></span>

<span data-ttu-id="6aeca-133">FORMAT(DATE(1999,10,14),"C")</span><span class="sxs-lookup"><span data-stu-id="6aeca-133">FORMAT(DATE(1999,10,14),"C")</span></span>
  
<span data-ttu-id="6aeca-134">返回表示 Tuesday, October 14, 1999 的值。</span><span class="sxs-lookup"><span data-stu-id="6aeca-134">Returns the value representing Tuesday, October 14, 1999.</span></span>
  

