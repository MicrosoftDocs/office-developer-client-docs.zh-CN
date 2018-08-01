---
title: PidTagSubmitFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubmitFlags
api_type:
- COM
ms.assetid: 9ea1c029-d53c-4c28-b413-560083b6215a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 444d98c4e8e32e0cc7d2eb8af753a394af1f020c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778484"
---
# <a name="pidtagsubmitflags-canonical-property"></a><span data-ttu-id="45d2b-103">PidTagSubmitFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="45d2b-103">PidTagSubmitFlags Canonical Property</span></span>

  
  
<span data-ttu-id="45d2b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="45d2b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="45d2b-105">包含指示的详细信息消息提交标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="45d2b-105">Contains a bitmask of flags indicating details about a message submission.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="45d2b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="45d2b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="45d2b-107">PR_SUBMIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45d2b-107">PR_SUBMIT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="45d2b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="45d2b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="45d2b-109">0x0E14</span><span class="sxs-lookup"><span data-stu-id="45d2b-109">0x0E14</span></span>  <br/> |
|<span data-ttu-id="45d2b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="45d2b-110">Data type:</span></span>  <br/> |<span data-ttu-id="45d2b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="45d2b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="45d2b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="45d2b-112">Area:</span></span>  <br/> |<span data-ttu-id="45d2b-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="45d2b-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45d2b-114">说明</span><span class="sxs-lookup"><span data-stu-id="45d2b-114">Remarks</span></span>

<span data-ttu-id="45d2b-115">可以为**PR_SUBMIT_FLAGS**位掩码设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="45d2b-115">One or more of the following flags can be set for the **PR_SUBMIT_FLAGS** bitmask:</span></span> 
  
<span data-ttu-id="45d2b-116">SUBMITFLAG_LOCKED</span><span class="sxs-lookup"><span data-stu-id="45d2b-116">SUBMITFLAG_LOCKED</span></span> 
  
> <span data-ttu-id="45d2b-117">MAPI 后台打印当前已锁定的消息。</span><span class="sxs-lookup"><span data-stu-id="45d2b-117">The MAPI spooler currently has the message locked.</span></span> 
    
<span data-ttu-id="45d2b-118">SUBMITFLAG_PREPROCESS</span><span class="sxs-lookup"><span data-stu-id="45d2b-118">SUBMITFLAG_PREPROCESS</span></span> 
  
> <span data-ttu-id="45d2b-119">需要预处理消息。</span><span class="sxs-lookup"><span data-stu-id="45d2b-119">The message needs preprocessing.</span></span> <span data-ttu-id="45d2b-120">完 MAPI 后台处理程序预处理此消息时，它应调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="45d2b-120">When the MAPI spooler is done preprocessing this message, it should call the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="45d2b-121">消息存储提供程序可识别的后台处理程序，而不是客户端应用程序，呼叫**SubmitMessage**、 清除标志，并继续消息提交。</span><span class="sxs-lookup"><span data-stu-id="45d2b-121">The message store provider recognizes that the spooler, rather than the client application, has called **SubmitMessage**, clears the flag, and continues message submission.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="45d2b-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="45d2b-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="45d2b-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="45d2b-123">Protocol specifications</span></span>

<span data-ttu-id="45d2b-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45d2b-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45d2b-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="45d2b-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="45d2b-126">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45d2b-126">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45d2b-127">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="45d2b-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="45d2b-128">头文件</span><span class="sxs-lookup"><span data-stu-id="45d2b-128">Header files</span></span>

<span data-ttu-id="45d2b-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="45d2b-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="45d2b-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="45d2b-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="45d2b-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="45d2b-131">Mapitags.h</span></span>
  
> <span data-ttu-id="45d2b-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="45d2b-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="45d2b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d2b-133">See also</span></span>



[<span data-ttu-id="45d2b-134">IMsgStore::SetLockState</span><span class="sxs-lookup"><span data-stu-id="45d2b-134">IMsgStore::SetLockState</span></span>](imsgstore-setlockstate.md)


[<span data-ttu-id="45d2b-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="45d2b-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="45d2b-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="45d2b-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="45d2b-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="45d2b-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="45d2b-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="45d2b-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

