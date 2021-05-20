---
title: 'Access 自定义 Web (EOMonth 函数) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: df98bcca-152b-49f2-b4e1-35d68008fb8f
description: 返回月的最后一天或指定的月数。
ms.openlocfilehash: 87a837069be223fdd2f9c809d706782e0955e2aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437453"
---
# <a name="eomonth-function-access-custom-web-app"></a><span data-ttu-id="dc3ba-103">Access 自定义 Web (EOMonth 函数) </span><span class="sxs-lookup"><span data-stu-id="dc3ba-103">EOMonth Function (Access custom web app)</span></span>

<span data-ttu-id="dc3ba-104">返回月的最后一天或指定的月数。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-104">Returns the last day of the month before or specified number of months.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc3ba-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="dc3ba-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="dc3ba-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="dc3ba-107">语法</span><span class="sxs-lookup"><span data-stu-id="dc3ba-107">Syntax</span></span>

 <span data-ttu-id="dc3ba-108">**EOMonth** (*Date*、 *NumberOfMonth)*</span><span class="sxs-lookup"><span data-stu-id="dc3ba-108">**EOMonth** (*Date*, *NumberOfMonth*)</span></span> 
  
<span data-ttu-id="dc3ba-109">**EOMonth** 包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-109">The **EOMonth** contains the following arguments.</span></span> 
  
|<span data-ttu-id="dc3ba-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="dc3ba-110">**Argument name**</span></span>|<span data-ttu-id="dc3ba-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="dc3ba-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="dc3ba-112">*Date*</span><span class="sxs-lookup"><span data-stu-id="dc3ba-112">*Date*</span></span>  <br/> |<span data-ttu-id="dc3ba-113">开始日期，采用日期/时间格式，或接受的日期文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-113">The start date in Date/Time format, or in an accepted text representation of a date.</span></span>  <br/> |
| <span data-ttu-id="dc3ba-114">*NumberOfMonth*</span><span class="sxs-lookup"><span data-stu-id="dc3ba-114">*NumberOfMonth*</span></span>  <br/> |<span data-ttu-id="dc3ba-115">一个数字，表示日期之前或之后几个月  *的月份*  数。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-115">A number representing the number of months before or after the  *Date*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc3ba-116">备注</span><span class="sxs-lookup"><span data-stu-id="dc3ba-116">Remarks</span></span>

<span data-ttu-id="dc3ba-117">如果  *Date*  不是有效日期， **则 EOMonth** 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-117">If  *Date*  is not a valid date, **EOMonth** returns an error.</span></span> 
  
<span data-ttu-id="dc3ba-118">如果  *Date*  加上  *NumberOfMonth*  产生无效日期， **则 EOMonth** 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="dc3ba-118">If  *Date*  plus  *NumberOfMonth*  yields an invalid date, **EOMonth** returns an error.</span></span> 
  

