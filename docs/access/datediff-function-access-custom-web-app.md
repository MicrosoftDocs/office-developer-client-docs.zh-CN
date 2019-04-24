---
title: DateDiff 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1c58ee87-0f57-4643-be4d-62da815df705
description: 返回在指定的开始日期和结束日期之间交叉的指定日期部分边界的计数。
ms.openlocfilehash: 1cce8a501c5a57384372e681f903baa4f4c20bef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280720"
---
# <a name="datediff-function-access-custom-web-app"></a><span data-ttu-id="09900-103">DateDiff 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="09900-103">DateDiff function (Access custom web app)</span></span>

<span data-ttu-id="09900-104">返回在指定的开始日期和结束日期之间交叉的指定日期部分边界的计数。</span><span class="sxs-lookup"><span data-stu-id="09900-104">Returns the count of the specified date part boundaries crossed between the specified start date and end date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09900-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="09900-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="09900-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="09900-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="09900-107">语法</span><span class="sxs-lookup"><span data-stu-id="09900-107">Syntax</span></span>

<span data-ttu-id="09900-108">**DateDiff**(*DatePart*、开始*日期*和*结束*日期)</span><span class="sxs-lookup"><span data-stu-id="09900-108">**DateDiff** (*DatePart*, *StartDate*, *EndDate*)</span></span> 
  
<span data-ttu-id="09900-109">**DateDiff**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="09900-109">The **DateDiff** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="09900-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="09900-110">**Argument name**</span></span>|<span data-ttu-id="09900-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="09900-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="09900-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="09900-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="09900-113">是指定所交叉边界类型的*起始日期*和*结束*日期的部分。</span><span class="sxs-lookup"><span data-stu-id="09900-113">Is the part of  *StartDate*  and  *EndDate*  that specifies the type of boundary crossed.</span></span> <span data-ttu-id="09900-114">有关有效设置的列表, 请参阅 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="09900-114">Refer to the Remarks section for the list of valid settings.</span></span>  <br/> |
| <span data-ttu-id="09900-115">*StartDate*</span><span class="sxs-lookup"><span data-stu-id="09900-115">*StartDate*</span></span>  <br/> |<span data-ttu-id="09900-116">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="09900-116">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="09900-117">*日期*参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="09900-117">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
| <span data-ttu-id="09900-118">*EndDate*</span><span class="sxs-lookup"><span data-stu-id="09900-118">*EndDate*</span></span>  <br/> |<span data-ttu-id="09900-119">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="09900-119">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="09900-120">*日期*参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="09900-120">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="09900-121">注解</span><span class="sxs-lookup"><span data-stu-id="09900-121">Remarks</span></span>

<span data-ttu-id="09900-122">下表列出了所有有效的*DatePart*参数。</span><span class="sxs-lookup"><span data-stu-id="09900-122">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="09900-123">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="09900-123">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="09900-124">**year**</span><span class="sxs-lookup"><span data-stu-id="09900-124">**year**</span></span> <br/> |
|<span data-ttu-id="09900-125">**结算**</span><span class="sxs-lookup"><span data-stu-id="09900-125">**quarter**</span></span> <br/> |
|<span data-ttu-id="09900-126">**month**</span><span class="sxs-lookup"><span data-stu-id="09900-126">**month**</span></span> <br/> |
|<span data-ttu-id="09900-127">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="09900-127">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="09900-128">**为期**</span><span class="sxs-lookup"><span data-stu-id="09900-128">**day**</span></span> <br/> |
|<span data-ttu-id="09900-129">**周**</span><span class="sxs-lookup"><span data-stu-id="09900-129">**week**</span></span> <br/> |
|<span data-ttu-id="09900-130">**七点**</span><span class="sxs-lookup"><span data-stu-id="09900-130">**hour**</span></span> <br/> |
|<span data-ttu-id="09900-131">**还要**</span><span class="sxs-lookup"><span data-stu-id="09900-131">**minute**</span></span> <br/> |
|<span data-ttu-id="09900-132">**第二个**</span><span class="sxs-lookup"><span data-stu-id="09900-132">**second**</span></span> <br/> |
|<span data-ttu-id="09900-133">**加**</span><span class="sxs-lookup"><span data-stu-id="09900-133">**millisecond**</span></span> <br/> |
   

