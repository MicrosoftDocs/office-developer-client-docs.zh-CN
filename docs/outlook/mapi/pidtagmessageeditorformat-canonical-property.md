---
title: PidTagMessageEditorFormat 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageEditorFormat
api_type:
- HeaderDef
ms.assetid: 197b21ed-9f2f-425f-a6ed-cae1208fa2ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 029df4397f4d24c7c111d2017d34e6403df367d6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401571"
---
# <a name="pidtagmessageeditorformat-canonical-property"></a><span data-ttu-id="8c048-103">PidTagMessageEditorFormat 规范属性</span><span class="sxs-lookup"><span data-stu-id="8c048-103">PidTagMessageEditorFormat Canonical Property</span></span>

  
  
<span data-ttu-id="8c048-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c048-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c048-105">指定编辑器，用于显示一条消息的格式。</span><span class="sxs-lookup"><span data-stu-id="8c048-105">Specifies the format for an editor to use to display a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8c048-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8c048-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8c048-107">PR_MSG_EDITOR_FORMAT</span><span class="sxs-lookup"><span data-stu-id="8c048-107">PR_MSG_EDITOR_FORMAT</span></span>  <br/> |
|<span data-ttu-id="8c048-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8c048-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8c048-109">0x5909</span><span class="sxs-lookup"><span data-stu-id="8c048-109">0x5909</span></span>  <br/> |
|<span data-ttu-id="8c048-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8c048-110">Data type:</span></span>  <br/> |<span data-ttu-id="8c048-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8c048-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8c048-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8c048-112">Area:</span></span>  <br/> |<span data-ttu-id="8c048-113">其他</span><span class="sxs-lookup"><span data-stu-id="8c048-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c048-114">说明</span><span class="sxs-lookup"><span data-stu-id="8c048-114">Remarks</span></span>

<span data-ttu-id="8c048-115">**PR_MSG_EDITOR_FORMAT**的可能值可以是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="8c048-115">The possible values for **PR_MSG_EDITOR_FORMAT** can be one of the following:</span></span> 
  
|<span data-ttu-id="8c048-116">**值**</span><span class="sxs-lookup"><span data-stu-id="8c048-116">**Value**</span></span>|<span data-ttu-id="8c048-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c048-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c048-118">**EDITOR_FORMAT_DONTKNOW**</span><span class="sxs-lookup"><span data-stu-id="8c048-118">**EDITOR_FORMAT_DONTKNOW**</span></span> <br/> |<span data-ttu-id="8c048-119">未知编辑器要使用的格式。</span><span class="sxs-lookup"><span data-stu-id="8c048-119">The format for the editor to use is unknown.</span></span>  <br/> |
|<span data-ttu-id="8c048-120">**EDITOR_FORMAT_PLAINTEXT**</span><span class="sxs-lookup"><span data-stu-id="8c048-120">**EDITOR_FORMAT_PLAINTEXT**</span></span> <br/> |<span data-ttu-id="8c048-121">在编辑器应以纯文本格式显示消息。</span><span class="sxs-lookup"><span data-stu-id="8c048-121">The editor should display the message in plain text format.</span></span>  <br/> |
|<span data-ttu-id="8c048-122">**EDITOR_FORMAT_HTML**</span><span class="sxs-lookup"><span data-stu-id="8c048-122">**EDITOR_FORMAT_HTML**</span></span> <br/> |<span data-ttu-id="8c048-123">在编辑器应显示邮件以 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="8c048-123">The editor should display the message in HTML format.</span></span>  <br/> |
|<span data-ttu-id="8c048-124">**EDITOR_FORMAT_RTF**</span><span class="sxs-lookup"><span data-stu-id="8c048-124">**EDITOR_FORMAT_RTF**</span></span> <br/> |<span data-ttu-id="8c048-125">在编辑器应以富文本格式显示消息。</span><span class="sxs-lookup"><span data-stu-id="8c048-125">The editor should display the message in Rich Text Format.</span></span>  <br/> |
   
<span data-ttu-id="8c048-126">默认情况下，邮件的邮件 （邮件类**IPM 中。注意**或**IPM 从派生自定义邮件类别。请注意**) 发送帐户从 POP3/SMTP 邮件发送中传输中性封装格式 (TNEF)。</span><span class="sxs-lookup"><span data-stu-id="8c048-126">By default, mail messages (with the message class **IPM.Note** or with a custom message class derived from **IPM.Note**) sent from a POP3/SMTP mail account are sent in the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="8c048-127">**PR_MSG_EDITOR_FORMAT**属性可用于强制实施仅纯文本，而不是 TNEF，发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="8c048-127">The **PR_MSG_EDITOR_FORMAT** property can be used to enforce only plain text, and not TNEF, when sending a message.</span></span> <span data-ttu-id="8c048-128">如果**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_PLAINTEXT**，没有 TNEF 纯文本形式发送邮件。</span><span class="sxs-lookup"><span data-stu-id="8c048-128">If **PR_MSG_EDITOR_FORMAT** is set to **EDITOR_FORMAT_PLAINTEXT**, the message is sent as plain text without TNEF.</span></span> <span data-ttu-id="8c048-129">如果**PR_MSG_EDITOR_FORMAT**设置为**EDITOR_FORMAT_RTF**，隐式启用 TNEF 编码，并通过使用 Outlook 客户端中指定的默认 Internet 格式发送邮件。</span><span class="sxs-lookup"><span data-stu-id="8c048-129">If **PR_MSG_EDITOR_FORMAT** is set to **EDITOR_FORMAT_RTF**, TNEF encoding is implicitly enabled, and the message is sent by using the default Internet format that is specified in the Outlook client.</span></span>
  
<span data-ttu-id="8c048-130">有两个其他方式发送邮件时强制使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="8c048-130">There are two other ways to enforce the use of TNEF when sending a message.</span></span>
  
- <span data-ttu-id="8c048-131">设置**dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) 名为属性设置为 True 上一条消息，指示转换为 MIME/SMTP 邮件 MAPI 时应包含 TNEF。</span><span class="sxs-lookup"><span data-stu-id="8c048-131">Setting the **dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) named property to True on a message indicates TNEF should be included when converting the message from MAPI to MIME/SMTP.</span></span> <span data-ttu-id="8c048-132">请注意该**dispidUseTNEF**仅适用于邮件发送的 POP3/SMTP 邮件帐户，并不适用于由其他提供程序，例如 Microsoft Exchange Server 发送邮件时。</span><span class="sxs-lookup"><span data-stu-id="8c048-132">Note that **dispidUseTNEF** only applies when the message is sent from a POP3/SMTP mail account, and does not apply when the message is sent by other providers, such as Microsoft Exchange Server.</span></span> <span data-ttu-id="8c048-133">**dispidUseTNEF**覆盖**PR_MSG_EDITOR_FORMAT**中的设置。</span><span class="sxs-lookup"><span data-stu-id="8c048-133">**dispidUseTNEF** overrides the setting in **PR_MSG_EDITOR_FORMAT**.</span></span>
    
- <span data-ttu-id="8c048-134">使用**CCSF_USE_TNEF**标志调用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)时将传出的 MAPI 邮件转换为 MIME 流还可以强制 TNEF。</span><span class="sxs-lookup"><span data-stu-id="8c048-134">Using the **CCSF_USE_TNEF** flag when calling [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to convert an outgoing MAPI message to a MIME stream can also enforce TNEF.</span></span> <span data-ttu-id="8c048-135">这适用即使**dispidUseTNEF**未设置。</span><span class="sxs-lookup"><span data-stu-id="8c048-135">This applies even if **dispidUseTNEF** is not set.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="8c048-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="8c048-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8c048-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="8c048-137">Protocol specifications</span></span>

<span data-ttu-id="8c048-138">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c048-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c048-139">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8c048-139">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8c048-140">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c048-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c048-141">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="8c048-141">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="8c048-142">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c048-142">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c048-143">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="8c048-143">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8c048-144">头文件</span><span class="sxs-lookup"><span data-stu-id="8c048-144">Header files</span></span>

<span data-ttu-id="8c048-145">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8c048-145">Mapidefs.h</span></span>
  
> <span data-ttu-id="8c048-146">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8c048-146">Provides data type definitions.</span></span>
    
<span data-ttu-id="8c048-147">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8c048-147">Mapitags.h</span></span>
  
> <span data-ttu-id="8c048-148">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8c048-148">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8c048-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c048-149">See also</span></span>



[<span data-ttu-id="8c048-150">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8c048-150">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8c048-151">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8c048-151">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8c048-152">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8c048-152">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8c048-153">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8c048-153">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

