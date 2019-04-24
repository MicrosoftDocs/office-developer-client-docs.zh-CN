---
title: Day 函数 (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0a77e4-0653-4a85-b507-13440aef195b
description: 返回一个整数, 表示公历中指定日期的日期 (月中的某一天)。
ms.openlocfilehash: 720adaffbd97a735f6b1395e64965f972c6099cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280689"
---
# <a name="day-function-access-custom-web-app"></a><span data-ttu-id="caa1d-103">Day 函数 (Access 自定义 web 应用)</span><span class="sxs-lookup"><span data-stu-id="caa1d-103">Day function (Access custom web app)</span></span>

<span data-ttu-id="caa1d-104">返回一个整数, 表示公历中指定日期的日期 (月中的某一天)。</span><span class="sxs-lookup"><span data-stu-id="caa1d-104">Returns an integer representing the day (day of the month) of the specified date in the Gregorian calendar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa1d-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="caa1d-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="caa1d-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="caa1d-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="caa1d-107">语法</span><span class="sxs-lookup"><span data-stu-id="caa1d-107">Syntax</span></span>

<span data-ttu-id="caa1d-108">**天**(*Date*)</span><span class="sxs-lookup"><span data-stu-id="caa1d-108">**Day** (*Date*)</span></span> 
  
<span data-ttu-id="caa1d-109">**Day**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="caa1d-109">The **Day** function contains the following argument.</span></span> 
  
|<span data-ttu-id="caa1d-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="caa1d-110">**Argument name**</span></span>|<span data-ttu-id="caa1d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="caa1d-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="caa1d-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="caa1d-112">*Date*</span></span>  <br/> |<span data-ttu-id="caa1d-113">可以解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="caa1d-113">An expression that can be resolved to a Date/Time value.</span></span> <span data-ttu-id="caa1d-114">*日期*参数表达式、列表达式、用户定义的变量或字符串文本。</span><span class="sxs-lookup"><span data-stu-id="caa1d-114">The  *Date*  argument expression, column expression, user-defined variable or string literal.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="caa1d-115">注解</span><span class="sxs-lookup"><span data-stu-id="caa1d-115">Remarks</span></span>

<span data-ttu-id="caa1d-116">**day**返回与**Datepart** (Day, date) 相同的值。</span><span class="sxs-lookup"><span data-stu-id="caa1d-116">**Day** returns the same value as **Datepart** (day, date).</span></span> 
  

