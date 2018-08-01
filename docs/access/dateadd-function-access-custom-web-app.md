---
title: DateAdd 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7174c585-86e1-42a3-bb7f-d6641001b0f2
description: 返回指定数字的时间间隔 （正整数或负整数） 与指定的日期添加到该日期的指定的日期部分。
ms.openlocfilehash: a2baa58a2ccab7d030750d03d4fddb84e8eb8ff7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773463"
---
# <a name="dateadd-function-access-custom-web-app"></a><span data-ttu-id="5e72b-103">DateAdd 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="5e72b-103">DateAdd function (Access custom web app)</span></span>

<span data-ttu-id="5e72b-104">返回指定数字的时间间隔 （正整数或负整数） 与指定的日期添加到该日期的指定的日期部分。</span><span class="sxs-lookup"><span data-stu-id="5e72b-104">Returns a specified date with the specified number interval (positive or negative integer) added to a specified date part of that date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e72b-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="5e72b-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="5e72b-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="5e72b-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5e72b-107">语法</span><span class="sxs-lookup"><span data-stu-id="5e72b-107">Syntax</span></span>

<span data-ttu-id="5e72b-108">**DateAdd**(*DatePart*，*号码*，*日期*)</span><span class="sxs-lookup"><span data-stu-id="5e72b-108">**DateAdd** (*DatePart*, *Number*, *Date*)</span></span> 
  
<span data-ttu-id="5e72b-109">**DateAdd**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="5e72b-109">The **DateAdd** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="5e72b-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="5e72b-110">**Argument name**</span></span>|<span data-ttu-id="5e72b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e72b-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="5e72b-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="5e72b-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="5e72b-113">*日期*向其中添加的整数部分。</span><span class="sxs-lookup"><span data-stu-id="5e72b-113">The part of  *Date*  to which an integer number is added.</span></span> <span data-ttu-id="5e72b-114">引用有效设置列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="5e72b-114">Refer to the Remarks section for the list of valid settings.</span></span>  <br/> |
| <span data-ttu-id="5e72b-115">*编号*</span><span class="sxs-lookup"><span data-stu-id="5e72b-115">*Number*</span></span>  <br/> |<span data-ttu-id="5e72b-116">是可以解析为添加到*日期* *DatePart*一个整数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="5e72b-116">Is an expression that can be resolved to an integer that is added to a  *DatePart*  of  *Date*  .</span></span> <span data-ttu-id="5e72b-117">如果使用小数部分指定一个值，则将被截断分数。</span><span class="sxs-lookup"><span data-stu-id="5e72b-117">If you specify a value with a decimal fraction, the fraction is truncated.</span></span>  <br/> |
| <span data-ttu-id="5e72b-118">*日期*</span><span class="sxs-lookup"><span data-stu-id="5e72b-118">*Date*</span></span>  <br/> |<span data-ttu-id="5e72b-119">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="5e72b-119">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="5e72b-120">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="5e72b-120">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5e72b-121">说明</span><span class="sxs-lookup"><span data-stu-id="5e72b-121">Remarks</span></span>

<span data-ttu-id="5e72b-122">下表列出了所有有效的*日期部分*参数。</span><span class="sxs-lookup"><span data-stu-id="5e72b-122">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="5e72b-123">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="5e72b-123">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="5e72b-124">**year**</span><span class="sxs-lookup"><span data-stu-id="5e72b-124">**year**</span></span> <br/> |
|<span data-ttu-id="5e72b-125">**季度**</span><span class="sxs-lookup"><span data-stu-id="5e72b-125">**quarter**</span></span> <br/> |
|<span data-ttu-id="5e72b-126">**month**</span><span class="sxs-lookup"><span data-stu-id="5e72b-126">**month**</span></span> <br/> |
|<span data-ttu-id="5e72b-127">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="5e72b-127">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="5e72b-128">**一天**</span><span class="sxs-lookup"><span data-stu-id="5e72b-128">**day**</span></span> <br/> |
|<span data-ttu-id="5e72b-129">**周**</span><span class="sxs-lookup"><span data-stu-id="5e72b-129">**week**</span></span> <br/> |
|<span data-ttu-id="5e72b-130">**小时**</span><span class="sxs-lookup"><span data-stu-id="5e72b-130">**hour**</span></span> <br/> |
|<span data-ttu-id="5e72b-131">**分钟**</span><span class="sxs-lookup"><span data-stu-id="5e72b-131">**minute**</span></span> <br/> |
|<span data-ttu-id="5e72b-132">**第二个**</span><span class="sxs-lookup"><span data-stu-id="5e72b-132">**second**</span></span> <br/> |
|<span data-ttu-id="5e72b-133">**毫秒**</span><span class="sxs-lookup"><span data-stu-id="5e72b-133">**millisecond**</span></span> <br/> |
   
## <a name="example"></a><span data-ttu-id="5e72b-134">示例</span><span class="sxs-lookup"><span data-stu-id="5e72b-134">Example</span></span>

<span data-ttu-id="5e72b-135">以下表达式计算当前月份的最后一天。</span><span class="sxs-lookup"><span data-stu-id="5e72b-135">The following expression calculates the last day of the current month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today())+1,0))`

<span data-ttu-id="5e72b-136">以下表达式计算上个月的最后一天。</span><span class="sxs-lookup"><span data-stu-id="5e72b-136">The following expression calculates the last day of the previous month.</span></span>
  
`DateAdd(Day,-1,DateAdd(Month,DateDiff(Month,0,Today()),0))`


