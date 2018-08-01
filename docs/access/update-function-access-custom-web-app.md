---
title: 更新函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8a8c52c9-81b9-4d10-b42b-e360c67bcf4e
description: 返回在指定的字段中是否尝试了插入或更新操作。
ms.openlocfilehash: 1685d9f44bd167571b949a34d6c7b6993e63fbc0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773636"
---
# <a name="update-function-access-custom-web-app"></a><span data-ttu-id="046e5-103">更新函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="046e5-103">Update Function (Access custom web app)</span></span>

<span data-ttu-id="046e5-104">返回在指定的字段中是否尝试了插入或更新操作。</span><span class="sxs-lookup"><span data-stu-id="046e5-104">Returns whether an INSERT or UPDATE operation was attempted on the specified field.</span></span>
  
> [!NOTE]
> <span data-ttu-id="046e5-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="046e5-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="046e5-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="046e5-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="046e5-107">语法</span><span class="sxs-lookup"><span data-stu-id="046e5-107">Syntax</span></span>

 <span data-ttu-id="046e5-108">**更新**（*列*）</span><span class="sxs-lookup"><span data-stu-id="046e5-108">**Update** (*Column*)</span></span> 
  
<span data-ttu-id="046e5-109">**更新**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="046e5-109">The **Update** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="046e5-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="046e5-110">**Argument name**</span></span>|<span data-ttu-id="046e5-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="046e5-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="046e5-112">*Column*</span><span class="sxs-lookup"><span data-stu-id="046e5-112">*Column*</span></span>  <br/> |<span data-ttu-id="046e5-113">要检查插入或更新操作的域的名称。</span><span class="sxs-lookup"><span data-stu-id="046e5-113">The name of the field to check for an INSERT or UPDATE operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="046e5-114">说明</span><span class="sxs-lookup"><span data-stu-id="046e5-114">Remarks</span></span>

<span data-ttu-id="046e5-115">**更新**函数无论插入或更新尝试是否成功，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="046e5-115">The **Update** function returns TRUE regardless of whether an INSERT or UPDATE attempt is successful.</span></span> 
  

