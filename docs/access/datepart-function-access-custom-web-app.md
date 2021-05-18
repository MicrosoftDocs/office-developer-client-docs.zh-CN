---
title: 'Access 自定义 (应用的 DatePart 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8936f0b6-f9b2-44ef-bf90-e482b64611cd
description: 返回一个数值，表示指定日期的指定日期部分。
ms.openlocfilehash: 31ac6423614afd61ed943bb7ba375f14696df1ea
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411433"
---
# <a name="datepart-function-access-custom-web-app"></a><span data-ttu-id="1a1fe-103">Access 自定义 (应用的 DatePart 函数) </span><span class="sxs-lookup"><span data-stu-id="1a1fe-103">DatePart function (Access custom web app)</span></span>

<span data-ttu-id="1a1fe-104">返回一个数值，表示指定日期的指定日期部分。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-104">Returns a numeric value that represents the specified date part of the specified date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a1fe-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="1a1fe-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="1a1fe-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1a1fe-107">语法</span><span class="sxs-lookup"><span data-stu-id="1a1fe-107">Syntax</span></span>

<span data-ttu-id="1a1fe-108">**DatePart** (*DatePart* *、Date*) </span><span class="sxs-lookup"><span data-stu-id="1a1fe-108">**DatePart** (*DatePart*, *Date*)</span></span> 
  
<span data-ttu-id="1a1fe-109">**DatePart** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-109">The **DatePart** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="1a1fe-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-110">**Argument name**</span></span>|<span data-ttu-id="1a1fe-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="1a1fe-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="1a1fe-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="1a1fe-113">Date  *部分 (*  一个日期或时间) 将返回一个整数。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-113">The part of  *Date*  (a date or time value) for which an integer will be returned.</span></span> <span data-ttu-id="1a1fe-114">有关有效缩写的列表，请参阅"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-114">Refer to the Remarks section for the list of valid abbreviations.</span></span>  <br/> |
| <span data-ttu-id="1a1fe-115">*Date*</span><span class="sxs-lookup"><span data-stu-id="1a1fe-115">*Date*</span></span>  <br/> |<span data-ttu-id="1a1fe-116">可以解析为"日期/时间"值的表达式。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-116">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="1a1fe-117">*Date* 参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-117">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a1fe-118">备注</span><span class="sxs-lookup"><span data-stu-id="1a1fe-118">Remarks</span></span>

<span data-ttu-id="1a1fe-119">下表列出了所有有效的  *DatePart*  参数。</span><span class="sxs-lookup"><span data-stu-id="1a1fe-119">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="1a1fe-120">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="1a1fe-120">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="1a1fe-121">**year**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-121">**year**</span></span> <br/> |
|<span data-ttu-id="1a1fe-122">**quarter**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-122">**quarter**</span></span> <br/> |
|<span data-ttu-id="1a1fe-123">**month**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-123">**month**</span></span> <br/> |
|<span data-ttu-id="1a1fe-124">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-124">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="1a1fe-125">**day**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-125">**day**</span></span> <br/> |
|<span data-ttu-id="1a1fe-126">**week**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-126">**week**</span></span> <br/> |
|<span data-ttu-id="1a1fe-127">**weekday**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-127">**weekday**</span></span> <br/> |
|<span data-ttu-id="1a1fe-128">**hour**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-128">**hour**</span></span> <br/> |
|<span data-ttu-id="1a1fe-129">**minute**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-129">**minute**</span></span> <br/> |
|<span data-ttu-id="1a1fe-130">**second**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-130">**second**</span></span> <br/> |
|<span data-ttu-id="1a1fe-131">**毫秒**</span><span class="sxs-lookup"><span data-stu-id="1a1fe-131">**millisecond**</span></span> <br/> |
   

