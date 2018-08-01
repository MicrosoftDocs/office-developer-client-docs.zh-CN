---
title: PidLidUseTnef 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidUseTnef
api_type:
- COM
ms.assetid: 954048d6-e2eb-43e7-b52c-c2f047bb84a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 73fa4311a61be9259d8c45aca79d719785c213a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777152"
---
# <a name="pidlidusetnef-canonical-property"></a><span data-ttu-id="2bc5b-103">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bc5b-103">PidLidUseTnef Canonical Property</span></span>

  
  
<span data-ttu-id="2bc5b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2bc5b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2bc5b-105">指定该邮件从 MAPI 转换为多用途 Internet 邮件扩展 (MIME) 或简单邮件传输协议 (SMTP) 格式时，是否应在上一条消息中包括传输中性封装格式 (TNEF)。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-105">Specifies whether Transport Neutral Encapsulation Format (TNEF) should be included on a message when that message is converted from MAPI to Multipurpose Internet Mail Extensions (MIME) or Simple Mail Transfer Protocol (SMTP) format.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2bc5b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2bc5b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2bc5b-107">dispidUseTNEF</span><span class="sxs-lookup"><span data-stu-id="2bc5b-107">dispidUseTNEF</span></span>  <br/> |
|<span data-ttu-id="2bc5b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2bc5b-108">Property set:</span></span>  <br/> |<span data-ttu-id="2bc5b-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2bc5b-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2bc5b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2bc5b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2bc5b-111">0x00008582</span><span class="sxs-lookup"><span data-stu-id="2bc5b-111">0x00008582</span></span>  <br/> |
|<span data-ttu-id="2bc5b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2bc5b-112">Data type:</span></span>  <br/> |<span data-ttu-id="2bc5b-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2bc5b-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="2bc5b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2bc5b-114">Area:</span></span>  <br/> |<span data-ttu-id="2bc5b-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="2bc5b-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2bc5b-116">说明</span><span class="sxs-lookup"><span data-stu-id="2bc5b-116">Remarks</span></span>

<span data-ttu-id="2bc5b-117">此属性指定该邮件从 TNEF 转换为 MIME 或 SMTP 格式时是否应在 TNEF 包括上一条消息。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-117">This property specifies whether TNEF should be included on a message when that message is converted from TNEF to MIME or SMTP format.</span></span> <span data-ttu-id="2bc5b-118">此属性可能不存在，并且如果是这样，TNEF 不能包含对邮件。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-118">This property may be absent, and if so, TNEF must not be included on the message.</span></span>
  
<span data-ttu-id="2bc5b-119">此属性仅适用时邮件发送的 POP3/SMTP 邮件帐户并不适用于由其他提供程序，例如 Microsoft Exchange Server 发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-119">This property only applies when the message is sent from a POP3/SMTP mail account and does not apply when the message is sent by other providers, such as Microsoft Exchange Server.</span></span>
  
<span data-ttu-id="2bc5b-120">在某些情况下，如时投票按钮处于启用状态或嵌入的 OLE 对象附加到邮件中，Outlook 可以设置此属性以强制使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-120">Under certain circumstances, such as when voting buttons are enabled or an OLE embedded object is attached to a message, Outlook can set this property to force the use of TNEF.</span></span>
  
<span data-ttu-id="2bc5b-121">**PR_MSG_EDITOR_FORMAT** ([PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) 属性可用于强制实施仅纯文本，而不是 TNEF，发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-121">The **PR_MSG_EDITOR_FORMAT** ([PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) property can be used to enforce only plain text, and not TNEF, when sending a message.</span></span> <span data-ttu-id="2bc5b-122">**PidLidUseTNEF**重写**PR_MSG_EDITOR_FORMAT**中的设置，因此想要强制对传出邮件的纯文本应用程序应还寻找**PidLidUseTNEF** ，并将其重置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-122">Because **PidLidUseTNEF** overrides the setting in **PR_MSG_EDITOR_FORMAT**, an application that wants to force plain text on an outgoing message should also look for **PidLidUseTNEF** and reset it to FALSE.</span></span> <span data-ttu-id="2bc5b-123">此外外, 接程序必须删除所需 TNEF 以避免在最后发送的消息上不可用的附件的邮件功能。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-123">Additionally, the add-in must remove the message features that required TNEF to avoid unusable attachments on the message that is finally sent.</span></span> 
  
<span data-ttu-id="2bc5b-124">使用**CCSF_USE_TNEF**标志调用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)将传出的 MAPI 邮件转换为 MIME 流时还可以强制实施 TNEF。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-124">Use the **CCSF_USE_TNEF** flag when calling [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to convert an outgoing MAPI message to a MIME stream can also enforce TNEF.</span></span> <span data-ttu-id="2bc5b-125">这适用即使**PidLidUseTNEF**未设置。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-125">This applies even if **PidLidUseTNEF** is not set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2bc5b-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="2bc5b-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2bc5b-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="2bc5b-127">Protocol specifications</span></span>

<span data-ttu-id="2bc5b-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2bc5b-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2bc5b-129">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2bc5b-130">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2bc5b-130">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2bc5b-131">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-131">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="2bc5b-132">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2bc5b-132">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2bc5b-133">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-133">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2bc5b-134">头文件</span><span class="sxs-lookup"><span data-stu-id="2bc5b-134">Header files</span></span>

<span data-ttu-id="2bc5b-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2bc5b-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="2bc5b-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2bc5b-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2bc5b-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc5b-137">See also</span></span>



[<span data-ttu-id="2bc5b-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2bc5b-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2bc5b-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2bc5b-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2bc5b-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2bc5b-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2bc5b-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2bc5b-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

