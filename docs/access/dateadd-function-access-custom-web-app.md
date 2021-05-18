---
title: 'DateAdd 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回具有指定数字间隔的指定 (正整数或负整数) 添加到该日期的指定日期部分。
ms.openlocfilehash: 7cfd68c4983eee22a5e542facd72ea083deb3184
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423200"
---
# <a name="dateadd-function-access-custom-web-app"></a><span data-ttu-id="d8d9e-103">DateAdd 函数 (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="d8d9e-103">DateAdd function (Access custom web app)</span></span>

<span data-ttu-id="d8d9e-104">返回具有指定数字间隔的指定 (正整数或负整数) 添加到该日期的指定日期部分。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-104">Returns a specified date with the specified number interval (positive or negative integer) added to a specified date part of that date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8d9e-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="d8d9e-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="d8d9e-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d8d9e-107">语法</span><span class="sxs-lookup"><span data-stu-id="d8d9e-107">Syntax</span></span>

<span data-ttu-id="d8d9e-108">**DateAdd** (*DatePart*、 *Number*、 *Date*) </span><span class="sxs-lookup"><span data-stu-id="d8d9e-108">**DateAdd** (*DatePart*, *Number*, *Date*)</span></span> 
  
<span data-ttu-id="d8d9e-109">**DateAdd** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-109">The **DateAdd** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="d8d9e-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-110">**Argument name**</span></span>|<span data-ttu-id="d8d9e-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d8d9e-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="d8d9e-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="d8d9e-113">将整数  *添加到的 Date*  部分。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-113">The part of  *Date*  to which an integer number is added.</span></span> <span data-ttu-id="d8d9e-114">有关有效设置的列表，请参阅"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-114">Refer to the Remarks section for the list of valid settings.</span></span>  <br/> |
| <span data-ttu-id="d8d9e-115">*Number*</span><span class="sxs-lookup"><span data-stu-id="d8d9e-115">*Number*</span></span>  <br/> |<span data-ttu-id="d8d9e-116">是可解析为添加到  *DatePart*  of Date 的整数的  *表达式*  。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-116">Is an expression that can be resolved to an integer that is added to a  *DatePart*  of  *Date*  .</span></span> <span data-ttu-id="d8d9e-117">如果指定一个包含小数部分的值，则分数将被截去。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-117">If you specify a value with a decimal fraction, the fraction is truncated.</span></span>  <br/> |
| <span data-ttu-id="d8d9e-118">*Date*</span><span class="sxs-lookup"><span data-stu-id="d8d9e-118">*Date*</span></span>  <br/> |<span data-ttu-id="d8d9e-119">可以解析为"日期/时间"值的表达式。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-119">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="d8d9e-120">*Date* 参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-120">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8d9e-121">备注</span><span class="sxs-lookup"><span data-stu-id="d8d9e-121">Remarks</span></span>

<span data-ttu-id="d8d9e-122">下表列出了所有有效的  *DatePart*  参数。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-122">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="d8d9e-123">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="d8d9e-123">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="d8d9e-124">**year**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-124">**year**</span></span> <br/> |
|<span data-ttu-id="d8d9e-125">**quarter**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-125">**quarter**</span></span> <br/> |
|<span data-ttu-id="d8d9e-126">**month**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-126">**month**</span></span> <br/> |
|<span data-ttu-id="d8d9e-127">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-127">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="d8d9e-128">**day**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-128">**day**</span></span> <br/> |
|<span data-ttu-id="d8d9e-129">**week**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-129">**week**</span></span> <br/> |
|<span data-ttu-id="d8d9e-130">**hour**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-130">**hour**</span></span> <br/> |
|<span data-ttu-id="d8d9e-131">**minute**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-131">**minute**</span></span> <br/> |
|<span data-ttu-id="d8d9e-132">**second**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-132">**second**</span></span> <br/> |
|<span data-ttu-id="d8d9e-133">**毫秒**</span><span class="sxs-lookup"><span data-stu-id="d8d9e-133">**millisecond**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="d8d9e-134">示例</span><span class="sxs-lookup"><span data-stu-id="d8d9e-134">Example</span></span>

<span data-ttu-id="d8d9e-135">下面的表达式计算当月的最后一天。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-135">The following expression calculates the last day of the current month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

<span data-ttu-id="d8d9e-136">下面的表达式计算上个月的最后一天。</span><span class="sxs-lookup"><span data-stu-id="d8d9e-136">The following expression calculates the last day of the previous month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


