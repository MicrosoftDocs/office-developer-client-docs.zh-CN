---
title: DateWithTimeFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: aa97cbaa-8b14-42e3-a098-938ebe0769eb
description: 返回日期和时间基于指定的年、 月、 日和时间。
ms.openlocfilehash: 8cc1fbe700d18c04d944793bcea889424b0cff3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773407"
---
# <a name="datewithtimefromparts-function-access-custom-web-app"></a><span data-ttu-id="e6386-103">DateWithTimeFromParts 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="e6386-103">DateWithTimeFromParts function (Access custom web app)</span></span>

<span data-ttu-id="e6386-104">返回日期和时间基于指定的年、 月、 日和时间。</span><span class="sxs-lookup"><span data-stu-id="e6386-104">Returns a Date and Time based on a specified year, month, day, and time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6386-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="e6386-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="e6386-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="e6386-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="e6386-107">语法</span><span class="sxs-lookup"><span data-stu-id="e6386-107">Syntax</span></span>

<span data-ttu-id="e6386-108">**DateWithTimeFromParts**（*年*、*月*、*日*、*小时*、*分钟*、*第二个*）</span><span class="sxs-lookup"><span data-stu-id="e6386-108">**DateWithTimeFromParts** (*Year*, *Month*, *Day*, *Hour*, *Minute*, *Second*)</span></span> 
  
<span data-ttu-id="e6386-109">**DateWithTimeFromParts**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="e6386-109">The **DateWithTimeFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="e6386-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="e6386-110">**Argument name**</span></span>|<span data-ttu-id="e6386-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6386-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e6386-112">*year()*</span><span class="sxs-lookup"><span data-stu-id="e6386-112">*Year*</span></span>  <br/> |<span data-ttu-id="e6386-113">指定一年的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="e6386-113">Integer expression specifying a year.</span></span>  <br/> |
| <span data-ttu-id="e6386-114">*month*</span><span class="sxs-lookup"><span data-stu-id="e6386-114">*Month*</span></span>  <br/> |<span data-ttu-id="e6386-115">指定某个月份的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="e6386-115">Integer expression specifying a month.</span></span>  <br/> |
| <span data-ttu-id="e6386-116">*日。*</span><span class="sxs-lookup"><span data-stu-id="e6386-116">*Day*</span></span>  <br/> |<span data-ttu-id="e6386-117">指定一天的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="e6386-117">Integer expression specifying a day.</span></span>  <br/> |
| <span data-ttu-id="e6386-118">*小时*</span><span class="sxs-lookup"><span data-stu-id="e6386-118">*Hour*</span></span>  <br/> |<span data-ttu-id="e6386-119">整型表达式，指定小时。</span><span class="sxs-lookup"><span data-stu-id="e6386-119">Integer expression specifying hours.</span></span>  <br/> |
| <span data-ttu-id="e6386-120">*分钟*</span><span class="sxs-lookup"><span data-stu-id="e6386-120">*Minute*</span></span>  <br/> |<span data-ttu-id="e6386-121">整型表达式，指定分钟。</span><span class="sxs-lookup"><span data-stu-id="e6386-121">Integer expression specifying minutes.</span></span>  <br/> |
| <span data-ttu-id="e6386-122">*第二节*</span><span class="sxs-lookup"><span data-stu-id="e6386-122">*Second*</span></span>  <br/> |<span data-ttu-id="e6386-123">整型表达式，指定秒。</span><span class="sxs-lookup"><span data-stu-id="e6386-123">Integer expression specifying seconds.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6386-124">说明</span><span class="sxs-lookup"><span data-stu-id="e6386-124">Remarks</span></span>

<span data-ttu-id="e6386-125">**DateWithTimeFromParts**返回一个完全初始化的日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="e6386-125">**DateWithTimeFromParts** returns a fully initialized Date/Time value.</span></span> <span data-ttu-id="e6386-126">如果参数不是有效的则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="e6386-126">If the arguments are not valid, an error is raised.</span></span> <span data-ttu-id="e6386-127">如果需要参数均为空，则返回 Null。</span><span class="sxs-lookup"><span data-stu-id="e6386-127">If required arguments are Null, then Null is returned.</span></span> 
  

