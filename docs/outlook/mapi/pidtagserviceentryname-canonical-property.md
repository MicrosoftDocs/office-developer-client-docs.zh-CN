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
ms.openlocfilehash: 0d75616aaa6599709828d32393a316c642bc613b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778396"
---
# <a name="pidtagserviceentryname-canonical-property"></a><span data-ttu-id="01a5a-103">PidTagServiceEntryName 规范属性</span><span class="sxs-lookup"><span data-stu-id="01a5a-103">PidTagServiceEntryName Canonical Property</span></span>

  
  
<span data-ttu-id="01a5a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="01a5a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="01a5a-105">包含消息服务的配置的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="01a5a-105">Contains the name of the entry point function for configuration of a message service.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="01a5a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="01a5a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="01a5a-107">PR_SERVICE_ENTRY_NAME</span><span class="sxs-lookup"><span data-stu-id="01a5a-107">PR_SERVICE_ENTRY_NAME</span></span>  <br/> |
|<span data-ttu-id="01a5a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="01a5a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="01a5a-109">0x3D0B</span><span class="sxs-lookup"><span data-stu-id="01a5a-109">0x3D0B</span></span>  <br/> |
|<span data-ttu-id="01a5a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="01a5a-110">Data type:</span></span>  <br/> |<span data-ttu-id="01a5a-111">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="01a5a-111">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="01a5a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="01a5a-112">Area:</span></span>  <br/> |<span data-ttu-id="01a5a-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="01a5a-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="01a5a-114">说明</span><span class="sxs-lookup"><span data-stu-id="01a5a-114">Remarks</span></span>

<span data-ttu-id="01a5a-115">建议的消息服务实施提供邮件服务入口点，但的入口点，则不需要。</span><span class="sxs-lookup"><span data-stu-id="01a5a-115">It is recommended that message service implementers provide a message service entry point, but the entry point is not required.</span></span> <span data-ttu-id="01a5a-116">但是，仅当存在相关的配置属性，则应提供的入口点。</span><span class="sxs-lookup"><span data-stu-id="01a5a-116">However, the entry point should be supplied only if the related configuration properties exist.</span></span> <span data-ttu-id="01a5a-117">如果不存在这些属性，MAPI 假定原样的入口点。</span><span class="sxs-lookup"><span data-stu-id="01a5a-117">If these properties do not exist, MAPI assumes that no entry point is provided.</span></span>
  
<span data-ttu-id="01a5a-118">动态链接库 (DLL) 中的入口点函数显示名为**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="01a5a-118">The dynamic-link library (DLL) in which the entry point function appears is named by the **PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="01a5a-119">消息服务入口点的详细信息，请参阅[实现服务提供程序入口点函数](implementing-a-service-provider-entry-point-function.md)。</span><span class="sxs-lookup"><span data-stu-id="01a5a-119">For more information on message service entry points, see [Implementing a Service Provider Entry Point Function](implementing-a-service-provider-entry-point-function.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="01a5a-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="01a5a-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="01a5a-121">头文件</span><span class="sxs-lookup"><span data-stu-id="01a5a-121">Header files</span></span>

<span data-ttu-id="01a5a-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="01a5a-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="01a5a-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="01a5a-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="01a5a-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="01a5a-124">Mapitags.h</span></span>
  
> <span data-ttu-id="01a5a-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="01a5a-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01a5a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01a5a-126">See also</span></span>



[<span data-ttu-id="01a5a-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="01a5a-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="01a5a-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="01a5a-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="01a5a-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="01a5a-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="01a5a-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="01a5a-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

