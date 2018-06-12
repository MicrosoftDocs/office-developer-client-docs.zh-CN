---
title: 现在函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8842a555-d4c8-4528-b5f9-0ddf5691273d
description: 返回当前的日期和时间值中定义的应用程序所在的时区。
ms.openlocfilehash: 721c0d2a872e0c4ec9ca75c963d5429a72fb2d3d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773572"
---
# <a name="now-function-access-custom-web-app"></a><span data-ttu-id="b53c9-103">现在函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="b53c9-103">Now Function (Access custom web app)</span></span>

<span data-ttu-id="b53c9-104">返回当前的日期和时间值中定义的应用程序所在的时区。</span><span class="sxs-lookup"><span data-stu-id="b53c9-104">Returns the current date and time value in the time zone defined by the application.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b53c9-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="b53c9-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="b53c9-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="b53c9-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b53c9-107">语法</span><span class="sxs-lookup"><span data-stu-id="b53c9-107">Syntax</span></span>

 <span data-ttu-id="b53c9-108">**现在**()</span><span class="sxs-lookup"><span data-stu-id="b53c9-108">**Now** ()</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b53c9-109">备注</span><span class="sxs-lookup"><span data-stu-id="b53c9-109">Remarks</span></span>

<span data-ttu-id="b53c9-110">更改的结果**现在**函数仅当刷新包含公式的列。</span><span class="sxs-lookup"><span data-stu-id="b53c9-110">The result of the **Now** function changes only when the column that contains the formula is refreshed.</span></span> <span data-ttu-id="b53c9-111">不持续更新。</span><span class="sxs-lookup"><span data-stu-id="b53c9-111">It is not updated continuously.</span></span> 
  
<span data-ttu-id="b53c9-112">**Today**函数返回相同的日期，但并不精确在时间;返回时始终是 12:00:00，该日期仅进行了更新。</span><span class="sxs-lookup"><span data-stu-id="b53c9-112">The **Today** function returns the same date but is not precise with regard to time; the time returned is always 12:00:00 AM and only the date is updated.</span></span> 
  

