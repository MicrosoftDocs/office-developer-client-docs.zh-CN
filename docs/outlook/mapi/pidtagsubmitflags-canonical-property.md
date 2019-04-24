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
ms.openlocfilehash: ca31aece48236227a03d8e2114f8af4b127b8f90
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339352"
---
# <a name="pidtagsubmitflags-canonical-property"></a><span data-ttu-id="46b68-103">PidTagSubmitFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="46b68-103">PidTagSubmitFlags Canonical Property</span></span>

  
  
<span data-ttu-id="46b68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46b68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46b68-105">包含指示邮件提交详细信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="46b68-105">Contains a bitmask of flags indicating details about a message submission.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="46b68-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="46b68-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="46b68-107">PR_SUBMIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="46b68-107">PR_SUBMIT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="46b68-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="46b68-108">Identifier:</span></span>  <br/> |<span data-ttu-id="46b68-109">0x0E14</span><span class="sxs-lookup"><span data-stu-id="46b68-109">0x0E14</span></span>  <br/> |
|<span data-ttu-id="46b68-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="46b68-110">Data type:</span></span>  <br/> |<span data-ttu-id="46b68-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="46b68-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="46b68-112">区域：</span><span class="sxs-lookup"><span data-stu-id="46b68-112">Area:</span></span>  <br/> |<span data-ttu-id="46b68-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="46b68-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="46b68-114">注解</span><span class="sxs-lookup"><span data-stu-id="46b68-114">Remarks</span></span>

<span data-ttu-id="46b68-115">可以为**PR_SUBMIT_FLAGS**位掩码设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="46b68-115">One or more of the following flags can be set for the **PR_SUBMIT_FLAGS** bitmask:</span></span> 
  
<span data-ttu-id="46b68-116">SUBMITFLAG_LOCKED</span><span class="sxs-lookup"><span data-stu-id="46b68-116">SUBMITFLAG_LOCKED</span></span> 
  
> <span data-ttu-id="46b68-117">MAPI 后台处理程序当前已锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="46b68-117">The MAPI spooler currently has the message locked.</span></span> 
    
<span data-ttu-id="46b68-118">SUBMITFLAG_PREPROCESS</span><span class="sxs-lookup"><span data-stu-id="46b68-118">SUBMITFLAG_PREPROCESS</span></span> 
  
> <span data-ttu-id="46b68-119">邮件需要进行预处理。</span><span class="sxs-lookup"><span data-stu-id="46b68-119">The message needs preprocessing.</span></span> <span data-ttu-id="46b68-120">当 MAPI 后台处理程序完成预处理此邮件时, 它应调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46b68-120">When the MAPI spooler is done preprocessing this message, it should call the [IMessage::SubmitMessage](imessage-submitmessage.md) method.</span></span> <span data-ttu-id="46b68-121">邮件存储区提供程序识别出后台处理程序 (而不是客户端应用程序) 已调用**SubmitMessage**, 清除该标志, 并继续邮件提交。</span><span class="sxs-lookup"><span data-stu-id="46b68-121">The message store provider recognizes that the spooler, rather than the client application, has called **SubmitMessage**, clears the flag, and continues message submission.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="46b68-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="46b68-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="46b68-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="46b68-123">Protocol specifications</span></span>

<span data-ttu-id="46b68-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46b68-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46b68-125">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="46b68-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="46b68-126">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="46b68-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="46b68-127">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="46b68-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="46b68-128">头文件</span><span class="sxs-lookup"><span data-stu-id="46b68-128">Header files</span></span>

<span data-ttu-id="46b68-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="46b68-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="46b68-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="46b68-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="46b68-131">Mapitags</span><span class="sxs-lookup"><span data-stu-id="46b68-131">Mapitags.h</span></span>
  
> <span data-ttu-id="46b68-132">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="46b68-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="46b68-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46b68-133">See also</span></span>



[<span data-ttu-id="46b68-134">IMsgStore::SetLockState</span><span class="sxs-lookup"><span data-stu-id="46b68-134">IMsgStore::SetLockState</span></span>](imsgstore-setlockstate.md)


[<span data-ttu-id="46b68-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="46b68-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="46b68-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="46b68-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="46b68-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="46b68-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="46b68-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="46b68-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

