---
title: Year 函数 (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a70751eb-bfde-4f7d-ad90-a1e4cca25dbc
description: 返回一个数值, 表示公历中指定日期的年份。
ms.openlocfilehash: 1400c352bcc070035d15b46f8e547e4637364299
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433120"
---
# <a name="year-function-access-custom-web-app"></a><span data-ttu-id="f86c9-103">Year 函数 (Access 自定义 web 应用)</span><span class="sxs-lookup"><span data-stu-id="f86c9-103">Year Function (Access custom web app)</span></span>

<span data-ttu-id="f86c9-104">返回一个数值, 表示公历中指定日期的年份。</span><span class="sxs-lookup"><span data-stu-id="f86c9-104">Returns a numeric value that represents the year of the specified date in the Gregorian calendar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f86c9-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="f86c9-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="f86c9-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="f86c9-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f86c9-107">语法</span><span class="sxs-lookup"><span data-stu-id="f86c9-107">Syntax</span></span>

 <span data-ttu-id="f86c9-108">**年**(*Date*)</span><span class="sxs-lookup"><span data-stu-id="f86c9-108">**Year** (*Date*)</span></span> 
  
<span data-ttu-id="f86c9-109">**Year**函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="f86c9-109">The **Year** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="f86c9-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="f86c9-110">**Argument name**</span></span>|<span data-ttu-id="f86c9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f86c9-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f86c9-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="f86c9-112">*Date*</span></span>  <br/> |<span data-ttu-id="f86c9-113">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="f86c9-113">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="f86c9-114">*日期*参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="f86c9-114">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f86c9-115">说明</span><span class="sxs-lookup"><span data-stu-id="f86c9-115">Remarks</span></span>

<span data-ttu-id="f86c9-116">由**Year**、 **Month**和**Day**函数返回的值将为公历值, 而不考虑提供的日期值的显示格式。</span><span class="sxs-lookup"><span data-stu-id="f86c9-116">Values returned by the **Year**, **Month**, and **Day** functions will be Gregorian values regardless of the display format for the supplied date value.</span></span> <span data-ttu-id="f86c9-117">例如, 如果所提供日期的显示格式使用阿拉伯回历日历, 则**Year**、 **Month**和**Day**函数的返回值将是与等效公历日期相关联的值。</span><span class="sxs-lookup"><span data-stu-id="f86c9-117">For example, if the display format of the supplied date uses the Hijri calendar, the returned values for the **Year**, **Month**, and **Day** functions will be values associated with the equivalent Gregorian date.</span></span> 
  

