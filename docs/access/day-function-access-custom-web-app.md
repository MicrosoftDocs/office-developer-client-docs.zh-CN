---
title: Day 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0a77e4-0653-4a85-b507-13440aef195b
description: 返回一个整数，表示公历日历中的指定日期的天 （相应月份的天）。
ms.openlocfilehash: ae0e5f4671a8c0ee3dc95683240328351ea2c5d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773422"
---
# <a name="day-function-access-custom-web-app"></a><span data-ttu-id="42fcc-103">Day 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="42fcc-103">Day function (Access custom web app)</span></span>

<span data-ttu-id="42fcc-104">返回一个整数，表示公历日历中的指定日期的天 （相应月份的天）。</span><span class="sxs-lookup"><span data-stu-id="42fcc-104">Returns an integer representing the day (day of the month) of the specified date in the Gregorian calendar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42fcc-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="42fcc-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="42fcc-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="42fcc-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="42fcc-107">语法</span><span class="sxs-lookup"><span data-stu-id="42fcc-107">Syntax</span></span>

<span data-ttu-id="42fcc-108">**一天**(*日期*)</span><span class="sxs-lookup"><span data-stu-id="42fcc-108">**Day** (*Date*)</span></span> 
  
<span data-ttu-id="42fcc-109">**Day**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="42fcc-109">The **Day** function contains the following argument.</span></span> 
  
|<span data-ttu-id="42fcc-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="42fcc-110">**Argument name**</span></span>|<span data-ttu-id="42fcc-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="42fcc-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="42fcc-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="42fcc-112">*Date*</span></span>  <br/> |<span data-ttu-id="42fcc-113">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="42fcc-113">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="42fcc-114">*日期*参数表达式、 列表达式、 用户定义的变量或字面字符串。</span><span class="sxs-lookup"><span data-stu-id="42fcc-114">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42fcc-115">说明</span><span class="sxs-lookup"><span data-stu-id="42fcc-115">Remarks</span></span>

<span data-ttu-id="42fcc-116">**天**返回**Datepart** （天、 日期） 相同的值。</span><span class="sxs-lookup"><span data-stu-id="42fcc-116">**Day** returns the same value as **Datepart** (day, date).</span></span> 
  

