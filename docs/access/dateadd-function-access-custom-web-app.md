---
title: DateAdd 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回一个指定的数字间隔 (正或负整数) 添加到该日期的指定日期部分的指定日期。
ms.openlocfilehash: 7cfd68c4983eee22a5e542facd72ea083deb3184
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282178"
---
# <a name="dateadd-function-access-custom-web-app"></a><span data-ttu-id="13ce4-103">DateAdd 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="13ce4-103">DateAdd function (Access custom web app)</span></span>

<span data-ttu-id="13ce4-104">返回一个指定的数字间隔 (正或负整数) 添加到该日期的指定日期部分的指定日期。</span><span class="sxs-lookup"><span data-stu-id="13ce4-104">Returns a specified date with the specified number interval (positive or negative integer) added to a specified date part of that date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13ce4-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="13ce4-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="13ce4-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="13ce4-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="13ce4-107">语法</span><span class="sxs-lookup"><span data-stu-id="13ce4-107">Syntax</span></span>

<span data-ttu-id="13ce4-108">**DateAdd**(*DatePart*、 *Number*、 *Date*)</span><span class="sxs-lookup"><span data-stu-id="13ce4-108">**DateAdd** (*DatePart*, *Number*, *Date*)</span></span> 
  
<span data-ttu-id="13ce4-109">**DateAdd**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="13ce4-109">The **DateAdd** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="13ce4-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="13ce4-110">**Argument name**</span></span>|<span data-ttu-id="13ce4-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="13ce4-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="13ce4-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="13ce4-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="13ce4-113">要向其中添加整数的*日期*部分。</span><span class="sxs-lookup"><span data-stu-id="13ce4-113">The part of  *Date*  to which an integer number is added.</span></span> <span data-ttu-id="13ce4-114">有关有效设置的列表, 请参阅 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="13ce4-114">Refer to the Remarks section for the list of valid settings.</span></span>  <br/> |
| <span data-ttu-id="13ce4-115">*Number*</span><span class="sxs-lookup"><span data-stu-id="13ce4-115">*Number*</span></span>  <br/> |<span data-ttu-id="13ce4-116">是一个表达式, 可解析为一个整数, 该整数将添加到日期的*日期\*\*部分*。</span><span class="sxs-lookup"><span data-stu-id="13ce4-116">Is an expression that can be resolved to an integer that is added to a  *DatePart*  of  *Date*  .</span></span> <span data-ttu-id="13ce4-117">如果指定十进制小数的值, 则分数将被截尾取整。</span><span class="sxs-lookup"><span data-stu-id="13ce4-117">If you specify a value with a decimal fraction, the fraction is truncated.</span></span>  <br/> |
| <span data-ttu-id="13ce4-118">*Date*</span><span class="sxs-lookup"><span data-stu-id="13ce4-118">*Date*</span></span>  <br/> |<span data-ttu-id="13ce4-119">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="13ce4-119">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="13ce4-120">*日期*参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="13ce4-120">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13ce4-121">注解</span><span class="sxs-lookup"><span data-stu-id="13ce4-121">Remarks</span></span>

<span data-ttu-id="13ce4-122">下表列出了所有有效的*DatePart*参数。</span><span class="sxs-lookup"><span data-stu-id="13ce4-122">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="13ce4-123">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="13ce4-123">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="13ce4-124">**year**</span><span class="sxs-lookup"><span data-stu-id="13ce4-124">**year**</span></span> <br/> |
|<span data-ttu-id="13ce4-125">**结算**</span><span class="sxs-lookup"><span data-stu-id="13ce4-125">**quarter**</span></span> <br/> |
|<span data-ttu-id="13ce4-126">**month**</span><span class="sxs-lookup"><span data-stu-id="13ce4-126">**month**</span></span> <br/> |
|<span data-ttu-id="13ce4-127">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="13ce4-127">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="13ce4-128">**为期**</span><span class="sxs-lookup"><span data-stu-id="13ce4-128">**day**</span></span> <br/> |
|<span data-ttu-id="13ce4-129">**周**</span><span class="sxs-lookup"><span data-stu-id="13ce4-129">**week**</span></span> <br/> |
|<span data-ttu-id="13ce4-130">**七点**</span><span class="sxs-lookup"><span data-stu-id="13ce4-130">**hour**</span></span> <br/> |
|<span data-ttu-id="13ce4-131">**还要**</span><span class="sxs-lookup"><span data-stu-id="13ce4-131">**minute**</span></span> <br/> |
|<span data-ttu-id="13ce4-132">**第二个**</span><span class="sxs-lookup"><span data-stu-id="13ce4-132">**second**</span></span> <br/> |
|<span data-ttu-id="13ce4-133">**加**</span><span class="sxs-lookup"><span data-stu-id="13ce4-133">**millisecond**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="13ce4-134">示例</span><span class="sxs-lookup"><span data-stu-id="13ce4-134">Example</span></span>

<span data-ttu-id="13ce4-135">下面的表达式计算当月的最后一天。</span><span class="sxs-lookup"><span data-stu-id="13ce4-135">The following expression calculates the last day of the current month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

<span data-ttu-id="13ce4-136">下面的表达式计算上个月的最后一天。</span><span class="sxs-lookup"><span data-stu-id="13ce4-136">The following expression calculates the last day of the previous month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


