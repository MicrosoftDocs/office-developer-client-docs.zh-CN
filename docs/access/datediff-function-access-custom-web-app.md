---
title: DateDiff 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 1c58ee87-0f57-4643-be4d-62da815df705
description: 返回指定的日期部分边界删除线之间的指定的开始日期和结束日期的计数。
ms.openlocfilehash: fe898ec5eb59cb341250cb0c0e2e35bc55d37eb3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773461"
---
# <a name="datediff-function-access-custom-web-app"></a><span data-ttu-id="e7f45-103">DateDiff 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="e7f45-103">DateDiff function (Access custom web app)</span></span>

<span data-ttu-id="e7f45-104">返回指定的日期部分边界删除线之间的指定的开始日期和结束日期的计数。</span><span class="sxs-lookup"><span data-stu-id="e7f45-104">Returns the count of the specified date part boundaries crossed between the specified start date and end date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7f45-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="e7f45-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="e7f45-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="e7f45-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e7f45-107">语法</span><span class="sxs-lookup"><span data-stu-id="e7f45-107">Syntax</span></span>

<span data-ttu-id="e7f45-108">**DateDiff**(*DatePart*， *StartDate*， *EndDate*)</span><span class="sxs-lookup"><span data-stu-id="e7f45-108">**DateDiff** (*DatePart*, *StartDate*, *EndDate*)</span></span> 
  
<span data-ttu-id="e7f45-109">**DateDiff**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="e7f45-109">The **DateDiff** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="e7f45-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="e7f45-110">**Argument name**</span></span>|<span data-ttu-id="e7f45-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7f45-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e7f45-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="e7f45-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="e7f45-113">*StartDate*和*EndDate* ，指定的边界删除线类型的一部分。</span><span class="sxs-lookup"><span data-stu-id="e7f45-113">Is the part of  *StartDate*  and  *EndDate*  that specifies the type of boundary crossed.</span></span> <span data-ttu-id="e7f45-114">引用有效设置列表的备注部分。</span><span class="sxs-lookup"><span data-stu-id="e7f45-114">Refer to the Remarks section for the list of valid settings.</span></span>  <br/> |
| <span data-ttu-id="e7f45-115">*StartDate*</span><span class="sxs-lookup"><span data-stu-id="e7f45-115">*StartDate*</span></span>  <br/> |<span data-ttu-id="e7f45-116">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="e7f45-116">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="e7f45-117">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="e7f45-117">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
| <span data-ttu-id="e7f45-118">*EndDate*</span><span class="sxs-lookup"><span data-stu-id="e7f45-118">*EndDate*</span></span>  <br/> |<span data-ttu-id="e7f45-119">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="e7f45-119">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="e7f45-120">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="e7f45-120">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e7f45-121">说明</span><span class="sxs-lookup"><span data-stu-id="e7f45-121">Remarks</span></span>

<span data-ttu-id="e7f45-122">下表列出了所有有效的*日期部分*参数。</span><span class="sxs-lookup"><span data-stu-id="e7f45-122">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="e7f45-123">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="e7f45-123">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="e7f45-124">**year**</span><span class="sxs-lookup"><span data-stu-id="e7f45-124">**year**</span></span> <br/> |
|<span data-ttu-id="e7f45-125">**季度**</span><span class="sxs-lookup"><span data-stu-id="e7f45-125">**quarter**</span></span> <br/> |
|<span data-ttu-id="e7f45-126">**month**</span><span class="sxs-lookup"><span data-stu-id="e7f45-126">**month**</span></span> <br/> |
|<span data-ttu-id="e7f45-127">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="e7f45-127">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="e7f45-128">**一天**</span><span class="sxs-lookup"><span data-stu-id="e7f45-128">**day**</span></span> <br/> |
|<span data-ttu-id="e7f45-129">**周**</span><span class="sxs-lookup"><span data-stu-id="e7f45-129">**week**</span></span> <br/> |
|<span data-ttu-id="e7f45-130">**小时**</span><span class="sxs-lookup"><span data-stu-id="e7f45-130">**hour**</span></span> <br/> |
|<span data-ttu-id="e7f45-131">**分钟**</span><span class="sxs-lookup"><span data-stu-id="e7f45-131">**minute**</span></span> <br/> |
|<span data-ttu-id="e7f45-132">**第二个**</span><span class="sxs-lookup"><span data-stu-id="e7f45-132">**second**</span></span> <br/> |
|<span data-ttu-id="e7f45-133">**毫秒**</span><span class="sxs-lookup"><span data-stu-id="e7f45-133">**millisecond**</span></span> <br/> |
   

