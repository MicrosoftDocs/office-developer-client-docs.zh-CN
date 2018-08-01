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
ms.openlocfilehash: 6ecd84e4ffa0959a037574998b5ff12d8f539c95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778066"
---
# <a name="pidtagprofilename-canonical-property"></a><span data-ttu-id="9c06a-103">PidTagProfileName 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c06a-103">PidTagProfileName Canonical Property</span></span>

  
  
<span data-ttu-id="9c06a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9c06a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9c06a-105">包含配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9c06a-105">Contains the name of the profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9c06a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9c06a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9c06a-107">PR_PROFILE_NAME，PR_PROFILE_NAME_A，PR_PROFILE_NAME_W</span><span class="sxs-lookup"><span data-stu-id="9c06a-107">PR_PROFILE_NAME, PR_PROFILE_NAME_A, PR_PROFILE_NAME_W</span></span>  <br/> |
|<span data-ttu-id="9c06a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9c06a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9c06a-109">0x3D12</span><span class="sxs-lookup"><span data-stu-id="9c06a-109">0x3D12</span></span>  <br/> |
|<span data-ttu-id="9c06a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9c06a-110">Data type:</span></span>  <br/> |<span data-ttu-id="9c06a-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9c06a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="9c06a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9c06a-112">Area:</span></span>  <br/> |<span data-ttu-id="9c06a-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="9c06a-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9c06a-114">说明</span><span class="sxs-lookup"><span data-stu-id="9c06a-114">Remarks</span></span>

<span data-ttu-id="9c06a-115">通过服务提供商，这些属性来计算。</span><span class="sxs-lookup"><span data-stu-id="9c06a-115">These properties are computed by service providers.</span></span> <span data-ttu-id="9c06a-116">**ServiceEntry**函数的提供程序实现可以使用这些属性来发现的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="9c06a-116">A provider's implementation of the **ServiceEntry** function can use these properties to discover the profile name.</span></span> 
  
<span data-ttu-id="9c06a-117">客户端应用程序可以使用这些属性，作为一个便捷的替代方式，通过检查 MAPI 子系统的状态表格行中的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性来获取的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="9c06a-117">Client applications can use these properties as a convenient alternative to obtaining the profile name by examining the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MAPI subsystem's status table row.</span></span>
  
<span data-ttu-id="9c06a-118">不随时间，例如其中一个配置文件删除和更高版本具有相同名称重新创建都是唯一这些属性。</span><span class="sxs-lookup"><span data-stu-id="9c06a-118">These properties may not be unique across time, for example where a profile is deleted and later recreated with the same name.</span></span> <span data-ttu-id="9c06a-119">MAPI 提供调用硬编码的配置文件一节中的完全唯一**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性**MUID_PROFILE_INSTANCE。**</span><span class="sxs-lookup"><span data-stu-id="9c06a-119">MAPI furnishes a totally unique **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property in a hard-coded profile section called **MUID_PROFILE_INSTANCE.**</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9c06a-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="9c06a-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9c06a-121">头文件</span><span class="sxs-lookup"><span data-stu-id="9c06a-121">Header files</span></span>

<span data-ttu-id="9c06a-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9c06a-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="9c06a-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9c06a-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="9c06a-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9c06a-124">Mapitags.h</span></span>
  
> <span data-ttu-id="9c06a-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9c06a-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9c06a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c06a-126">See also</span></span>



[<span data-ttu-id="9c06a-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9c06a-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9c06a-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c06a-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9c06a-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9c06a-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9c06a-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9c06a-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

