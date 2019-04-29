---
title: Month 函数 (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5df43594-a434-4fb7-8109-e5cf0401ae09
description: 返回一个 integer 类型的值, 该值代表指定日期的月份。
ms.openlocfilehash: 0ca7059a2fd6dad1f9790ad6f4eafe7affa014dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411489"
---
# <a name="month-function-access-custom-web-app"></a><span data-ttu-id="d0a06-103">Month 函数 (Access 自定义 web 应用)</span><span class="sxs-lookup"><span data-stu-id="d0a06-103">Month Function (Access custom web app)</span></span>

<span data-ttu-id="d0a06-104">返回一个 integer 类型的值, 该值代表指定日期的月份。</span><span class="sxs-lookup"><span data-stu-id="d0a06-104">Returns an integer that represents the month of the specified date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0a06-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="d0a06-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="d0a06-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="d0a06-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d0a06-107">语法</span><span class="sxs-lookup"><span data-stu-id="d0a06-107">Syntax</span></span>

 <span data-ttu-id="d0a06-108">**月**(*Date*)</span><span class="sxs-lookup"><span data-stu-id="d0a06-108">**Month** (*Date*)</span></span> 
  
<span data-ttu-id="d0a06-109">**Month**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="d0a06-109">The **Month** function contains the following argument.</span></span> 
  
|<span data-ttu-id="d0a06-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="d0a06-110">**Argument name**</span></span>|<span data-ttu-id="d0a06-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d0a06-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="d0a06-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="d0a06-112">*Date*</span></span>  <br/> |<span data-ttu-id="d0a06-113">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="d0a06-113">An expression that can be resolved to a Date/Time value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d0a06-114">说明</span><span class="sxs-lookup"><span data-stu-id="d0a06-114">Remarks</span></span>

 <span data-ttu-id="d0a06-115">**month**返回与**DatePart** (月, date) 相同的值。</span><span class="sxs-lookup"><span data-stu-id="d0a06-115">**Month** returns the same value as **DatePart** (month, date).</span></span> 
  
<span data-ttu-id="d0a06-116">如果*Date*仅包含一个时间部分, 则返回值为 1, 即基本月份。</span><span class="sxs-lookup"><span data-stu-id="d0a06-116">If  *Date*  contains only a time part, the return value is 1, the base month.</span></span> 
  

