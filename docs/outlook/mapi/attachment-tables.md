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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318135"
---
# <a name="attachment-tables"></a><span data-ttu-id="d6ae9-103">附件表</span><span class="sxs-lookup"><span data-stu-id="d6ae9-103">Attachment tables</span></span>

<span data-ttu-id="d6ae9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6ae9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d6ae9-105">附件表包含与提交的邮件或撰写中的邮件相关联的所有附件对象的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-105">An attachment table contains information about all of the attachment objects that are associated with a submitted message or a message under composition.</span></span> 
  
<span data-ttu-id="d6ae9-106">只有通过对邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用保存的附件才包含在表中。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-106">Only attachments that have been saved through a call to the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method are included in the table.</span></span> <span data-ttu-id="d6ae9-107">附件表由邮件存储提供程序实现, 并由客户端应用程序和传输提供程序使用。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-107">Attachment tables are implemented by message store providers and used by client applications and transport providers.</span></span> 
  
<span data-ttu-id="d6ae9-108">可以通过调用以下任一方法来访问附件表:</span><span class="sxs-lookup"><span data-stu-id="d6ae9-108">An attachment table can be accessed by calling either of the following:</span></span>
  
- [<span data-ttu-id="d6ae9-109">IMessage::GetAttachmentTable</span><span class="sxs-lookup"><span data-stu-id="d6ae9-109">IMessage::GetAttachmentTable</span></span>](imessage-getattachmenttable.md)
    
- <span data-ttu-id="d6ae9-110">[IMAPIProp:: OpenProperty](imapiprop-openproperty.md), 请求**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-110">[IMAPIProp::OpenProperty](imapiprop-openproperty.md), requesting the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="d6ae9-111">附件表是动态的。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-111">Attachment tables are dynamic.</span></span>
  
<span data-ttu-id="d6ae9-112">邮件存储提供程序不需要支持对其附件表进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-112">Message store providers are not required to support sorting on their attachment tables.</span></span> <span data-ttu-id="d6ae9-113">如果不支持排序, 则必须按呈现位置的顺序 ( **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性) 显示表。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-113">If sorting is not supported, the table must be presented in order by rendering position — the **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="d6ae9-114">邮件存储提供程序也不需要支持对其附件表的限制。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-114">Message store providers are also not required to support restrictions on their attachment tables.</span></span> <span data-ttu-id="d6ae9-115">不支持限制的提供程序将从其[IMAPITable:: Restrict](imapitable-restrict.md)和[IMAPITable:: FindRow](imapitable-findrow.md)的实现中返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-115">Providers that do not support restrictions return MAPI_E_NO_SUPPORT from their implementations of [IMAPITable::Restrict](imapitable-restrict.md) and [IMAPITable::FindRow](imapitable-findrow.md).</span></span>
  
<span data-ttu-id="d6ae9-116">附件表可能很小;在必需的列集中只有四列:</span><span class="sxs-lookup"><span data-stu-id="d6ae9-116">Attachment tables can be small; there are only four columns in the required column set:</span></span>
  
- <span data-ttu-id="d6ae9-117">**PR_ATTACH_NUM**([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-117">**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d6ae9-118">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-118">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d6ae9-119">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-119">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d6ae9-120">**PR_RENDERING_POSITION**</span><span class="sxs-lookup"><span data-stu-id="d6ae9-120">**PR_RENDERING_POSITION**</span></span>
    
 <span data-ttu-id="d6ae9-121">**PR_ATTACH_NUM**为 nontransmittable, 并且包含一个用于唯一标识邮件中的附件的值。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-121">**PR_ATTACH_NUM** is nontransmittable and contains a value for uniquely identifying an attachment within a message.</span></span> <span data-ttu-id="d6ae9-122">此属性通常用作表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-122">This property is often used as an index into the rows of the table.</span></span> <span data-ttu-id="d6ae9-123">**PR_ATTACH_NUM**的生命周期较短;仅当包含附件的邮件处于打开状态时, 此方法才有效。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-123">**PR_ATTACH_NUM** has a short lifespan; it is only valid while the message containing the attachment is open.</span></span> <span data-ttu-id="d6ae9-124">只要附件表打开, 它的值就会保持不变。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-124">Its value is guaranteed to remain constant as long as the attachment table is open.</span></span> 
  
 <span data-ttu-id="d6ae9-125">**PR_INSTANCE_KEY**在几乎每个表中都是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-125">**PR_INSTANCE_KEY** is required in nearly every table.</span></span> <span data-ttu-id="d6ae9-126">它用于唯一标识特定行。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-126">It is used to uniquely identify a particular row.</span></span> 
  
 <span data-ttu-id="d6ae9-127">**PR_RECORD_KEY**通常用于唯一标识用于比较目的的对象。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-127">**PR_RECORD_KEY** is commonly used to uniquely identify an object for comparison purposes.</span></span> <span data-ttu-id="d6ae9-128">与**PR_ATTACH_NUM**不同, **PR_RECORD_KEY**的作用域与长期条目标识符的作用域相同;即使在关闭并重新打开邮件之后, 它仍然可用且有效。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-128">Unlike **PR_ATTACH_NUM**, **PR_RECORD_KEY** has the same scope as a long-term entry identifier; it remains available and valid even after the message is closed and reopened.</span></span> <span data-ttu-id="d6ae9-129">有关 mapi 中使用记录密钥的详细信息, 请参阅[mapi 记录和搜索关键字](mapi-record-and-search-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-129">For more information about the use of record keys in MAPI, see [MAPI Record and Search Keys](mapi-record-and-search-keys.md).</span></span>
  
 <span data-ttu-id="d6ae9-130">**PR_RENDERING_POSITION**指示附件在 rtf 邮件中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-130">**PR_RENDERING_POSITION** indicates how an attachment should be displayed in a rich text message.</span></span> <span data-ttu-id="d6ae9-131">它可以设置为以字符为单位的偏移量, 邮件内容的第一个字符存储在**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中, 而不是偏移量为 0, 或为-1 (0xffffffff), 指示不应在邮件中呈现附件文本。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-131">It can be set to an offset in characters, with the first character of the message content as stored in the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property being offset 0, or to -1 (0xFFFFFFFF), indicating that the attachment should not be rendered within the message text at all.</span></span> <span data-ttu-id="d6ae9-132">不设置**PR_RENDERING_POSITION**也是一个选项。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-132">Not setting **PR_RENDERING_POSITION** is also an option.</span></span> 
  
<span data-ttu-id="d6ae9-133">当按呈现位置对附件表进行排序时, 邮件存储提供程序会将其视为有符号值 (PT_LONG)。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-133">When an attachment table is sorted by rendering position, the message store provider treats it as a signed value (PT_LONG).</span></span> <span data-ttu-id="d6ae9-134">因此, 呈现位置为-1 的附件在显示反映有效偏移量的呈现位置的附件之前进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-134">Therefore, attachments with rendering positions of -1 are sorted before attachments with rendering positions that reflect valid offsets.</span></span> 
  
<span data-ttu-id="d6ae9-135">有关在纯文本邮件中呈现附件的详细信息, 请参阅[以纯文本格式呈现附件](rendering-an-attachment-in-plain-text.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-135">For more information about rendering an attachment in a plain text message, see [Rendering an Attachment in Plain Text](rendering-an-attachment-in-plain-text.md).</span></span> 
  
<span data-ttu-id="d6ae9-136">有关使用格式化文本 (如 rtf 格式) 呈现附件的信息, 请参阅[在 rtf 文本中呈现附件](rendering-an-attachment-in-rtf-text.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ae9-136">For information about rendering an attachment in formatted text such as Rich Text Format (RTF), see [Rendering an Attachment in RTF Text](rendering-an-attachment-in-rtf-text.md).</span></span>
  
<span data-ttu-id="d6ae9-137">某些属性邮件存储提供程序通常包含在附件表中, 因为它们易于计算或检索:</span><span class="sxs-lookup"><span data-stu-id="d6ae9-137">Some of the properties message store providers commonly include in an attachment table because they are easy to compute or retrieve are:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d6ae9-138">**PR_ATTACH_ENCODING**([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-138">**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-139">**PR_ATTACH_EXTENSION**([PidTagAttachExtension](pidtagattachextension-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-139">**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="d6ae9-140">**PR_ATTACH_FILENAME**([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-140">**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-141">**PR_ATTACH_LONG_FILENAME**([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-141">**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="d6ae9-142">**PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-142">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-143">**PR_ATTACH_LONG_PATHNAME**([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-143">**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="d6ae9-144">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-144">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-145">**PR_ATTACH_TAG**([PidTagAttachTag](pidtagattachtag-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-145">**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="d6ae9-146">**PR_CREATION_TIME**([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-146">**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-147">**PR_ATTACH_TRANSPORT_NAME**([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-147">**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="d6ae9-148">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-148">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d6ae9-149">**操作**([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d6ae9-149">**PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d6ae9-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ae9-150">See also</span></span>

- [<span data-ttu-id="d6ae9-151">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="d6ae9-151">MAPI Tables</span></span>](mapi-tables.md)

