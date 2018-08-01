---
title: 则 eomonth 将函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: df98bcca-152b-49f2-b4e1-35d68008fb8f
description: 返回的最后一天前的月份或指定的月数。
ms.openlocfilehash: cee42c4e5cb3a24b2e702673238ac9ee09bc7372
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773428"
---
# <a name="eomonth-function-access-custom-web-app"></a><span data-ttu-id="20d1f-103">则 eomonth 将函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="20d1f-103">EOMonth Function (Access custom web app)</span></span>

<span data-ttu-id="20d1f-104">返回的最后一天前的月份或指定的月数。</span><span class="sxs-lookup"><span data-stu-id="20d1f-104">Returns the last day of the month before or specified number of months.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20d1f-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="20d1f-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="20d1f-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="20d1f-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="20d1f-107">语法</span><span class="sxs-lookup"><span data-stu-id="20d1f-107">Syntax</span></span>

 <span data-ttu-id="20d1f-108">**则 eomonth 将**(*日期*， *NumberOfMonth*)</span><span class="sxs-lookup"><span data-stu-id="20d1f-108">**EOMonth** (*Date*, *NumberOfMonth*)</span></span> 
  
<span data-ttu-id="20d1f-109">**则 eomonth 将**包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="20d1f-109">The **EOMonth** contains the following arguments.</span></span> 
  
|<span data-ttu-id="20d1f-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="20d1f-110">**Argument name**</span></span>|<span data-ttu-id="20d1f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="20d1f-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="20d1f-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="20d1f-112">*Date*</span></span>  <br/> |<span data-ttu-id="20d1f-113">在日期/时间格式，或接受的文本表示形式日期开始的日期。</span><span class="sxs-lookup"><span data-stu-id="20d1f-113">The start date in Date/Time format, or in an accepted text representation of a date.</span></span>  <br/> |
| <span data-ttu-id="20d1f-114">*NumberOfMonth*</span><span class="sxs-lookup"><span data-stu-id="20d1f-114">*NumberOfMonth*</span></span>  <br/> |<span data-ttu-id="20d1f-115">一个数字，表示的*日期*之前或之后的月数。</span><span class="sxs-lookup"><span data-stu-id="20d1f-115">A number representing the number of months before or after the  *Date*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="20d1f-116">说明</span><span class="sxs-lookup"><span data-stu-id="20d1f-116">Remarks</span></span>

<span data-ttu-id="20d1f-117">如果*日期*不是有效日期，**则 eomonth 将**返回错误。</span><span class="sxs-lookup"><span data-stu-id="20d1f-117">If  *Date*  is not a valid date, **EOMonth** returns an error.</span></span> 
  
<span data-ttu-id="20d1f-118">如果*日期*加上*NumberOfMonth*产生无效日期，**则 eomonth 将**返回错误。</span><span class="sxs-lookup"><span data-stu-id="20d1f-118">If  *Date*  plus  *NumberOfMonth*  yields an invalid date, **EOMonth** returns an error.</span></span> 
  

