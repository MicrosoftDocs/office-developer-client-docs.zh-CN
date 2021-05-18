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
ms.openlocfilehash: 9b4510a32fe14e4316a6bcddafcc163ee899436e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421562"
---
# <a name="pidtagstatusstring-canonical-property"></a><span data-ttu-id="74858-103">PidTagStatusString 规范属性</span><span class="sxs-lookup"><span data-stu-id="74858-103">PidTagStatusString Canonical Property</span></span>

  
  
<span data-ttu-id="74858-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74858-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74858-105">包含一条消息，指示会话资源的当前状态。</span><span class="sxs-lookup"><span data-stu-id="74858-105">Contains a message that indicates the current status of a session resource.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="74858-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="74858-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="74858-107">PR_STATUS_STRING、PR_STATUS_STRING_A、PR_STATUS_STRING_W</span><span class="sxs-lookup"><span data-stu-id="74858-107">PR_STATUS_STRING, PR_STATUS_STRING_A, PR_STATUS_STRING_W</span></span>  <br/> |
|<span data-ttu-id="74858-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="74858-108">Identifier:</span></span>  <br/> |<span data-ttu-id="74858-109">0x3E08</span><span class="sxs-lookup"><span data-stu-id="74858-109">0x3E08</span></span>  <br/> |
|<span data-ttu-id="74858-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="74858-110">Data type:</span></span>  <br/> |<span data-ttu-id="74858-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="74858-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="74858-112">区域：</span><span class="sxs-lookup"><span data-stu-id="74858-112">Area:</span></span>  <br/> |<span data-ttu-id="74858-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="74858-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="74858-114">备注</span><span class="sxs-lookup"><span data-stu-id="74858-114">Remarks</span></span>

<span data-ttu-id="74858-115">这些属性使服务提供商和 MAPI 有机会提供有关会话资源状态的特定信息，例如集成通讯簿或特定服务提供商。</span><span class="sxs-lookup"><span data-stu-id="74858-115">These properties give service providers and MAPI the opportunity to supply specific information about the status of a session resource, such as the integrated address book or a particular service provider.</span></span> <span data-ttu-id="74858-116">此属性解释并提供有关[PidTagStatusCode](pidtagstatuscode-canonical-property.md) PR_STATUS_CODE (状态代码) 信息。</span><span class="sxs-lookup"><span data-stu-id="74858-116">This property explains and provides additional information about a status code, or the **PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) property.</span></span> <span data-ttu-id="74858-117">尽管 **PR_STATUS_CODE** 状态对象都需要此参数，PR_STATUS_STRING属性和关联属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="74858-117">Whereas **PR_STATUS_CODE** is required for all status objects, **PR_STATUS_STRING** and associated properties are optional.</span></span> <span data-ttu-id="74858-118">当传输提供程序未提供值时，MAPI 后台处理程序会提供默认值。</span><span class="sxs-lookup"><span data-stu-id="74858-118">When the transport provider does not supply a value, the MAPI spooler supplies a default value.</span></span> 
  
<span data-ttu-id="74858-119">该字符串在远程过程调用的同一端与 MAPI 后台处理程序一起生成;它通过共享内存，而不是跨进程边界封送。</span><span class="sxs-lookup"><span data-stu-id="74858-119">The string is generated on the same side of the remote procedure call as the MAPI spooler; it travels through shared memory rather than being marshaled across a process boundary.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="74858-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="74858-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="74858-121">头文件</span><span class="sxs-lookup"><span data-stu-id="74858-121">Header files</span></span>

<span data-ttu-id="74858-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="74858-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="74858-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="74858-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="74858-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="74858-124">Mapitags.h</span></span>
  
> <span data-ttu-id="74858-125">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="74858-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74858-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74858-126">See also</span></span>



[<span data-ttu-id="74858-127">PidTagStatusCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="74858-127">PidTagStatusCode Canonical Property</span></span>](pidtagstatuscode-canonical-property.md)


[<span data-ttu-id="74858-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="74858-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="74858-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="74858-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="74858-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="74858-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="74858-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="74858-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

