---
title: 支持邮件存储区提供程序的邮件附件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d5fabc40-71e8-4afa-9846-533da605ce6c
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: a94d1230f4f26d080976fd15768bdfeb6ea04748
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576097"
---
# <a name="supporting-message-attachments-for-message-store-providers"></a><span data-ttu-id="d9202-103">支持邮件存储区提供程序的邮件附件</span><span class="sxs-lookup"><span data-stu-id="d9202-103">Supporting Message Attachments for Message Store Providers</span></span>

 
  
<span data-ttu-id="d9202-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9202-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9202-105">消息存储提供程序不需要支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="d9202-105">Your message store provider does not need to support message attachments.</span></span> <span data-ttu-id="d9202-106">但是，多个客户端应用程序还希望能够将附件添加到邮件。</span><span class="sxs-lookup"><span data-stu-id="d9202-106">However, many client applications expect to be able to add attachments to messages.</span></span> <span data-ttu-id="d9202-107">如果您的消息存储将用于创建或存储 IPM。说明消息，则您应支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="d9202-107">If your message store will be used to create or store IPM.Note messages, then you should support message attachments.</span></span> <span data-ttu-id="d9202-108">默认消息存储提供程序还应支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="d9202-108">Default message store providers should also support message attachments.</span></span> <span data-ttu-id="d9202-109">有关详细信息，请参阅[MAPI 邮件类](mapi-message-classes.md)和[默认邮件存储区](default-message-stores.md)。</span><span class="sxs-lookup"><span data-stu-id="d9202-109">For more information, see [MAPI Message Classes](mapi-message-classes.md), and [Default Message Stores](default-message-stores.md).</span></span>
  
<span data-ttu-id="d9202-110">有五种类型的附件的 MAPI 支持： 文件附件、 数据附件、 邮件附件、 OLE 对象附件和链接。</span><span class="sxs-lookup"><span data-stu-id="d9202-110">There are five types of attachments that MAPI supports: file attachments, data attachments, message attachments, OLE object attachments, and links.</span></span> <span data-ttu-id="d9202-111">支持每种类型的要求具有不同。</span><span class="sxs-lookup"><span data-stu-id="d9202-111">The requirements for supporting each type are different.</span></span> <span data-ttu-id="d9202-112">客户端区分两种类型的附件通过 attachment 对象的**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d9202-112">Clients differentiate between the two types of attachments by means of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property on attachment objects.</span></span>
  
<span data-ttu-id="d9202-113">支持附件意味着实现[IAttach: IMAPIProp](iattachimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d9202-113">Supporting attachments means implementing the [IAttach : IMAPIProp](iattachimapiprop.md) interface.</span></span> <span data-ttu-id="d9202-114">此**IAttach**接口具有自己的; 没有方法它具有仅从[IMAPIProp](imapipropiunknown.md)接口继承的方法。</span><span class="sxs-lookup"><span data-stu-id="d9202-114">The **IAttach** interface has no methods of its own; it has only methods that are inherited from the [IMAPIProp](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="d9202-115">消息存储提供程序必须已实现消息对象的属性，因为这大大简化了支持的附件的任务。</span><span class="sxs-lookup"><span data-stu-id="d9202-115">Because your message store provider must already implement properties for message objects, this greatly simplifies the task of supporting attachments.</span></span> <span data-ttu-id="d9202-116">基本上实现**IAttach**意味着提供一种客户端访问的特定邮件的附件的属性表的方法。</span><span class="sxs-lookup"><span data-stu-id="d9202-116">Implementing **IAttach** basically means providing a way for clients to access a table of properties for particular attachments on messages.</span></span> 
  
<span data-ttu-id="d9202-117">数据附件是只需为其直接在附件**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性中存储附件的内容的附件。</span><span class="sxs-lookup"><span data-stu-id="d9202-117">Data attachments are simply attachments for which the contents of the attachment are stored directly in an attachment's **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property.</span></span> <span data-ttu-id="d9202-118">数据附件存在主要是为了使客户端可以将文件附加到一条消息，当发件人和收件人的邮件没有访问常见的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="d9202-118">Data attachments exist primarily to allow clients to attach files to a message when the sender and the recipient of the message do not have access to a common file server.</span></span> <span data-ttu-id="d9202-119">有关详细信息，请参阅**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d9202-119">For more information, see the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="d9202-120">邮件附件的附件的附件子对象是另一个[IMessage: MAPIProp](imessageimapiprop.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d9202-120">Message attachments are attachments for which the attachment subobject is another [IMessage : MAPIProp](imessageimapiprop.md) object.</span></span> <span data-ttu-id="d9202-121">由于消息存储提供程序已经支持**IMessage**接口，并不难支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="d9202-121">Because message store providers already support the **IMessage** interface, supporting message attachments is not difficult.</span></span> 
  
<span data-ttu-id="d9202-122">支持 OLE 对象附件意味着实现 OLE **IStorage**、 **IStream**和**IStreamDocfile**接口。</span><span class="sxs-lookup"><span data-stu-id="d9202-122">Supporting OLE object attachments means implementing the OLE **IStorage**, **IStream**, and **IStreamDocfile** interfaces.</span></span> <span data-ttu-id="d9202-123">消息存储提供程序必须能够将客户端打开对象时到活动的 OLE 对象存储在消息中的 OLE 对象数据转换。</span><span class="sxs-lookup"><span data-stu-id="d9202-123">Your message store provider must be able to convert OLE object data stored in the message into an active OLE object when a client opens the object.</span></span> 
  
<span data-ttu-id="d9202-124">链接有两种类型： 指向文件和指向其他消息。</span><span class="sxs-lookup"><span data-stu-id="d9202-124">Links come in two types: links to files and links to other messages.</span></span> <span data-ttu-id="d9202-125">文件的链接以及**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) **PR_ATTACH_METHOD**属性使用 ATTACH_BY_REF_ONLY 值指定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d9202-125">Links to files use the ATTACH_BY_REF_ONLY value for the **PR_ATTACH_METHOD** property along with **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) or **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) to specify the location of a file.</span></span>
  
<span data-ttu-id="d9202-126">一个如何实现指向邮件可能依赖于本地邮件系统的方面，因此，不能完全此处介绍。</span><span class="sxs-lookup"><span data-stu-id="d9202-126">How one implements links to messages may depend on aspects of the local messaging system and, as such, cannot be fully documented here.</span></span> <span data-ttu-id="d9202-127">例如，将链接发送给一条消息，对基于服务器的消息存储存储通常是消息的只需发送链接，提供的发件人和收件人有权访问该服务器的项标识符。</span><span class="sxs-lookup"><span data-stu-id="d9202-127">For example, sending a link to a message that is stored on a server-based message store is typically just a matter of sending the entry identifier of the linked message, providing that both the sender and recipient have access to that server.</span></span> <span data-ttu-id="d9202-128">其他消息的系统配置提供其他要求和实现指向邮件难题。</span><span class="sxs-lookup"><span data-stu-id="d9202-128">Other messaging system configurations present other requirements and challenges for implementing links to messages.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9202-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9202-129">See also</span></span>



[<span data-ttu-id="d9202-130">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="d9202-130">Message Store Features</span></span>](message-store-features.md)

