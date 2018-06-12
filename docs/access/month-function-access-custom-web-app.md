---
title: Month 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5df43594-a434-4fb7-8109-e5cf0401ae09
description: 返回一个 integer 值，该值代表指定日期的月。
ms.openlocfilehash: 5e4a583a5a299456e57b90d7cef41a32b0a6ffba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773582"
---
# <a name="month-function-access-custom-web-app"></a><span data-ttu-id="387fa-103">Month 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="387fa-103">Month Function (Access custom web app)</span></span>

<span data-ttu-id="387fa-104">返回一个 integer 值，该值代表指定日期的月。</span><span class="sxs-lookup"><span data-stu-id="387fa-104">Returns an integer that represents the month of the specified date.</span></span>
  
> [!NOTE]
> <span data-ttu-id="387fa-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="387fa-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="387fa-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="387fa-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="387fa-107">语法</span><span class="sxs-lookup"><span data-stu-id="387fa-107">Syntax</span></span>

 <span data-ttu-id="387fa-108">**月**(*日期*)</span><span class="sxs-lookup"><span data-stu-id="387fa-108">**Month** (*Date*)</span></span> 
  
<span data-ttu-id="387fa-109">**Month**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="387fa-109">The **Month** function contains the following argument.</span></span> 
  
|<span data-ttu-id="387fa-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="387fa-110">**Argument name**</span></span>|<span data-ttu-id="387fa-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="387fa-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="387fa-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="387fa-112">*Date*</span></span>  <br/> |<span data-ttu-id="387fa-113">一个可解析为日期/时间值的表达式。</span><span class="sxs-lookup"><span data-stu-id="387fa-113">An expression that can be resolved to a Date/Time value.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="387fa-114">备注</span><span class="sxs-lookup"><span data-stu-id="387fa-114">Remarks</span></span>

 <span data-ttu-id="387fa-115">**月**返回**DatePart** （月、 日期） 相同的值。</span><span class="sxs-lookup"><span data-stu-id="387fa-115">**Month** returns the same value as **DatePart** (month, date).</span></span> 
  
<span data-ttu-id="387fa-116">如果*日期*包含时间部分，返回值为 1，基本的月份。</span><span class="sxs-lookup"><span data-stu-id="387fa-116">If  *Date*  contains only a time part, the return value is 1, the base month.</span></span> 
  

