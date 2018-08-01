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
ms.openlocfilehash: 2fd79cfe18e7d39f26563c87b8fb15553bf32ddf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774570"
---
# <a name="attachment-tables"></a><span data-ttu-id="cdfbf-103">附件表</span><span class="sxs-lookup"><span data-stu-id="cdfbf-103">Attachment tables</span></span>

<span data-ttu-id="cdfbf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cdfbf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cdfbf-105">附件表包含有关与已提交的邮件或在组合下的一条消息相关联的 attachment 对象的所有信息。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-105">An attachment table contains information about all of the attachment objects that are associated with a submitted message or a message under composition.</span></span> 
  
<span data-ttu-id="cdfbf-106">通过调用消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法已保存的附件包含在表中。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-106">Only attachments that have been saved through a call to the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method are included in the table.</span></span> <span data-ttu-id="cdfbf-107">附件表由消息存储提供程序实现并使用客户端应用程序和传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-107">Attachment tables are implemented by message store providers and used by client applications and transport providers.</span></span> 
  
<span data-ttu-id="cdfbf-108">附件表可通过调用以下任一项：</span><span class="sxs-lookup"><span data-stu-id="cdfbf-108">An attachment table can be accessed by calling either of the following:</span></span>
  
- [<span data-ttu-id="cdfbf-109">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="cdfbf-109">IMessage::GetAttachmentTable</span></span>](imessage-getattachmenttable.md)
    
- <span data-ttu-id="cdfbf-110">[IMAPIProp::OpenProperty](imapiprop-openproperty.md)，请求**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-110">[IMAPIProp::OpenProperty](imapiprop-openproperty.md), requesting the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="cdfbf-111">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-111">Attachment tables are dynamic.</span></span>
  
<span data-ttu-id="cdfbf-112">消息存储提供程序不需要支持对其附件表排序。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-112">Message store providers are not required to support sorting on their attachment tables.</span></span> <span data-ttu-id="cdfbf-113">如果不支持进行排序，必须按呈现位置顺序显示表 — **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-113">If sorting is not supported, the table must be presented in order by rendering position — the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="cdfbf-114">消息存储提供程序不还需要支持其附件表上的限制。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-114">Message store providers are also not required to support restrictions on their attachment tables.</span></span> <span data-ttu-id="cdfbf-115">不支持限制的提供程序返回的[IMAPITable::Restrict](imapitable-restrict.md)和[IMAPITable::FindRow](imapitable-findrow.md)其实现 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-115">Providers that do not support restrictions return MAPI_E_NO_SUPPORT from their implementations of [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md).</span></span>
  
<span data-ttu-id="cdfbf-116">附件表可以小型;所需的列设置中有仅四列：</span><span class="sxs-lookup"><span data-stu-id="cdfbf-116">Attachment tables can be small; there are only four columns in the required column set:</span></span>
  
- <span data-ttu-id="cdfbf-117">**PR_ATTACH_NUM**([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-117">**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="cdfbf-118">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-118">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="cdfbf-119">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-119">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="cdfbf-120">**PR_RENDERING_POSITION**</span><span class="sxs-lookup"><span data-stu-id="cdfbf-120">**PR_RENDERING_POSITION**</span></span>
    
 <span data-ttu-id="cdfbf-121">**PR_ATTACH_NUM** nontransmittable 并包含用于唯一地标识邮件中的附件的值。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-121">**PR_ATTACH_NUM** is nontransmittable and contains a value for uniquely identifying an attachment within a message.</span></span> <span data-ttu-id="cdfbf-122">此属性通常用作索引到 table 的行。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-122">This property is often used as an index into the rows of the table.</span></span> <span data-ttu-id="cdfbf-123">**PR_ATTACH_NUM**具有短寿命;打开包含附件的邮件时才有效。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-123">**PR_ATTACH_NUM** has a short lifespan; it is only valid while the message containing the attachment is open.</span></span> <span data-ttu-id="cdfbf-124">其值保证保持不变，只要附件表处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-124">Its value is guaranteed to remain constant as long as the attachment table is open.</span></span> 
  
 <span data-ttu-id="cdfbf-125">几乎在每个表中需要**PR_INSTANCE_KEY** 。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-125">**PR_INSTANCE_KEY** is required in nearly every table.</span></span> <span data-ttu-id="cdfbf-126">它用于唯一标识的特定行。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-126">It is used to uniquely identify a particular row.</span></span> 
  
 <span data-ttu-id="cdfbf-127">**PR_RECORD_KEY**通常用于唯一标识为了进行比较的对象。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-127">**PR_RECORD_KEY** is commonly used to uniquely identify an object for comparison purposes.</span></span> <span data-ttu-id="cdfbf-128">与**PR_ATTACH_NUM**，不同**PR_RECORD_KEY**具有相同的范围的长期的项标识符;尚待可用且有效，即使关闭并重新打开该邮件。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-128">Unlike **PR_ATTACH_NUM**, **PR_RECORD_KEY** has the same scope as a long-term entry identifier; it remains available and valid even after the message is closed and reopened.</span></span> <span data-ttu-id="cdfbf-129">有关使用 MAPI 中的记录项的详细信息，请参阅[MAPI 记录和搜索键](mapi-record-and-search-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-129">For more information about the use of record keys in MAPI, see [MAPI Record and Search Keys](mapi-record-and-search-keys.md).</span></span>
  
 <span data-ttu-id="cdfbf-130">**PR_RENDERING_POSITION**指示附件格式文本消息中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-130">**PR_RENDERING_POSITION** indicates how an attachment should be displayed in a rich text message.</span></span> <span data-ttu-id="cdfbf-131">它可以设为字符，如要偏移 0， **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中存储的消息内容的第一个字符中的偏移量或为-1 (0xFFFFFFFF)，指示附件应不呈现在邮件内部在所有的文本。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-131">It can be set to an offset in characters, with the first character of the message content as stored in the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property being offset 0, or to -1 (0xFFFFFFFF), indicating that the attachment should not be rendered within the message text at all.</span></span> <span data-ttu-id="cdfbf-132">不设置**PR_RENDERING_POSITION**也是一个选项。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-132">Not setting **PR_RENDERING_POSITION** is also an option.</span></span> 
  
<span data-ttu-id="cdfbf-133">附件表进行排序的呈现位置时, 的消息存储提供程序会将其视为有符号值 (PT_LONG)。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-133">When an attachment table is sorted by rendering position, the message store provider treats it as a signed value (PT_LONG).</span></span> <span data-ttu-id="cdfbf-134">因此，具有呈现位置为-1 附件进行排序之前具有反映有效偏移量的呈现位置的附件。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-134">Therefore, attachments with rendering positions of -1 are sorted before attachments with rendering positions that reflect valid offsets.</span></span> 
  
<span data-ttu-id="cdfbf-135">关于呈现纯文本邮件的附件的详细信息，请参阅[呈现纯文本中的附件](rendering-an-attachment-in-plain-text.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-135">For more information about rendering an attachment in a plain text message, see [Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md).</span></span> 
  
<span data-ttu-id="cdfbf-136">关于呈现附件格式化文本如富文本格式 (RTF) 中的信息，请参阅[呈现 RTF 文本中的附件](rendering-an-attachment-in-rtf-text.md)。</span><span class="sxs-lookup"><span data-stu-id="cdfbf-136">For information about rendering an attachment in formatted text such as Rich Text Format (RTF), see [Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md).</span></span>
  
<span data-ttu-id="cdfbf-137">下面是一些消息存储提供程序通常包括附件表格中因为它们是易于计算或检索的属性：</span><span class="sxs-lookup"><span data-stu-id="cdfbf-137">Some of the properties message store providers commonly include in an attachment table because they are easy to compute or retrieve are:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cdfbf-138">**PR_ATTACH_ENCODING**([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-138">**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-139">**PR_ATTACH_EXTENSION**([PidTagAttachExtension](pidtagattachextension-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-139">**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="cdfbf-140">**PR_ATTACH_FILENAME**([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-140">**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-141">**PR_ATTACH_LONG_FILENAME**([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-141">**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="cdfbf-142">**PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-142">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-143">**PR_ATTACH_LONG_PATHNAME**([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-143">**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="cdfbf-144">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-144">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-145">**PR_ATTACH_TAG**([PidTagAttachTag](pidtagattachtag-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-145">**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="cdfbf-146">**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-146">**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-147">**PR_ATTACH_TRANSPORT_NAME**([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-147">**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="cdfbf-148">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-148">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="cdfbf-149">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="cdfbf-149">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cdfbf-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdfbf-150">See also</span></span>

- [<span data-ttu-id="cdfbf-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="cdfbf-151">MAPI Tables</span></span>](mapi-tables.md)

