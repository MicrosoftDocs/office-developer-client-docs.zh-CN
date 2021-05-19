---
title: PidTagMessageRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageRecipients
api_type:
- HeaderDef
ms.assetid: 7f8b0d96-99d6-4f1c-8ac4-4dbb83626382
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d30088ba7398669228a18be825323afa800ec536
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355683"
---
# <a name="pidtagmessagerecipients-canonical-property"></a><span data-ttu-id="e6b38-103">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6b38-103">PidTagMessageRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="e6b38-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6b38-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6b38-105">包含一个限制表，可应用于内容表以查找包含符合限制的收件人子对象的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b38-105">Contains a table of restrictions that can be applied to a contents table to find all messages that contain recipient subobjects that meet the restrictions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6b38-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6b38-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6b38-107">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="e6b38-107">PR_MESSAGE_RECIPIENTS</span></span>  <br/> |
|<span data-ttu-id="e6b38-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e6b38-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e6b38-109">0x0E12</span><span class="sxs-lookup"><span data-stu-id="e6b38-109">0x0E12</span></span>  <br/> |
|<span data-ttu-id="e6b38-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6b38-110">Data type:</span></span>  <br/> |<span data-ttu-id="e6b38-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="e6b38-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="e6b38-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e6b38-112">Area:</span></span>  <br/> |<span data-ttu-id="e6b38-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="e6b38-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6b38-114">备注</span><span class="sxs-lookup"><span data-stu-id="e6b38-114">Remarks</span></span>

<span data-ttu-id="e6b38-115">此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。</span><span class="sxs-lookup"><span data-stu-id="e6b38-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="e6b38-116">作为类型为 PT_OBJECT  [，IMAPIProp：：GetProps](imapiprop-getprops.md)方法无法成功检索它。</span><span class="sxs-lookup"><span data-stu-id="e6b38-116">As a property of type **PT_OBJECT**, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="e6b38-117">它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法访问，并请求 **IID_IMAPITable标识符。**</span><span class="sxs-lookup"><span data-stu-id="e6b38-117">Its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="e6b38-118">如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但如果尚未设置，也可以不报告此方法。</span><span class="sxs-lookup"><span data-stu-id="e6b38-118">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="e6b38-119">若要检索表内容，客户端应用程序应调用 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e6b38-119">To retrieve table contents, a client application should call the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method.</span></span> 
  
<span data-ttu-id="e6b38-120">此属性可用于子对象限制，具体方法为在 [SSubRestriction](ssubrestriction.md) 结构中指定它。</span><span class="sxs-lookup"><span data-stu-id="e6b38-120">This property can be used for subobject restriction by specifying it in the [SSubRestriction](ssubrestriction.md) structure.</span></span> <span data-ttu-id="e6b38-121">这使客户端能够将容器视图限制为收件人满足给定条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b38-121">This enables a client to limit the view of a container to messages with recipients meeting given criteria.</span></span> <span data-ttu-id="e6b38-122">如果邮件的收件人表中至少有一行（即，一个收件人满足子对象限制，则邮件符合查看条件）。</span><span class="sxs-lookup"><span data-stu-id="e6b38-122">A message qualifies for viewing if at least one row in its recipient table, that is, one recipient satisfies the subobject restriction.</span></span> 
  
 <span data-ttu-id="e6b38-123">**注意** 使用子对象限制结果等效于表中每条消息上的 [IMAPISession：：OpenEntry](imapisession-openentry.md) 调用。</span><span class="sxs-lookup"><span data-stu-id="e6b38-123">**Note** Using subobject restriction results is the equivalent of an [IMAPISession::OpenEntry](imapisession-openentry.md) call on every message in the table.</span></span> <span data-ttu-id="e6b38-124">根据客户端应用程序和要搜索的消息数，它可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="e6b38-124">Depending on the client application and the number of messages to be searched, it can affect performance.</span></span> 
  
<span data-ttu-id="e6b38-125">**PR_MESSAGE_ATTACHMENTS** [PidTagMessageAttachments)  (PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)属性和此属性的用法相似。</span><span class="sxs-lookup"><span data-stu-id="e6b38-125">The **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property and this property are similar in usage.</span></span> <span data-ttu-id="e6b38-126">多个 MAPI 属性提供对表的访问权限：</span><span class="sxs-lookup"><span data-stu-id="e6b38-126">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="e6b38-127">**Property**</span><span class="sxs-lookup"><span data-stu-id="e6b38-127">**Property**</span></span>|<span data-ttu-id="e6b38-128">**Table**</span><span class="sxs-lookup"><span data-stu-id="e6b38-128">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6b38-129">**PR_CONTAINER_CONTENTS (** [PidTagContainerContents)](pidtagcontainercontents-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="e6b38-129">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6b38-130">Contents 表</span><span class="sxs-lookup"><span data-stu-id="e6b38-130">Contents table</span></span>  <br/> |
|<span data-ttu-id="e6b38-131">**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="e6b38-131">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6b38-132">层次结构表</span><span class="sxs-lookup"><span data-stu-id="e6b38-132">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="e6b38-133">**PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="e6b38-133">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6b38-134">关联内容表</span><span class="sxs-lookup"><span data-stu-id="e6b38-134">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="e6b38-135">**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments)](pidtagmessageattachments-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="e6b38-135">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="e6b38-136">Attachment 表</span><span class="sxs-lookup"><span data-stu-id="e6b38-136">Attachment table</span></span>  <br/> |
|<span data-ttu-id="e6b38-137">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="e6b38-137">PR_MESSAGE_RECIPIENTS</span></span>  <br/> |<span data-ttu-id="e6b38-138">收件人表</span><span class="sxs-lookup"><span data-stu-id="e6b38-138">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e6b38-139">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6b38-139">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6b38-140">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6b38-140">Protocol specifications</span></span>

<span data-ttu-id="e6b38-141">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6b38-141">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6b38-142">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e6b38-142">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6b38-143">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6b38-143">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6b38-144">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="e6b38-144">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="e6b38-145">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6b38-145">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6b38-146">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="e6b38-146">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="e6b38-147">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6b38-147">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6b38-148">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="e6b38-148">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="e6b38-149">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6b38-149">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6b38-150">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="e6b38-150">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6b38-151">头文件</span><span class="sxs-lookup"><span data-stu-id="e6b38-151">Header files</span></span>

<span data-ttu-id="e6b38-152">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6b38-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6b38-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6b38-153">Provides data type definitions.</span></span>
    
<span data-ttu-id="e6b38-154">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e6b38-154">Mapitags.h</span></span>
  
> <span data-ttu-id="e6b38-155">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e6b38-155">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6b38-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b38-156">See also</span></span>



[<span data-ttu-id="e6b38-157">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6b38-157">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6b38-158">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6b38-158">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6b38-159">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6b38-159">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6b38-160">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6b38-160">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

