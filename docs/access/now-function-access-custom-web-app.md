---
title: Now 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8842a555-d4c8-4528-b5f9-0ddf5691273d
description: 返回应用程序定义的时区中的当前日期和时间值。
ms.openlocfilehash: 74b0a124e5715036146fedc9a6079d84a39ce84a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308097"
---
# <a name="now-function-access-custom-web-app"></a><span data-ttu-id="b665d-103">Now 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="b665d-103">Now Function (Access custom web app)</span></span>

<span data-ttu-id="b665d-104">返回应用程序定义的时区中的当前日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="b665d-104">Returns the current date and time value in the time zone defined by the application.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b665d-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="b665d-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="b665d-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="b665d-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b665d-107">语法</span><span class="sxs-lookup"><span data-stu-id="b665d-107">Syntax</span></span>

 <span data-ttu-id="b665d-108">**现在**()</span><span class="sxs-lookup"><span data-stu-id="b665d-108">**Now** ()</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b665d-109">注解</span><span class="sxs-lookup"><span data-stu-id="b665d-109">Remarks</span></span>

<span data-ttu-id="b665d-110">**Now**函数的结果仅当刷新包含公式的列时才会更改。</span><span class="sxs-lookup"><span data-stu-id="b665d-110">The result of the **Now** function changes only when the column that contains the formula is refreshed.</span></span> <span data-ttu-id="b665d-111">它不会连续更新。</span><span class="sxs-lookup"><span data-stu-id="b665d-111">It is not updated continuously.</span></span> 
  
<span data-ttu-id="b665d-112">**Today**函数返回相同的日期, 但并不是相对于时间的精度;返回的时间始终为 12:00:00 AM, 并且仅更新日期。</span><span class="sxs-lookup"><span data-stu-id="b665d-112">The **Today** function returns the same date but is not precise with regard to time; the time returned is always 12:00:00 AM and only the date is updated.</span></span> 
  

