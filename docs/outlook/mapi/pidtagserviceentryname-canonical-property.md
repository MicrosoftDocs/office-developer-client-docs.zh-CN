---
title: PidTagServiceEntryName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceEntryName
api_type:
- COM
ms.assetid: 783f08aa-fb5a-432d-b8bd-48d69f0e5c38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c771f1d97305271b70102c148e62f30512974fb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351070"
---
# <a name="pidtagserviceentryname-canonical-property"></a><span data-ttu-id="8a31b-103">PidTagServiceEntryName 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a31b-103">PidTagServiceEntryName Canonical Property</span></span>

  
  
<span data-ttu-id="8a31b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a31b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a31b-105">包含用于配置邮件服务的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="8a31b-105">Contains the name of the entry point function for configuration of a message service.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a31b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8a31b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8a31b-107">PR_SERVICE_ENTRY_NAME</span><span class="sxs-lookup"><span data-stu-id="8a31b-107">PR_SERVICE_ENTRY_NAME</span></span>  <br/> |
|<span data-ttu-id="8a31b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8a31b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8a31b-109">0x3D0B</span><span class="sxs-lookup"><span data-stu-id="8a31b-109">0x3D0B</span></span>  <br/> |
|<span data-ttu-id="8a31b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8a31b-110">Data type:</span></span>  <br/> |<span data-ttu-id="8a31b-111">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="8a31b-111">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="8a31b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8a31b-112">Area:</span></span>  <br/> |<span data-ttu-id="8a31b-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="8a31b-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8a31b-114">注解</span><span class="sxs-lookup"><span data-stu-id="8a31b-114">Remarks</span></span>

<span data-ttu-id="8a31b-115">建议邮件服务实现者提供邮件服务入口点, 但不需要该入口点。</span><span class="sxs-lookup"><span data-stu-id="8a31b-115">It is recommended that message service implementers provide a message service entry point, but the entry point is not required.</span></span> <span data-ttu-id="8a31b-116">但是, 仅当存在相关的配置属性时, 才应提供入口点。</span><span class="sxs-lookup"><span data-stu-id="8a31b-116">However, the entry point should be supplied only if the related configuration properties exist.</span></span> <span data-ttu-id="8a31b-117">如果这些属性不存在, MAPI 将假定未提供入口点。</span><span class="sxs-lookup"><span data-stu-id="8a31b-117">If these properties do not exist, MAPI assumes that no entry point is provided.</span></span>
  
<span data-ttu-id="8a31b-118">入口点函数显示的动态链接库 (DLL) 由**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 属性命名。</span><span class="sxs-lookup"><span data-stu-id="8a31b-118">The dynamic-link library (DLL) in which the entry point function appears is named by the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="8a31b-119">有关邮件服务入口点的详细信息, 请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="8a31b-119">For more information on message service entry points, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8a31b-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="8a31b-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8a31b-121">头文件</span><span class="sxs-lookup"><span data-stu-id="8a31b-121">Header files</span></span>

<span data-ttu-id="8a31b-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8a31b-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="8a31b-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8a31b-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="8a31b-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8a31b-124">Mapitags.h</span></span>
  
> <span data-ttu-id="8a31b-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8a31b-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8a31b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a31b-126">See also</span></span>



[<span data-ttu-id="8a31b-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8a31b-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8a31b-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8a31b-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8a31b-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8a31b-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8a31b-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8a31b-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

