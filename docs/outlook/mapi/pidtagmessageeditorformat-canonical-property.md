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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325632"
---
# <a name="pidtagmessageeditorformat-canonical-property"></a><span data-ttu-id="4215a-103">PidTagMessageEditorFormat 规范属性</span><span class="sxs-lookup"><span data-stu-id="4215a-103">PidTagMessageEditorFormat Canonical Property</span></span>

  
  
<span data-ttu-id="4215a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4215a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4215a-105">指定编辑器用于显示消息的格式。</span><span class="sxs-lookup"><span data-stu-id="4215a-105">Specifies the format for an editor to use to display a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4215a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4215a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4215a-107">PR_MSG_EDITOR_FORMAT</span><span class="sxs-lookup"><span data-stu-id="4215a-107">PR_MSG_EDITOR_FORMAT</span></span>  <br/> |
|<span data-ttu-id="4215a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4215a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4215a-109">0x5909</span><span class="sxs-lookup"><span data-stu-id="4215a-109">0x5909</span></span>  <br/> |
|<span data-ttu-id="4215a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4215a-110">Data type:</span></span>  <br/> |<span data-ttu-id="4215a-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4215a-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4215a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4215a-112">Area:</span></span>  <br/> |<span data-ttu-id="4215a-113">其他</span><span class="sxs-lookup"><span data-stu-id="4215a-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4215a-114">备注</span><span class="sxs-lookup"><span data-stu-id="4215a-114">Remarks</span></span>

<span data-ttu-id="4215a-115">此参数 **PR_MSG_EDITOR_FORMAT** 可以是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="4215a-115">The possible values for **PR_MSG_EDITOR_FORMAT** can be one of the following:</span></span> 
  
|<span data-ttu-id="4215a-116">**值**</span><span class="sxs-lookup"><span data-stu-id="4215a-116">**Value**</span></span>|<span data-ttu-id="4215a-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="4215a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4215a-118">**EDITOR_FORMAT_DONTKNOW**</span><span class="sxs-lookup"><span data-stu-id="4215a-118">**EDITOR_FORMAT_DONTKNOW**</span></span> <br/> |<span data-ttu-id="4215a-119">编辑器使用的格式未知。</span><span class="sxs-lookup"><span data-stu-id="4215a-119">The format for the editor to use is unknown.</span></span>  <br/> |
|<span data-ttu-id="4215a-120">**EDITOR_FORMAT_PLAINTEXT**</span><span class="sxs-lookup"><span data-stu-id="4215a-120">**EDITOR_FORMAT_PLAINTEXT**</span></span> <br/> |<span data-ttu-id="4215a-121">编辑器应该以纯文本格式显示消息。</span><span class="sxs-lookup"><span data-stu-id="4215a-121">The editor should display the message in plain text format.</span></span>  <br/> |
|<span data-ttu-id="4215a-122">**EDITOR_FORMAT_HTML**</span><span class="sxs-lookup"><span data-stu-id="4215a-122">**EDITOR_FORMAT_HTML**</span></span> <br/> |<span data-ttu-id="4215a-123">编辑器应该以 HTML 格式显示邮件。</span><span class="sxs-lookup"><span data-stu-id="4215a-123">The editor should display the message in HTML format.</span></span>  <br/> |
|<span data-ttu-id="4215a-124">**EDITOR_FORMAT_RTF**</span><span class="sxs-lookup"><span data-stu-id="4215a-124">**EDITOR_FORMAT_RTF**</span></span> <br/> |<span data-ttu-id="4215a-125">编辑器应该以格式文本格式显示消息。</span><span class="sxs-lookup"><span data-stu-id="4215a-125">The editor should display the message in Rich Text Format.</span></span>  <br/> |
   
<span data-ttu-id="4215a-126">默认情况下，邮件与 (IPM 一起 **发送。注意** 或具有派生自 IPM 的自定义邮件 **类。请注意**) POP3/SMTP 邮件帐户发送的邮件采用 TNEF 传输中性封装 (格式) 。</span><span class="sxs-lookup"><span data-stu-id="4215a-126">By default, mail messages (with the message class **IPM.Note** or with a custom message class derived from **IPM.Note**) sent from a POP3/SMTP mail account are sent in the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="4215a-127">the **PR_MSG_EDITOR_FORMAT** property can be used to enforce only plain text， not TNEF， when sending a message.</span><span class="sxs-lookup"><span data-stu-id="4215a-127">The **PR_MSG_EDITOR_FORMAT** property can be used to enforce only plain text, and not TNEF, when sending a message.</span></span> <span data-ttu-id="4215a-128">如果 **PR_MSG_EDITOR_FORMAT** 设置为 EDITOR_FORMAT_PLAINTEXT **，则** 邮件将作为不带 TNEF 的纯文本发送。</span><span class="sxs-lookup"><span data-stu-id="4215a-128">If **PR_MSG_EDITOR_FORMAT** is set to **EDITOR_FORMAT_PLAINTEXT**, the message is sent as plain text without TNEF.</span></span> <span data-ttu-id="4215a-129">如果 **PR_MSG_EDITOR_FORMAT** 设置为 EDITOR_FORMAT_RTF，则隐式启用 TNEF 编码，并且邮件使用 Outlook 客户端中指定的默认 Internet 格式发送。</span><span class="sxs-lookup"><span data-stu-id="4215a-129">If **PR_MSG_EDITOR_FORMAT** is set to **EDITOR_FORMAT_RTF**, TNEF encoding is implicitly enabled, and the message is sent by using the default Internet format that is specified in the Outlook client.</span></span>
  
<span data-ttu-id="4215a-130">还有其他两种方法可以强制在发送邮件时使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="4215a-130">There are two other ways to enforce the use of TNEF when sending a message.</span></span>
  
- <span data-ttu-id="4215a-131">将邮件的 **dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) 命名属性设置为 True 表示将邮件从 MAPI 转换为 MIME/SMTP 时，应包含 TNEF。</span><span class="sxs-lookup"><span data-stu-id="4215a-131">Setting the **dispidUseTNEF** ([PidLidUseTnef](pidlidusetnef-canonical-property.md)) named property to True on a message indicates TNEF should be included when converting the message from MAPI to MIME/SMTP.</span></span> <span data-ttu-id="4215a-132">请注意 **，dispidUseTNEF** 仅适用于从 POP3/SMTP 邮件帐户发送邮件的情况，而不适用于其他提供程序（如 Microsoft Exchange Server）发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="4215a-132">Note that **dispidUseTNEF** only applies when the message is sent from a POP3/SMTP mail account, and does not apply when the message is sent by other providers, such as Microsoft Exchange Server.</span></span> <span data-ttu-id="4215a-133">**dispidUseTNEF** 会覆盖 PR_MSG_EDITOR_FORMAT 中的 **设置**。</span><span class="sxs-lookup"><span data-stu-id="4215a-133">**dispidUseTNEF** overrides the setting in **PR_MSG_EDITOR_FORMAT**.</span></span>
    
- <span data-ttu-id="4215a-134">调用[IConverterSession：：MAPIToMIMEStm](iconvertersession-mapitomimestm.md)将传出 MAPI 邮件转换为 MIME 流时，使用 CCSF_USE_TNEF 标志也可强制使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="4215a-134">Using the **CCSF_USE_TNEF** flag when calling [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to convert an outgoing MAPI message to a MIME stream can also enforce TNEF.</span></span> <span data-ttu-id="4215a-135">即使未设置 **dispidUseTNEF，** 这仍然适用。</span><span class="sxs-lookup"><span data-stu-id="4215a-135">This applies even if **dispidUseTNEF** is not set.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="4215a-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="4215a-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4215a-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="4215a-137">Protocol specifications</span></span>

<span data-ttu-id="4215a-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4215a-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4215a-139">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="4215a-139">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4215a-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4215a-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4215a-141">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="4215a-141">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="4215a-142">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4215a-142">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4215a-143">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4215a-143">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4215a-144">头文件</span><span class="sxs-lookup"><span data-stu-id="4215a-144">Header files</span></span>

<span data-ttu-id="4215a-145">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4215a-145">Mapidefs.h</span></span>
  
> <span data-ttu-id="4215a-146">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4215a-146">Provides data type definitions.</span></span>
    
<span data-ttu-id="4215a-147">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4215a-147">Mapitags.h</span></span>
  
> <span data-ttu-id="4215a-148">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4215a-148">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4215a-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4215a-149">See also</span></span>



[<span data-ttu-id="4215a-150">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4215a-150">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4215a-151">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4215a-151">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4215a-152">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4215a-152">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4215a-153">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4215a-153">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

