---
title: 'Update Function (Access custom web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8a8c52c9-81b9-4d10-b42b-e360c67bcf4e
description: 返回是否尝试对指定字段执行 INSERT 或 UPDATE 操作。
ms.openlocfilehash: 20e1b87be857f302f36244a6733625dc477da912
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410915"
---
# <a name="update-function-access-custom-web-app"></a><span data-ttu-id="f9435-103">Update Function (Access custom web app) </span><span class="sxs-lookup"><span data-stu-id="f9435-103">Update Function (Access custom web app)</span></span>

<span data-ttu-id="f9435-104">返回是否尝试对指定字段执行 INSERT 或 UPDATE 操作。</span><span class="sxs-lookup"><span data-stu-id="f9435-104">Returns whether an INSERT or UPDATE operation was attempted on the specified field.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f9435-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="f9435-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="f9435-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="f9435-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f9435-107">语法</span><span class="sxs-lookup"><span data-stu-id="f9435-107">Syntax</span></span>

 <span data-ttu-id="f9435-108">**更新** (*列*) </span><span class="sxs-lookup"><span data-stu-id="f9435-108">**Update** (*Column*)</span></span> 
  
<span data-ttu-id="f9435-109">**Update** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="f9435-109">The **Update** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="f9435-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="f9435-110">**Argument name**</span></span>|<span data-ttu-id="f9435-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9435-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f9435-112">*Column*</span><span class="sxs-lookup"><span data-stu-id="f9435-112">*Column*</span></span>  <br/> |<span data-ttu-id="f9435-113">要检查 INSERT 或 UPDATE 操作字段的名称。</span><span class="sxs-lookup"><span data-stu-id="f9435-113">The name of the field to check for an INSERT or UPDATE operation.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f9435-114">备注</span><span class="sxs-lookup"><span data-stu-id="f9435-114">Remarks</span></span>

<span data-ttu-id="f9435-115">无论 **INSERT** 或 UPDATE 尝试是否成功，Update 函数都返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f9435-115">The **Update** function returns TRUE regardless of whether an INSERT or UPDATE attempt is successful.</span></span> 
  

