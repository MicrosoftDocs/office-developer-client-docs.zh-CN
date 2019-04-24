---
title: PidTagProfileName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProfileName
api_type:
- COM
ms.assetid: 13ca726d-ae7a-4da9-9c8e-3db3c479f839
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 992b3a6a30e15d267ffeda11ec98c7b4aeacb2c4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341648"
---
# <a name="pidtagprofilename-canonical-property"></a><span data-ttu-id="df0c8-103">PidTagProfileName 规范属性</span><span class="sxs-lookup"><span data-stu-id="df0c8-103">PidTagProfileName Canonical Property</span></span>

  
  
<span data-ttu-id="df0c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df0c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df0c8-105">包含配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="df0c8-105">Contains the name of the profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="df0c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="df0c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="df0c8-107">PR_PROFILE_NAME、PR_PROFILE_NAME_A、PR_PROFILE_NAME_W</span><span class="sxs-lookup"><span data-stu-id="df0c8-107">PR_PROFILE_NAME, PR_PROFILE_NAME_A, PR_PROFILE_NAME_W</span></span>  <br/> |
|<span data-ttu-id="df0c8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="df0c8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="df0c8-109">0x3D12</span><span class="sxs-lookup"><span data-stu-id="df0c8-109">0x3D12</span></span>  <br/> |
|<span data-ttu-id="df0c8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="df0c8-110">Data type:</span></span>  <br/> |<span data-ttu-id="df0c8-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="df0c8-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="df0c8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="df0c8-112">Area:</span></span>  <br/> |<span data-ttu-id="df0c8-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="df0c8-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="df0c8-114">注解</span><span class="sxs-lookup"><span data-stu-id="df0c8-114">Remarks</span></span>

<span data-ttu-id="df0c8-115">这些属性由服务提供程序进行计算。</span><span class="sxs-lookup"><span data-stu-id="df0c8-115">These properties are computed by service providers.</span></span> <span data-ttu-id="df0c8-116">提供程序的**ServiceEntry**函数实现可以使用这些属性来发现配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="df0c8-116">A provider's implementation of the **ServiceEntry** function can use these properties to discover the profile name.</span></span> 
  
<span data-ttu-id="df0c8-117">客户端应用程序可以通过检查 MAPI 子系统的状态表行中的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性, 将这些属性用作获取配置文件名称的简便方法。</span><span class="sxs-lookup"><span data-stu-id="df0c8-117">Client applications can use these properties as a convenient alternative to obtaining the profile name by examining the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MAPI subsystem's status table row.</span></span>
  
<span data-ttu-id="df0c8-118">这些属性在一段时间内可能不是唯一的, 例如, 在删除配置文件后, 再用相同的名称重新创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="df0c8-118">These properties may not be unique across time, for example where a profile is deleted and later recreated with the same name.</span></span> <span data-ttu-id="df0c8-119">MAPI 提供 MUID_PROFILE_INSTANCE 中的硬编码配置文件部分中的完全唯一的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性 **。**</span><span class="sxs-lookup"><span data-stu-id="df0c8-119">MAPI furnishes a totally unique **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property in a hard-coded profile section called **MUID_PROFILE_INSTANCE.**</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="df0c8-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="df0c8-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="df0c8-121">头文件</span><span class="sxs-lookup"><span data-stu-id="df0c8-121">Header files</span></span>

<span data-ttu-id="df0c8-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="df0c8-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="df0c8-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="df0c8-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="df0c8-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="df0c8-124">Mapitags.h</span></span>
  
> <span data-ttu-id="df0c8-125">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="df0c8-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="df0c8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df0c8-126">See also</span></span>



[<span data-ttu-id="df0c8-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="df0c8-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="df0c8-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="df0c8-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="df0c8-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="df0c8-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="df0c8-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="df0c8-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

