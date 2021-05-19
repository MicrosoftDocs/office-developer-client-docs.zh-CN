---
title: 'TimeFromParts (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f631b7e-6e3c-46dc-a05f-6a07f9a91268
description: 返回基于指定部分的时间值。
ms.openlocfilehash: 8e2105140056bc65e9af0a6eda6e40fc44caed1a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417992"
---
# <a name="timefromparts-function-access-custom-web-app"></a><span data-ttu-id="10235-103">TimeFromParts (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="10235-103">TimeFromParts Function (Access custom web app)</span></span>

<span data-ttu-id="10235-104">返回基于指定部分的时间值。</span><span class="sxs-lookup"><span data-stu-id="10235-104">Returns a time value based on specified parts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10235-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="10235-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="10235-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="10235-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="10235-107">语法</span><span class="sxs-lookup"><span data-stu-id="10235-107">Syntax</span></span>

 <span data-ttu-id="10235-108">**TimeFromParts** (*Hour、Minute、Second* *)* </span><span class="sxs-lookup"><span data-stu-id="10235-108">**TimeFromParts** (*Hour*, *Minute*, *Second*)</span></span> 
  
<span data-ttu-id="10235-109">**TimeFromParts** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="10235-109">The **TimeFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="10235-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="10235-110">**Argument name**</span></span>|<span data-ttu-id="10235-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="10235-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="10235-112">*Hour*</span><span class="sxs-lookup"><span data-stu-id="10235-112">*Hour*</span></span>  <br/> |<span data-ttu-id="10235-113">指定小时数的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="10235-113">Integer expression specifying hours.</span></span>  <br/> |
| <span data-ttu-id="10235-114">*Minute*</span><span class="sxs-lookup"><span data-stu-id="10235-114">*Minute*</span></span>  <br/> |<span data-ttu-id="10235-115">指定分钟数的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="10235-115">Integer expression specifying minutes.</span></span>  <br/> |
| <span data-ttu-id="10235-116">*Second*</span><span class="sxs-lookup"><span data-stu-id="10235-116">*Second*</span></span>  <br/> |<span data-ttu-id="10235-117">指定秒的整数表达式。</span><span class="sxs-lookup"><span data-stu-id="10235-117">Integer expression specifying seconds.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="10235-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10235-118">See also</span></span>

 <span data-ttu-id="10235-119">**TimeFromParts** 返回完全初始化的时间值。</span><span class="sxs-lookup"><span data-stu-id="10235-119">**TimeFromParts** returns a fully initialized time value.</span></span> <span data-ttu-id="10235-120">如果参数无效，则引发错误。</span><span class="sxs-lookup"><span data-stu-id="10235-120">If the arguments are invalid, then an error is raised.</span></span> <span data-ttu-id="10235-121">如果任一参数为 null，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="10235-121">If any of the parameters are null, null is returned.</span></span> 
  

