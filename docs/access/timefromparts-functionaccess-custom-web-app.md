---
title: TimeFromParts 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7f631b7e-6e3c-46dc-a05f-6a07f9a91268
description: 返回基于指定的部件的时间值。
ms.openlocfilehash: 55a4d1c31fdd2248e3e154d83e803d9f5a5ebb06
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773612"
---
# <a name="timefromparts-function-access-custom-web-app"></a><span data-ttu-id="67d74-103">TimeFromParts 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="67d74-103">TimeFromParts Function (Access custom web app)</span></span>

<span data-ttu-id="67d74-104">返回基于指定的部件的时间值。</span><span class="sxs-lookup"><span data-stu-id="67d74-104">Returns a time value based on specified parts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67d74-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="67d74-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="67d74-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="67d74-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="67d74-107">语法</span><span class="sxs-lookup"><span data-stu-id="67d74-107">Syntax</span></span>

 <span data-ttu-id="67d74-108">**TimeFromParts**（*小时*、*分钟*、*秒*）</span><span class="sxs-lookup"><span data-stu-id="67d74-108">**TimeFromParts** (*Hour*, *Minute*, *Second*)</span></span> 
  
<span data-ttu-id="67d74-109">**TimeFromParts**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="67d74-109">The **TimeFromParts** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="67d74-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="67d74-110">**Argument name**</span></span>|<span data-ttu-id="67d74-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="67d74-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="67d74-112">*小时*</span><span class="sxs-lookup"><span data-stu-id="67d74-112">*Hour*</span></span>  <br/> |<span data-ttu-id="67d74-113">整型表达式，指定小时。</span><span class="sxs-lookup"><span data-stu-id="67d74-113">Integer expression specifying hours.</span></span>  <br/> |
| <span data-ttu-id="67d74-114">*分钟*</span><span class="sxs-lookup"><span data-stu-id="67d74-114">*Minute*</span></span>  <br/> |<span data-ttu-id="67d74-115">整型表达式，指定分钟。</span><span class="sxs-lookup"><span data-stu-id="67d74-115">Integer expression specifying minutes.</span></span>  <br/> |
| <span data-ttu-id="67d74-116">*第二节*</span><span class="sxs-lookup"><span data-stu-id="67d74-116">*Second*</span></span>  <br/> |<span data-ttu-id="67d74-117">整型表达式，指定秒。</span><span class="sxs-lookup"><span data-stu-id="67d74-117">Integer expression specifying seconds.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="67d74-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67d74-118">See also</span></span>

 <span data-ttu-id="67d74-119">**TimeFromParts**返回一个完全初始化的时间值。</span><span class="sxs-lookup"><span data-stu-id="67d74-119">**TimeFromParts** returns a fully initialized time value.</span></span> <span data-ttu-id="67d74-120">如果参数均无效，则引发错误。</span><span class="sxs-lookup"><span data-stu-id="67d74-120">If the arguments are invalid, then an error is raised.</span></span> <span data-ttu-id="67d74-121">如果任一参数为 null，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="67d74-121">If any of the parameters are null, null is returned.</span></span> 
  

