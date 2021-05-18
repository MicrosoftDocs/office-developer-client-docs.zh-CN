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
ms.openlocfilehash: 56f6e2355ee2e64cc766bafe27cd59454e210ab6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315419"
---
# <a name="pidlidusetnef-canonical-property"></a><span data-ttu-id="733ba-103">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="733ba-103">PidLidUseTnef Canonical Property</span></span>

  
  
<span data-ttu-id="733ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="733ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="733ba-105">指定在邮件从 MAPI 转换为多用途 Internet 邮件扩展 (MIME) 或简单邮件传输协议 (SMTP) 格式时，是否应在邮件中包含传输中性封装格式 (TNEF) 。</span><span class="sxs-lookup"><span data-stu-id="733ba-105">Specifies whether Transport Neutral Encapsulation Format (TNEF) should be included on a message when that message is converted from MAPI to Multipurpose Internet Mail Extensions (MIME) or Simple Mail Transfer Protocol (SMTP) format.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="733ba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="733ba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="733ba-107">dispidUseTNEF</span><span class="sxs-lookup"><span data-stu-id="733ba-107">dispidUseTNEF</span></span>  <br/> |
|<span data-ttu-id="733ba-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="733ba-108">Property set:</span></span>  <br/> |<span data-ttu-id="733ba-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="733ba-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="733ba-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="733ba-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="733ba-111">0x00008582</span><span class="sxs-lookup"><span data-stu-id="733ba-111">0x00008582</span></span>  <br/> |
|<span data-ttu-id="733ba-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="733ba-112">Data type:</span></span>  <br/> |<span data-ttu-id="733ba-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="733ba-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="733ba-114">区域：</span><span class="sxs-lookup"><span data-stu-id="733ba-114">Area:</span></span>  <br/> |<span data-ttu-id="733ba-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="733ba-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="733ba-116">备注</span><span class="sxs-lookup"><span data-stu-id="733ba-116">Remarks</span></span>

<span data-ttu-id="733ba-117">此属性指定当邮件从 TNEF 转换为 MIME 或 SMTP 格式时，是否应在邮件中包含 TNEF。</span><span class="sxs-lookup"><span data-stu-id="733ba-117">This property specifies whether TNEF should be included on a message when that message is converted from TNEF to MIME or SMTP format.</span></span> <span data-ttu-id="733ba-118">此属性可能不存在，如果不存在，则邮件中不得包含 TNEF。</span><span class="sxs-lookup"><span data-stu-id="733ba-118">This property may be absent, and if so, TNEF must not be included on the message.</span></span>
  
<span data-ttu-id="733ba-119">此属性仅在邮件从 POP3/SMTP 邮件帐户发送时适用，不适用于其他提供程序（如 Microsoft Exchange Server）发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="733ba-119">This property only applies when the message is sent from a POP3/SMTP mail account and does not apply when the message is sent by other providers, such as Microsoft Exchange Server.</span></span>
  
<span data-ttu-id="733ba-120">在某些情况下，例如启用投票按钮或将 OLE 嵌入对象附加到邮件时，Outlook设置此属性以强制使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="733ba-120">Under certain circumstances, such as when voting buttons are enabled or an OLE embedded object is attached to a message, Outlook can set this property to force the use of TNEF.</span></span>
  
<span data-ttu-id="733ba-121">[PidTagMessageEditorFormat PR_MSG_EDITOR_FORMAT (PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) 属性可用于在发送邮件时仅强制实施纯文本，而不是 TNEF。 </span><span class="sxs-lookup"><span data-stu-id="733ba-121">The **PR_MSG_EDITOR_FORMAT** ([PidTagMessageEditorFormat](pidtagmessageeditorformat-canonical-property.md)) property can be used to enforce only plain text, and not TNEF, when sending a message.</span></span> <span data-ttu-id="733ba-122">因为 **PidLidUseTNEF** 会覆盖 **PR_MSG_EDITOR_FORMAT** 中的设置，所以想要对传出邮件强制使用纯文本的应用程序还应查找 **PidLidUseTNEF，** 并重置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="733ba-122">Because **PidLidUseTNEF** overrides the setting in **PR_MSG_EDITOR_FORMAT**, an application that wants to force plain text on an outgoing message should also look for **PidLidUseTNEF** and reset it to FALSE.</span></span> <span data-ttu-id="733ba-123">此外，外接程序必须删除需要 TNEF 的邮件功能，以避免最终发送的邮件上的附件不可用。</span><span class="sxs-lookup"><span data-stu-id="733ba-123">Additionally, the add-in must remove the message features that required TNEF to avoid unusable attachments on the message that is finally sent.</span></span> 
  
<span data-ttu-id="733ba-124">调用[IConverterSession：：MAPIToMIMEStm](iconvertersession-mapitomimestm.md)时，使用 CCSF_USE_TNEF 标志将传出 MAPI 邮件转换为 MIME 流也可强制执行 TNEF。</span><span class="sxs-lookup"><span data-stu-id="733ba-124">Use the **CCSF_USE_TNEF** flag when calling [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to convert an outgoing MAPI message to a MIME stream can also enforce TNEF.</span></span> <span data-ttu-id="733ba-125">即使未设置 **PidLidUseTNEF，** 这仍然适用。</span><span class="sxs-lookup"><span data-stu-id="733ba-125">This applies even if **PidLidUseTNEF** is not set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="733ba-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="733ba-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="733ba-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="733ba-127">Protocol specifications</span></span>

<span data-ttu-id="733ba-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="733ba-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="733ba-129">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="733ba-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="733ba-130">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="733ba-130">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="733ba-131">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="733ba-131">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="733ba-132">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="733ba-132">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="733ba-133">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="733ba-133">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="733ba-134">头文件</span><span class="sxs-lookup"><span data-stu-id="733ba-134">Header files</span></span>

<span data-ttu-id="733ba-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="733ba-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="733ba-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="733ba-136">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="733ba-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="733ba-137">See also</span></span>



[<span data-ttu-id="733ba-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="733ba-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="733ba-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="733ba-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="733ba-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="733ba-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="733ba-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="733ba-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

