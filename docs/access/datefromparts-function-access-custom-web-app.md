---
title: DateFromParts 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4fa49d5f-12ea-4d14-9a03-28418f01746c
description: 返回指定的年、月和日的日期值。
ms.openlocfilehash: 7d47fe93d1990365f1db5885a3ea8fc056aabb9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423221"
---
# <a name="datefromparts-function-access-custom-web-app"></a><span data-ttu-id="69310-103">DateFromParts 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="69310-103">DateFromParts function (Access custom web app)</span></span>

<span data-ttu-id="69310-104">返回指定的年、月和日的日期值。</span><span class="sxs-lookup"><span data-stu-id="69310-104">Returns a date value for the specified year, month, and day.</span></span>
  
> [!NOTE]
> <span data-ttu-id="69310-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="69310-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="69310-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="69310-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="69310-107">语法</span><span class="sxs-lookup"><span data-stu-id="69310-107">Syntax</span></span>

<span data-ttu-id="69310-108">**DateFromParts**(*年*、*月*、*日*)</span><span class="sxs-lookup"><span data-stu-id="69310-108">**DateFromParts** (*Year*, *Month*, *Day*)</span></span> 
  
<span data-ttu-id="69310-109">**DateFromParts**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="69310-109">The **DateFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="69310-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="69310-110">**Argument name**</span></span>|<span data-ttu-id="69310-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="69310-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="69310-112">*Year*</span><span class="sxs-lookup"><span data-stu-id="69310-112">*Year*</span></span>  <br/> |<span data-ttu-id="69310-113">指定一年的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="69310-113">Integer expression specifying a year.</span></span>  <br/> |
| <span data-ttu-id="69310-114">*Month*</span><span class="sxs-lookup"><span data-stu-id="69310-114">*Month*</span></span>  <br/> |<span data-ttu-id="69310-115">指定1到12之间的月份的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="69310-115">Integer expression specifying a month, from 1 to 12.</span></span>  <br/> |
| <span data-ttu-id="69310-116">*Day*</span><span class="sxs-lookup"><span data-stu-id="69310-116">*Day*</span></span>  <br/> |<span data-ttu-id="69310-117">指定一天的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="69310-117">Integer expression specifying a day.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="69310-118">说明</span><span class="sxs-lookup"><span data-stu-id="69310-118">Remarks</span></span>

<span data-ttu-id="69310-119">**DateFromParts**返回日期部分设置为指定的年、月和日以及将时间部分设置为默认值的 date 值。</span><span class="sxs-lookup"><span data-stu-id="69310-119">**DateFromParts** returns a date value with the date portion set to the specified year, month and day, and the time portion set to the default.</span></span> <span data-ttu-id="69310-120">如果参数无效, 则会引发错误。</span><span class="sxs-lookup"><span data-stu-id="69310-120">If the arguments are not valid, then an error is raised.</span></span> <span data-ttu-id="69310-121">如果必需的参数为 null, 则返回 null。</span><span class="sxs-lookup"><span data-stu-id="69310-121">If required arguments are null, then NULL is returned.</span></span> 
  
## <a name="example"></a><span data-ttu-id="69310-122">示例</span><span class="sxs-lookup"><span data-stu-id="69310-122">Example</span></span>

<span data-ttu-id="69310-123">下面的表达式使用**DateFromParts**函数计算当月的第一天。</span><span class="sxs-lookup"><span data-stu-id="69310-123">The following expression uses the **DateFromParts** function to calculate the first day of the current month.</span></span> 
  
`DateFromParts(Year(Today()),Month(Today()),1)`



