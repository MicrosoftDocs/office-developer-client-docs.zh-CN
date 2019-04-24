---
title: DateWithTimeFromParts 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: aa97cbaa-8b14-42e3-a098-938ebe0769eb
description: 返回基于指定的年、月、日和时间的日期和时间。
ms.openlocfilehash: ee995d346ca27e683f342cf3f611c1147997d24e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282139"
---
# <a name="datewithtimefromparts-function-access-custom-web-app"></a><span data-ttu-id="44807-103">DateWithTimeFromParts 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="44807-103">DateWithTimeFromParts function (Access custom web app)</span></span>

<span data-ttu-id="44807-104">返回基于指定的年、月、日和时间的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="44807-104">Returns a Date and Time based on a specified year, month, day, and time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44807-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="44807-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="44807-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="44807-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="44807-107">语法</span><span class="sxs-lookup"><span data-stu-id="44807-107">Syntax</span></span>

<span data-ttu-id="44807-108">**DateWithTimeFromParts**(*年*、*月*、*日*、*小时*、*分钟*、*秒*)</span><span class="sxs-lookup"><span data-stu-id="44807-108">**DateWithTimeFromParts** (*Year*, *Month*, *Day*, *Hour*, *Minute*, *Second*)</span></span> 
  
<span data-ttu-id="44807-109">**DateWithTimeFromParts**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="44807-109">The **DateWithTimeFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="44807-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="44807-110">**Argument name**</span></span>|<span data-ttu-id="44807-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="44807-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="44807-112">*Year*</span><span class="sxs-lookup"><span data-stu-id="44807-112">*Year*</span></span>  <br/> |<span data-ttu-id="44807-113">指定一年的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-113">Integer expression specifying a year.</span></span>  <br/> |
| <span data-ttu-id="44807-114">*Month*</span><span class="sxs-lookup"><span data-stu-id="44807-114">*Month*</span></span>  <br/> |<span data-ttu-id="44807-115">指定一个月的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-115">Integer expression specifying a month.</span></span>  <br/> |
| <span data-ttu-id="44807-116">*Day*</span><span class="sxs-lookup"><span data-stu-id="44807-116">*Day*</span></span>  <br/> |<span data-ttu-id="44807-117">指定一天的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-117">Integer expression specifying a day.</span></span>  <br/> |
| <span data-ttu-id="44807-118">*Hour*</span><span class="sxs-lookup"><span data-stu-id="44807-118">*Hour*</span></span>  <br/> |<span data-ttu-id="44807-119">指定小时的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-119">Integer expression specifying hours.</span></span>  <br/> |
| <span data-ttu-id="44807-120">*Minute*</span><span class="sxs-lookup"><span data-stu-id="44807-120">*Minute*</span></span>  <br/> |<span data-ttu-id="44807-121">指定分钟的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-121">Integer expression specifying minutes.</span></span>  <br/> |
| <span data-ttu-id="44807-122">*Second*</span><span class="sxs-lookup"><span data-stu-id="44807-122">*Second*</span></span>  <br/> |<span data-ttu-id="44807-123">指定秒的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="44807-123">Integer expression specifying seconds.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44807-124">注解</span><span class="sxs-lookup"><span data-stu-id="44807-124">Remarks</span></span>

<span data-ttu-id="44807-125">**DateWithTimeFromParts**返回完全初始化的日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="44807-125">**DateWithTimeFromParts** returns a fully initialized Date/Time value.</span></span> <span data-ttu-id="44807-126">如果参数无效, 则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="44807-126">If the arguments are not valid, an error is raised.</span></span> <span data-ttu-id="44807-127">如果必需的参数为 null, 则返回 null。</span><span class="sxs-lookup"><span data-stu-id="44807-127">If required arguments are Null, then Null is returned.</span></span> 
  

