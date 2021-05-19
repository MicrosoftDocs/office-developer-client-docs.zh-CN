---
title: 附件表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 92a07f7b-d34c-4085-ab11-eadcd918fa1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4aa800b504e7ffb07d94ace6d8dc30c1463ed637
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427441"
---
# <a name="attachment-tables"></a><span data-ttu-id="856c4-103">附件表</span><span class="sxs-lookup"><span data-stu-id="856c4-103">Attachment tables</span></span>

<span data-ttu-id="856c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="856c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="856c4-105">附件表包含有关与提交的邮件或组合下的邮件关联的所有附件对象的信息。</span><span class="sxs-lookup"><span data-stu-id="856c4-105">An attachment table contains information about all of the attachment objects that are associated with a submitted message or a message under composition.</span></span> 
  
<span data-ttu-id="856c4-106">表中仅包含通过调用邮件 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存的附件。</span><span class="sxs-lookup"><span data-stu-id="856c4-106">Only attachments that have been saved through a call to the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method are included in the table.</span></span> <span data-ttu-id="856c4-107">附件表由邮件存储提供程序实现，由客户端应用程序和传输提供程序使用。</span><span class="sxs-lookup"><span data-stu-id="856c4-107">Attachment tables are implemented by message store providers and used by client applications and transport providers.</span></span> 
  
<span data-ttu-id="856c4-108">可以通过调用以下任一方法访问附件表：</span><span class="sxs-lookup"><span data-stu-id="856c4-108">An attachment table can be accessed by calling either of the following:</span></span>
  
- [<span data-ttu-id="856c4-109">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="856c4-109">IMessage::GetAttachmentTable</span></span>](imessage-getattachmenttable.md)
    
- <span data-ttu-id="856c4-110">[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)，请求PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="856c4-110">[IMAPIProp::OpenProperty](imapiprop-openproperty.md), requesting the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="856c4-111">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="856c4-111">Attachment tables are dynamic.</span></span>
  
<span data-ttu-id="856c4-112">邮件存储提供程序不需要支持对附件表进行排序。</span><span class="sxs-lookup"><span data-stu-id="856c4-112">Message store providers are not required to support sorting on their attachment tables.</span></span> <span data-ttu-id="856c4-113">如果不支持排序，则表必须按呈现位置（PR_RENDERING_POSITION ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 显示。 </span><span class="sxs-lookup"><span data-stu-id="856c4-113">If sorting is not supported, the table must be presented in order by rendering position — the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="856c4-114">邮件存储提供程序也不需要支持对附件表的限制。</span><span class="sxs-lookup"><span data-stu-id="856c4-114">Message store providers are also not required to support restrictions on their attachment tables.</span></span> <span data-ttu-id="856c4-115">不支持限制的提供程序将MAPI_E_NO_SUPPORT [IMAPITable：：Restrict](imapitable-restrict.md) 和 [IMAPITable：：FindRow](imapitable-findrow.md)的实现返回值。</span><span class="sxs-lookup"><span data-stu-id="856c4-115">Providers that do not support restrictions return MAPI_E_NO_SUPPORT from their implementations of [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md).</span></span>
  
<span data-ttu-id="856c4-116">附件表可以较小;所需的列集只有四列：</span><span class="sxs-lookup"><span data-stu-id="856c4-116">Attachment tables can be small; there are only four columns in the required column set:</span></span>
  
- <span data-ttu-id="856c4-117">**PR_ATTACH_NUM (** [PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-117">**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="856c4-118">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-118">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="856c4-119">**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-119">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="856c4-120">**PR_RENDERING_POSITION**</span><span class="sxs-lookup"><span data-stu-id="856c4-120">**PR_RENDERING_POSITION**</span></span>
    
 <span data-ttu-id="856c4-121">**PR_ATTACH_NUM** 不可传递，并且包含用于唯一标识邮件中的附件的值。</span><span class="sxs-lookup"><span data-stu-id="856c4-121">**PR_ATTACH_NUM** is nontransmittable and contains a value for uniquely identifying an attachment within a message.</span></span> <span data-ttu-id="856c4-122">此属性通常用作表行的索引。</span><span class="sxs-lookup"><span data-stu-id="856c4-122">This property is often used as an index into the rows of the table.</span></span> <span data-ttu-id="856c4-123">**PR_ATTACH_NUM** 生存期短;仅在包含附件的邮件打开时有效。</span><span class="sxs-lookup"><span data-stu-id="856c4-123">**PR_ATTACH_NUM** has a short lifespan; it is only valid while the message containing the attachment is open.</span></span> <span data-ttu-id="856c4-124">只要附件表处于打开状态，它的值就保证保持恒定。</span><span class="sxs-lookup"><span data-stu-id="856c4-124">Its value is guaranteed to remain constant as long as the attachment table is open.</span></span> 
  
 <span data-ttu-id="856c4-125">**PR_INSTANCE_KEY** 表都需要此配置。</span><span class="sxs-lookup"><span data-stu-id="856c4-125">**PR_INSTANCE_KEY** is required in nearly every table.</span></span> <span data-ttu-id="856c4-126">它用于唯一标识特定行。</span><span class="sxs-lookup"><span data-stu-id="856c4-126">It is used to uniquely identify a particular row.</span></span> 
  
 <span data-ttu-id="856c4-127">**PR_RECORD_KEY** 用于唯一地标识对象，以便进行比较。</span><span class="sxs-lookup"><span data-stu-id="856c4-127">**PR_RECORD_KEY** is commonly used to uniquely identify an object for comparison purposes.</span></span> <span data-ttu-id="856c4-128">与 **PR_ATTACH_NUM** 不同 **，PR_RECORD_KEY** 具有与长期条目标识符相同的作用域;即使关闭并重新打开邮件，它仍然可用且有效。</span><span class="sxs-lookup"><span data-stu-id="856c4-128">Unlike **PR_ATTACH_NUM**, **PR_RECORD_KEY** has the same scope as a long-term entry identifier; it remains available and valid even after the message is closed and reopened.</span></span> <span data-ttu-id="856c4-129">有关在 MAPI 中使用记录键的信息，请参阅[MAPI Record and Search Keys。](mapi-record-and-search-keys.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-129">For more information about the use of record keys in MAPI, see [MAPI Record and Search Keys](mapi-record-and-search-keys.md).</span></span>
  
 <span data-ttu-id="856c4-130">**PR_RENDERING_POSITION** 指示附件在格式文本邮件中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="856c4-130">**PR_RENDERING_POSITION** indicates how an attachment should be displayed in a rich text message.</span></span> <span data-ttu-id="856c4-131">它可以设置为字符的偏移，其中 **存储在 PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的邮件内容的第一个字符偏移量为 0，或设置为 -1 (0xFFFFFFFF) ，指示完全不应在邮件文本中呈现附件。</span><span class="sxs-lookup"><span data-stu-id="856c4-131">It can be set to an offset in characters, with the first character of the message content as stored in the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property being offset 0, or to -1 (0xFFFFFFFF), indicating that the attachment should not be rendered within the message text at all.</span></span> <span data-ttu-id="856c4-132">不设置 **PR_RENDERING_POSITION** 也是一个选项。</span><span class="sxs-lookup"><span data-stu-id="856c4-132">Not setting **PR_RENDERING_POSITION** is also an option.</span></span> 
  
<span data-ttu-id="856c4-133">当附件表按呈现位置排序时，邮件存储提供程序会视其为已签名 (PT_LONG) 。</span><span class="sxs-lookup"><span data-stu-id="856c4-133">When an attachment table is sorted by rendering position, the message store provider treats it as a signed value (PT_LONG).</span></span> <span data-ttu-id="856c4-134">因此，呈现位置为 -1 的附件在呈现位置反映有效偏移的附件之前进行排序。</span><span class="sxs-lookup"><span data-stu-id="856c4-134">Therefore, attachments with rendering positions of -1 are sorted before attachments with rendering positions that reflect valid offsets.</span></span> 
  
<span data-ttu-id="856c4-135">有关在纯文本邮件中呈现附件的信息，请参阅以纯文本 [呈现附件](rendering-an-attachment-in-plain-text.md)。</span><span class="sxs-lookup"><span data-stu-id="856c4-135">For more information about rendering an attachment in a plain text message, see [Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md).</span></span> 
  
<span data-ttu-id="856c4-136">有关以 RTF 格式格式等格式文本呈现附件 (RTF) ，请参阅在 [RTF](rendering-an-attachment-in-rtf-text.md)文本中呈现附件。</span><span class="sxs-lookup"><span data-stu-id="856c4-136">For information about rendering an attachment in formatted text such as Rich Text Format (RTF), see [Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md).</span></span>
  
<span data-ttu-id="856c4-137">附件表中通常包括邮件存储提供程序的一些属性，因为它们易于计算或检索：</span><span class="sxs-lookup"><span data-stu-id="856c4-137">Some of the properties message store providers commonly include in an attachment table because they are easy to compute or retrieve are:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="856c4-138">**PR_ATTACH_ENCODING (** [PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-138">**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-139">**PR_ATTACH_EXTENSION (** [PidTagAttachExtension)](pidtagattachextension-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-139">**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="856c4-140">**PR_ATTACH_FILENAME (** [PidTagAttachFilename)](pidtagattachfilename-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-140">**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-141">**PR_ATTACH_LONG_FILENAME (** [PidTagAttachLongFilename)](pidtagattachlongfilename-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-141">**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="856c4-142">**PR_ATTACH_PATHNAME (** [PidTagAttachPathname)](pidtagattachpathname-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-142">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-143">**PR_ATTACH_LONG_PATHNAME (** [PidTagAttachLongPathname)](pidtagattachlongpathname-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-143">**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="856c4-144">**PR_ATTACH_METHOD (** [PidTagAttachMethod)](pidtagattachmethod-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="856c4-144">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-145">**PR_ATTACH_TAG (** [PidTagAttachTag](pidtagattachtag-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-145">**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="856c4-146">**PR_CREATION_TIME (** [PidTagCreationTime](pidtagcreationtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-146">**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-147">**PR_ATTACH_TRANSPORT_NAME (** [PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-147">**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="856c4-148">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-148">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="856c4-149">**PR_LAST_MODIFICATION_TIME (** [PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="856c4-149">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="856c4-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="856c4-150">See also</span></span>

- [<span data-ttu-id="856c4-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="856c4-151">MAPI Tables</span></span>](mapi-tables.md)

