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
description: 返回以年、月和日表示的日期, 根据系统区域设置中的短日期样式的格式设置。 年、月和日的值反映公历日历。
ms.openlocfilehash: 0175c1f06ec3dbdf89774759546c65994d38105e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360331"
---
# <a name="date-function-visioshapesheet"></a><span data-ttu-id="45b48-104">DATE 函数 (VisioShapeSheet)</span><span class="sxs-lookup"><span data-stu-id="45b48-104">DATE Function (VisioShapeSheet)</span></span>

<span data-ttu-id="45b48-105">返回以*年、月*和*日*表示的日期, 根据系统区域设置中的短日期样式的格式设置。</span><span class="sxs-lookup"><span data-stu-id="45b48-105">Returns the date represented by  *year, month,*  and  *day*  formatted according to the short date style in the system's Regional Settings.</span></span> <span data-ttu-id="45b48-106">*年*、*月*和*日*的值反映公历日历。</span><span class="sxs-lookup"><span data-stu-id="45b48-106">The values for  *year*, *month*  , and  *day*  reflect the Gregorian calendar.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="45b48-107">语法</span><span class="sxs-lookup"><span data-stu-id="45b48-107">Syntax</span></span>

<span data-ttu-id="45b48-108">DATE (\* **年** *、* **月** *、* **日** \*)</span><span class="sxs-lookup"><span data-stu-id="45b48-108">DATE(\*\* *year* \*\*, \*\* *month* \*\*, \*\* *day* \*\* )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="45b48-109">参数</span><span class="sxs-lookup"><span data-stu-id="45b48-109">Parameters</span></span>

|<span data-ttu-id="45b48-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="45b48-110">**Name**</span></span>|<span data-ttu-id="45b48-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="45b48-111">**Required/Optional**</span></span>|<span data-ttu-id="45b48-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="45b48-112">**Data Type**</span></span>|<span data-ttu-id="45b48-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="45b48-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="45b48-114">_year_</span><span class="sxs-lookup"><span data-stu-id="45b48-114">_year_</span></span> <br/> |<span data-ttu-id="45b48-115">必需</span><span class="sxs-lookup"><span data-stu-id="45b48-115">Required</span></span>  <br/> |<span data-ttu-id="45b48-116">**Integer**</span><span class="sxs-lookup"><span data-stu-id="45b48-116">**Integer**</span></span> <br/> |<span data-ttu-id="45b48-117">年份。</span><span class="sxs-lookup"><span data-stu-id="45b48-117">The year.</span></span>  <br/> |
| <span data-ttu-id="45b48-118">_month_</span><span class="sxs-lookup"><span data-stu-id="45b48-118">_month_</span></span> <br/> |<span data-ttu-id="45b48-119">必需</span><span class="sxs-lookup"><span data-stu-id="45b48-119">Required</span></span>  <br/> |<span data-ttu-id="45b48-120">**Integer**</span><span class="sxs-lookup"><span data-stu-id="45b48-120">**Integer**</span></span> <br/> |<span data-ttu-id="45b48-121">月份。</span><span class="sxs-lookup"><span data-stu-id="45b48-121">The month.</span></span>  <br/> |
| <span data-ttu-id="45b48-122">_为期_</span><span class="sxs-lookup"><span data-stu-id="45b48-122">_day_</span></span> <br/> |<span data-ttu-id="45b48-123">必需</span><span class="sxs-lookup"><span data-stu-id="45b48-123">Required</span></span>  <br/> |<span data-ttu-id="45b48-124">**Integer**</span><span class="sxs-lookup"><span data-stu-id="45b48-124">**Integer**</span></span> <br/> |<span data-ttu-id="45b48-125">日期。</span><span class="sxs-lookup"><span data-stu-id="45b48-125">The day.</span></span>  <br/> |
   
## <a name="example-1"></a><span data-ttu-id="45b48-126">示例 1</span><span class="sxs-lookup"><span data-stu-id="45b48-126">Example 1</span></span>

<span data-ttu-id="45b48-127">日期 (1999、6、7)</span><span class="sxs-lookup"><span data-stu-id="45b48-127">DATE(1999,6,7)</span></span>
  
<span data-ttu-id="45b48-128">返回表示 6/7/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="45b48-128">Returns the value representing 6/7/1999.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="45b48-129">示例 2</span><span class="sxs-lookup"><span data-stu-id="45b48-129">Example 2</span></span>

<span data-ttu-id="45b48-130">DATE(1999,6,7) + 4 ed.</span><span class="sxs-lookup"><span data-stu-id="45b48-130">DATE(1999,6,7) + 4 ed.</span></span>
  
<span data-ttu-id="45b48-131">返回表示 6/11/1999 的值。</span><span class="sxs-lookup"><span data-stu-id="45b48-131">Returns the value representing 6/11/1999.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="45b48-132">示例 3</span><span class="sxs-lookup"><span data-stu-id="45b48-132">Example 3</span></span>

<span data-ttu-id="45b48-133">FORMAT (DATE (1999、10、14)、"C")</span><span class="sxs-lookup"><span data-stu-id="45b48-133">FORMAT(DATE(1999,10,14),"C")</span></span>
  
<span data-ttu-id="45b48-134">返回表示 Tuesday, October 14, 1999 的值。</span><span class="sxs-lookup"><span data-stu-id="45b48-134">Returns the value representing Tuesday, October 14, 1999.</span></span>
  

