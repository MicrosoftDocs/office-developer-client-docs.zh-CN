---
title: DateFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4fa49d5f-12ea-4d14-9a03-28418f01746c
description: 返回指定的年、 月和日的 date 值。
ms.openlocfilehash: 5a2ff76d99076cf9f53b0dce8c5019f38d910f58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773409"
---
# <a name="datefromparts-function-access-custom-web-app"></a><span data-ttu-id="a2ce0-103">DateFromParts 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="a2ce0-103">DateFromParts function (Access custom web app)</span></span>

<span data-ttu-id="a2ce0-104">返回指定的年、 月和日的 date 值。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-104">Returns a date value for the specified year, month, and day.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a2ce0-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="a2ce0-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="a2ce0-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a2ce0-107">语法</span><span class="sxs-lookup"><span data-stu-id="a2ce0-107">Syntax</span></span>

<span data-ttu-id="a2ce0-108">**DateFromParts**（*年*、*月*、*日*）</span><span class="sxs-lookup"><span data-stu-id="a2ce0-108">**DateFromParts** (*Year*, *Month*, *Day*)</span></span> 
  
<span data-ttu-id="a2ce0-109">**DateFromParts**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-109">The **DateFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="a2ce0-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-110">**Argument name**</span></span>|<span data-ttu-id="a2ce0-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="a2ce0-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="a2ce0-112">*year()*</span><span class="sxs-lookup"><span data-stu-id="a2ce0-112">*Year*</span></span>  <br/> |<span data-ttu-id="a2ce0-113">指定一年的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-113">Integer expression specifying a year.</span></span>  <br/> |
| <span data-ttu-id="a2ce0-114">*month*</span><span class="sxs-lookup"><span data-stu-id="a2ce0-114">*Month*</span></span>  <br/> |<span data-ttu-id="a2ce0-115">整数表达式，指定一个月、 从 1 到 12。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-115">Integer expression specifying a month, from 1 to 12.</span></span>  <br/> |
| <span data-ttu-id="a2ce0-116">*日。*</span><span class="sxs-lookup"><span data-stu-id="a2ce0-116">*Day*</span></span>  <br/> |<span data-ttu-id="a2ce0-117">指定一天的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-117">Integer expression specifying a day.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a2ce0-118">备注</span><span class="sxs-lookup"><span data-stu-id="a2ce0-118">Remarks</span></span>

<span data-ttu-id="a2ce0-119">**DateFromParts**返回设置为指定的年、 月和日和设置为默认值的时间部分的日期部分与一个 date 值。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-119">**DateFromParts** returns a date value with the date portion set to the specified year, month and day, and the time portion set to the default.</span></span> <span data-ttu-id="a2ce0-120">如果参数不是有效的则引发一个错误。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-120">If the arguments are not valid, then an error is raised.</span></span> <span data-ttu-id="a2ce0-121">如果需要参数为 null，则返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-121">If required arguments are null, then NULL is returned.</span></span> 
  
## <a name="example"></a><span data-ttu-id="a2ce0-122">示例</span><span class="sxs-lookup"><span data-stu-id="a2ce0-122">Example</span></span>

<span data-ttu-id="a2ce0-123">以下表达式使用**DateFromParts**函数计算当前月份的第一天。</span><span class="sxs-lookup"><span data-stu-id="a2ce0-123">The following expression uses the **DateFromParts** function to calculate the first day of the current month.</span></span> 
  
`DateFromParts(Year(Today()),Month(Today()),1)`



