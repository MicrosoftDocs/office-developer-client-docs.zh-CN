---
title: PidTagStatusString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatusString
api_type:
- COM
ms.assetid: 42cd946c-c55a-4371-99ee-05e2248fdd5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea24b5e721317668c8f43278a5e4c38d73b3e91c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778446"
---
# <a name="pidtagstatusstring-canonical-property"></a><span data-ttu-id="e2155-103">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2155-103">PidTagStatusString Canonical Property</span></span>

  
  
<span data-ttu-id="e2155-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e2155-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e2155-105">包含一条消息，指示会话资源的当前状态。</span><span class="sxs-lookup"><span data-stu-id="e2155-105">Contains a message that indicates the current status of a session resource.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e2155-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e2155-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e2155-107">PR_STATUS_STRING，PR_STATUS_STRING_A，PR_STATUS_STRING_W</span><span class="sxs-lookup"><span data-stu-id="e2155-107">PR_STATUS_STRING, PR_STATUS_STRING_A, PR_STATUS_STRING_W</span></span>  <br/> |
|<span data-ttu-id="e2155-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e2155-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e2155-109">0x3E08</span><span class="sxs-lookup"><span data-stu-id="e2155-109">0x3E08</span></span>  <br/> |
|<span data-ttu-id="e2155-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e2155-110">Data type:</span></span>  <br/> |<span data-ttu-id="e2155-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e2155-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e2155-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e2155-112">Area:</span></span>  <br/> |<span data-ttu-id="e2155-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="e2155-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e2155-114">说明</span><span class="sxs-lookup"><span data-stu-id="e2155-114">Remarks</span></span>

<span data-ttu-id="e2155-115">这些属性授予服务提供商和 MAPI 能够提供有关状态的会话资源，如集成的通讯簿或特定服务提供商的特定信息。</span><span class="sxs-lookup"><span data-stu-id="e2155-115">These properties give service providers and MAPI the opportunity to supply specific information about the status of a session resource, such as the integrated address book or a particular service provider.</span></span> <span data-ttu-id="e2155-116">此属性说明，并提供其他信息的状态代码或**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e2155-116">This property explains and provides additional information about a status code, or the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property.</span></span> <span data-ttu-id="e2155-117">**PR_STATUS_CODE**是必需的所有状态对象， **PR_STATUS_STRING**和关联的属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="e2155-117">Whereas **PR_STATUS_CODE** is required for all status objects, **PR_STATUS_STRING** and associated properties are optional.</span></span> <span data-ttu-id="e2155-118">传输提供程序不会提供一个值，当 MAPI 后台处理程序提供的默认值。</span><span class="sxs-lookup"><span data-stu-id="e2155-118">When the transport provider does not supply a value, the MAPI spooler supplies a default value.</span></span> 
  
<span data-ttu-id="e2155-119">在与 MAPI 后台处理程序; 远程过程调用的相同端上生成字符串通过共享的内存，而不是跨进程边界被封送传输。</span><span class="sxs-lookup"><span data-stu-id="e2155-119">The string is generated on the same side of the remote procedure call as the MAPI spooler; it travels through shared memory rather than being marshaled across a process boundary.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e2155-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="e2155-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e2155-121">头文件</span><span class="sxs-lookup"><span data-stu-id="e2155-121">Header files</span></span>

<span data-ttu-id="e2155-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e2155-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="e2155-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e2155-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="e2155-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e2155-124">Mapitags.h</span></span>
  
> <span data-ttu-id="e2155-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e2155-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2155-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2155-126">See also</span></span>



[<span data-ttu-id="e2155-127">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2155-127">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)


[<span data-ttu-id="e2155-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e2155-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e2155-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2155-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e2155-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e2155-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e2155-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e2155-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

