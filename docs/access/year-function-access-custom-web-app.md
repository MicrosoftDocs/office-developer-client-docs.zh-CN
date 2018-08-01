---
title: Year 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a70751eb-bfde-4f7d-ad90-a1e4cca25dbc
description: 返回一个代表公历日历中的指定日期的年的数字值。
ms.openlocfilehash: f9d72343637734257a2ed9589e5539b845933826
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773633"
---
# <a name="year-function-access-custom-web-app"></a><span data-ttu-id="b38e3-103">Year 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="b38e3-103">Year Function (Access custom web app)</span></span>

<span data-ttu-id="b38e3-104">返回一个代表公历日历中的指定日期的年的数字值。</span><span class="sxs-lookup"><span data-stu-id="b38e3-104">Returns a numeric value that represents the year of the specified date in the Gregorian calendar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b38e3-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="b38e3-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="b38e3-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="b38e3-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b38e3-107">语法</span><span class="sxs-lookup"><span data-stu-id="b38e3-107">Syntax</span></span>

 <span data-ttu-id="b38e3-108">**年**(*日期*)</span><span class="sxs-lookup"><span data-stu-id="b38e3-108">**Year** (*Date*)</span></span> 
  
<span data-ttu-id="b38e3-109">**Year**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="b38e3-109">The **Year** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="b38e3-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="b38e3-110">**Argument name**</span></span>|<span data-ttu-id="b38e3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="b38e3-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b38e3-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="b38e3-112">*Date*</span></span>  <br/> |<span data-ttu-id="b38e3-113">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="b38e3-113">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="b38e3-114">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="b38e3-114">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b38e3-115">说明</span><span class="sxs-lookup"><span data-stu-id="b38e3-115">Remarks</span></span>

<span data-ttu-id="b38e3-116">**年**、**月**和**日**函数返回值将是公历-无论提供的日期值的显示格式的值。</span><span class="sxs-lookup"><span data-stu-id="b38e3-116">Values returned by the **Year**, **Month**, and **Day** functions will be Gregorian values regardless of the display format for the supplied date value.</span></span> <span data-ttu-id="b38e3-117">例如，如果提供的日期使用的显示格式回历、**年**、**月**和**日**函数的返回的值将为值与等效公历日期关联。</span><span class="sxs-lookup"><span data-stu-id="b38e3-117">For example, if the display format of the supplied date uses the Hijri calendar, the returned values for the **Year**, **Month**, and **Day** functions will be values associated with the equivalent Gregorian date.</span></span> 
  

