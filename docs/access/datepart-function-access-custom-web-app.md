---
title: DatePart 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8936f0b6-f9b2-44ef-bf90-e482b64611cd
description: 返回一个数字值，该值代表指定日期的指定的日期部分。
ms.openlocfilehash: 81aa1880e5b38c33f75018418a44ed82e5e7e8c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773419"
---
# <a name="datepart-function-access-custom-web-app"></a><span data-ttu-id="a61d2-103">DatePart 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="a61d2-103">DatePart function (Access custom web app)</span></span>

<span data-ttu-id="a61d2-104">返回一个数字值，该值代表指定日期的指定的日期部分。</span><span class="sxs-lookup"><span data-stu-id="a61d2-104">Returns a numeric value that represents the specified date part of the specified date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a61d2-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="a61d2-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="a61d2-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="a61d2-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a61d2-107">语法</span><span class="sxs-lookup"><span data-stu-id="a61d2-107">Syntax</span></span>

<span data-ttu-id="a61d2-108">**DatePart**(*DatePart*，*日期*)</span><span class="sxs-lookup"><span data-stu-id="a61d2-108">**DatePart** (*DatePart*, *Date*)</span></span> 
  
<span data-ttu-id="a61d2-109">**DatePart**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="a61d2-109">The **DatePart** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="a61d2-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="a61d2-110">**Argument name**</span></span>|<span data-ttu-id="a61d2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a61d2-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a61d2-112">*DatePart*</span><span class="sxs-lookup"><span data-stu-id="a61d2-112">*DatePart*</span></span>  <br/> |<span data-ttu-id="a61d2-113">部分*日期*（日期或时间值） 将为其返回一个整数。</span><span class="sxs-lookup"><span data-stu-id="a61d2-113">The part of  *Date*  (a date or time value) for which an integer will be returned.</span></span> <span data-ttu-id="a61d2-114">引用有效缩写的备注部分的列表。</span><span class="sxs-lookup"><span data-stu-id="a61d2-114">Refer to the Remarks section for the list of valid abbreviations.</span></span>  <br/> |
| <span data-ttu-id="a61d2-115">*日期*</span><span class="sxs-lookup"><span data-stu-id="a61d2-115">*Date*</span></span>  <br/> |<span data-ttu-id="a61d2-116">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="a61d2-116">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="a61d2-117">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="a61d2-117">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a61d2-118">说明</span><span class="sxs-lookup"><span data-stu-id="a61d2-118">Remarks</span></span>

<span data-ttu-id="a61d2-119">下表列出了所有有效的*日期部分*参数。</span><span class="sxs-lookup"><span data-stu-id="a61d2-119">The following table lists all valid  *DatePart*  arguments.</span></span> 
  
|<span data-ttu-id="a61d2-120">***DatePart***</span><span class="sxs-lookup"><span data-stu-id="a61d2-120">***DatePart***</span></span>|
|:-----|
|<span data-ttu-id="a61d2-121">**year**</span><span class="sxs-lookup"><span data-stu-id="a61d2-121">**year**</span></span> <br/> |
|<span data-ttu-id="a61d2-122">**季度**</span><span class="sxs-lookup"><span data-stu-id="a61d2-122">**quarter**</span></span> <br/> |
|<span data-ttu-id="a61d2-123">**month**</span><span class="sxs-lookup"><span data-stu-id="a61d2-123">**month**</span></span> <br/> |
|<span data-ttu-id="a61d2-124">**dayofyear**</span><span class="sxs-lookup"><span data-stu-id="a61d2-124">**dayofyear**</span></span> <br/> |
|<span data-ttu-id="a61d2-125">**一天**</span><span class="sxs-lookup"><span data-stu-id="a61d2-125">**day**</span></span> <br/> |
|<span data-ttu-id="a61d2-126">**周**</span><span class="sxs-lookup"><span data-stu-id="a61d2-126">**week**</span></span> <br/> |
|<span data-ttu-id="a61d2-127">**weekday**</span><span class="sxs-lookup"><span data-stu-id="a61d2-127">**weekday**</span></span> <br/> |
|<span data-ttu-id="a61d2-128">**小时**</span><span class="sxs-lookup"><span data-stu-id="a61d2-128">**hour**</span></span> <br/> |
|<span data-ttu-id="a61d2-129">**分钟**</span><span class="sxs-lookup"><span data-stu-id="a61d2-129">**minute**</span></span> <br/> |
|<span data-ttu-id="a61d2-130">**第二个**</span><span class="sxs-lookup"><span data-stu-id="a61d2-130">**second**</span></span> <br/> |
|<span data-ttu-id="a61d2-131">**毫秒**</span><span class="sxs-lookup"><span data-stu-id="a61d2-131">**millisecond**</span></span> <br/> |
   

