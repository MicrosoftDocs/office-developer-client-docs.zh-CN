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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 980b1b81a0afbfe05fee915ddd730aad31811132
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777861"
---
# <a name="pidtagmessagerecipients-canonical-property"></a><span data-ttu-id="edd03-103">PidTagMessageRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="edd03-103">PidTagMessageRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="edd03-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="edd03-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="edd03-105">包含可应用到内容表中查找包含满足限制的收件人子对象的所有消息的限制的表。</span><span class="sxs-lookup"><span data-stu-id="edd03-105">Contains a table of restrictions that can be applied to a contents table to find all messages that contain recipient subobjects that meet the restrictions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="edd03-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="edd03-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="edd03-107">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="edd03-107">PR_MESSAGE_RECIPIENTS</span></span>  <br/> |
|<span data-ttu-id="edd03-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="edd03-108">Identifier:</span></span>  <br/> |<span data-ttu-id="edd03-109">0x0E12</span><span class="sxs-lookup"><span data-stu-id="edd03-109">0x0E12</span></span>  <br/> |
|<span data-ttu-id="edd03-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="edd03-110">Data type:</span></span>  <br/> |<span data-ttu-id="edd03-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="edd03-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="edd03-112">区域：</span><span class="sxs-lookup"><span data-stu-id="edd03-112">Area:</span></span>  <br/> |<span data-ttu-id="edd03-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="edd03-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="edd03-114">备注</span><span class="sxs-lookup"><span data-stu-id="edd03-114">Remarks</span></span>

<span data-ttu-id="edd03-115">可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。</span><span class="sxs-lookup"><span data-stu-id="edd03-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="edd03-116">作为**PT_OBJECT**类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="edd03-116">As a property of type **PT_OBJECT**, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="edd03-117">应由请求**IID_IMAPITable**接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。</span><span class="sxs-lookup"><span data-stu-id="edd03-117">Its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="edd03-118">服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法如果设置，但可以选择将其报告或不如果它未设置。</span><span class="sxs-lookup"><span data-stu-id="edd03-118">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="edd03-119">若要检索目录，客户端应用程序应调用[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="edd03-119">To retrieve table contents, a client application should call the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method.</span></span> 
  
<span data-ttu-id="edd03-120">此属性可用于任务的子对象限制通过指定[SSubRestriction](ssubrestriction.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="edd03-120">This property can be used for subobject restriction by specifying it in the [SSubRestriction](ssubrestriction.md) structure.</span></span> <span data-ttu-id="edd03-121">这样的客户端限制到会议的收件人的邮件给定条件的容器的视图。</span><span class="sxs-lookup"><span data-stu-id="edd03-121">This enables a client to limit the view of a container to messages with recipients meeting given criteria.</span></span> <span data-ttu-id="edd03-122">查看如果其收件人表，即一个收件人中的至少一个行满足子对象限制符合一条消息。</span><span class="sxs-lookup"><span data-stu-id="edd03-122">A message qualifies for viewing if at least one row in its recipient table, that is, one recipient satisfies the subobject restriction.</span></span> 
  
 <span data-ttu-id="edd03-123">**注释**使用子对象限制结果是相当于[IMAPISession::OpenEntry](imapisession-openentry.md)呼叫上表中的每条消息。</span><span class="sxs-lookup"><span data-stu-id="edd03-123">**Note** Using subobject restriction results is the equivalent of an [IMAPISession::OpenEntry](imapisession-openentry.md) call on every message in the table.</span></span> <span data-ttu-id="edd03-124">根据客户端应用程序和要搜索的消息的数目，它会影响性能。</span><span class="sxs-lookup"><span data-stu-id="edd03-124">Depending on the client application and the number of messages to be searched, it can affect performance.</span></span> 
  
<span data-ttu-id="edd03-125">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性和此属性是在使用率类似。</span><span class="sxs-lookup"><span data-stu-id="edd03-125">The **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property and this property are similar in usage.</span></span> <span data-ttu-id="edd03-126">几个 MAPI 属性提供对表访问：</span><span class="sxs-lookup"><span data-stu-id="edd03-126">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="edd03-127">**属性**</span><span class="sxs-lookup"><span data-stu-id="edd03-127">**Property**</span></span>|<span data-ttu-id="edd03-128">**Table**</span><span class="sxs-lookup"><span data-stu-id="edd03-128">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="edd03-129">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="edd03-129">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="edd03-130">内容表</span><span class="sxs-lookup"><span data-stu-id="edd03-130">Contents table</span></span>  <br/> |
|<span data-ttu-id="edd03-131">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="edd03-131">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="edd03-132">层次结构表</span><span class="sxs-lookup"><span data-stu-id="edd03-132">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="edd03-133">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="edd03-133">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="edd03-134">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="edd03-134">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="edd03-135">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="edd03-135">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="edd03-136">附件表</span><span class="sxs-lookup"><span data-stu-id="edd03-136">Attachment table</span></span>  <br/> |
|<span data-ttu-id="edd03-137">PR_MESSAGE_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="edd03-137">PR_MESSAGE_RECIPIENTS</span></span>  <br/> |<span data-ttu-id="edd03-138">收件人表</span><span class="sxs-lookup"><span data-stu-id="edd03-138">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="edd03-139">相关资源</span><span class="sxs-lookup"><span data-stu-id="edd03-139">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="edd03-140">协议规范</span><span class="sxs-lookup"><span data-stu-id="edd03-140">Protocol specifications</span></span>

<span data-ttu-id="edd03-141">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="edd03-141">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="edd03-142">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="edd03-142">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="edd03-143">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="edd03-143">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="edd03-144">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="edd03-144">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="edd03-145">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="edd03-145">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="edd03-146">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="edd03-146">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="edd03-147">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="edd03-147">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="edd03-148">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="edd03-148">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="edd03-149">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="edd03-149">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="edd03-150">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="edd03-150">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="edd03-151">头文件</span><span class="sxs-lookup"><span data-stu-id="edd03-151">Header files</span></span>

<span data-ttu-id="edd03-152">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="edd03-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="edd03-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="edd03-153">Provides data type definitions.</span></span>
    
<span data-ttu-id="edd03-154">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="edd03-154">Mapitags.h</span></span>
  
> <span data-ttu-id="edd03-155">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="edd03-155">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="edd03-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edd03-156">See also</span></span>



[<span data-ttu-id="edd03-157">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="edd03-157">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="edd03-158">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="edd03-158">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="edd03-159">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="edd03-159">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="edd03-160">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="edd03-160">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

