---
title: DATE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251412
localization_priority: Normal
ms.assetid: 2b6c5375-c543-ff2f-f20a-6d92fd65717a
description: 返回由年、月、日表示的日期，这些日期的格式根据系统的"区域"样式中的短日期设置。 年、月和日的值反映公历。
ms.openlocfilehash: 0175c1f06ec3dbdf89774759546c65994d38105e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360331"
---
# <a name="date-function-visioshapesheet"></a><span data-ttu-id="ffbe2-104">DATE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="ffbe2-104">DATE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="ffbe2-105">返回由年、*月*、日表示的日期，它们根据系统的"区域"样式中的短日期样式设置。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-105">Returns the date represented by  *year, month,*  and  *day*  formatted according to the short date style in the system's Regional Settings.</span></span> <span data-ttu-id="ffbe2-106">年 *、**月和**日* 的值反映公历。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-106">The values for  *year*, *month*  , and  *day*  reflect the Gregorian calendar.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="ffbe2-107">语法</span><span class="sxs-lookup"><span data-stu-id="ffbe2-107">Syntax</span></span>

<span data-ttu-id="ffbe2-108">DATE (\*\* *year* \*\*， \*\* *month* \*\*， \*\* *day* \*\* ) </span><span class="sxs-lookup"><span data-stu-id="ffbe2-108">DATE(\*\* *year* \*\*, \*\* *month* \*\*, \*\* *day* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="ffbe2-109">参数</span><span class="sxs-lookup"><span data-stu-id="ffbe2-109">Parameters</span></span>

|<span data-ttu-id="ffbe2-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-110">**Name**</span></span>|<span data-ttu-id="ffbe2-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-111">**Required/Optional**</span></span>|<span data-ttu-id="ffbe2-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-112">**Data Type**</span></span>|<span data-ttu-id="ffbe2-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ffbe2-114">_year_</span><span class="sxs-lookup"><span data-stu-id="ffbe2-114">_year_</span></span> <br/> |<span data-ttu-id="ffbe2-115">必需</span><span class="sxs-lookup"><span data-stu-id="ffbe2-115">Required</span></span>  <br/> |<span data-ttu-id="ffbe2-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-116">**Integer**</span></span> <br/> |<span data-ttu-id="ffbe2-117">年份。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-117">The year.</span></span>  <br/> |
| <span data-ttu-id="ffbe2-118">_month_</span><span class="sxs-lookup"><span data-stu-id="ffbe2-118">_month_</span></span> <br/> |<span data-ttu-id="ffbe2-119">必需</span><span class="sxs-lookup"><span data-stu-id="ffbe2-119">Required</span></span>  <br/> |<span data-ttu-id="ffbe2-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-120">**Integer**</span></span> <br/> |<span data-ttu-id="ffbe2-121">月份。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-121">The month.</span></span>  <br/> |
| <span data-ttu-id="ffbe2-122">_day_</span><span class="sxs-lookup"><span data-stu-id="ffbe2-122">_day_</span></span> <br/> |<span data-ttu-id="ffbe2-123">必需</span><span class="sxs-lookup"><span data-stu-id="ffbe2-123">Required</span></span>  <br/> |<span data-ttu-id="ffbe2-124">**Integer**</span><span class="sxs-lookup"><span data-stu-id="ffbe2-124">**Integer**</span></span> <br/> |<span data-ttu-id="ffbe2-125">日期。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-125">The day.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="ffbe2-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="ffbe2-126">Example 1</span></span>

<span data-ttu-id="ffbe2-127">DATE (1999，6，7) </span><span class="sxs-lookup"><span data-stu-id="ffbe2-127">DATE(1999,6,7)</span></span>
  
<span data-ttu-id="ffbe2-128">返回表示 6/7/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-128">Returns the value representing 6/7/1999.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="ffbe2-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="ffbe2-129">Example 2</span></span>

<span data-ttu-id="ffbe2-130">DATE(1999,6,7) + 4 ed.</span><span class="sxs-lookup"><span data-stu-id="ffbe2-130">DATE(1999,6,7) + 4 ed.</span></span>
  
<span data-ttu-id="ffbe2-131">返回表示 6/11/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-131">Returns the value representing 6/11/1999.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="ffbe2-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="ffbe2-132">Example 3</span></span>

<span data-ttu-id="ffbe2-133">FORMAT (DATE (1999，10，14) ，"C") </span><span class="sxs-lookup"><span data-stu-id="ffbe2-133">FORMAT(DATE(1999,10,14),"C")</span></span>
  
<span data-ttu-id="ffbe2-134">返回表示 Tuesday, October 14, 1999 的值。</span><span class="sxs-lookup"><span data-stu-id="ffbe2-134">Returns the value representing Tuesday, October 14, 1999.</span></span>
  

