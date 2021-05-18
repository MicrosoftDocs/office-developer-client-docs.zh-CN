---
title: 支持邮件存储提供程序的邮件附件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d5fabc40-71e8-4afa-9846-533da605ce6c
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 69d1df5bf206cddd0d25698665c9fd87b81e4ea5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412133"
---
# <a name="supporting-message-attachments-for-message-store-providers"></a><span data-ttu-id="3891d-103">支持邮件存储提供程序的邮件附件</span><span class="sxs-lookup"><span data-stu-id="3891d-103">Supporting Message Attachments for Message Store Providers</span></span>

 
  
<span data-ttu-id="3891d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3891d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3891d-105">您的邮件存储提供程序不需要支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3891d-105">Your message store provider does not need to support message attachments.</span></span> <span data-ttu-id="3891d-106">但是，许多客户端应用程序希望能够向邮件添加附件。</span><span class="sxs-lookup"><span data-stu-id="3891d-106">However, many client applications expect to be able to add attachments to messages.</span></span> <span data-ttu-id="3891d-107">如果你的邮件存储将用于创建或存储 IPM。请注意邮件，然后应支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3891d-107">If your message store will be used to create or store IPM.Note messages, then you should support message attachments.</span></span> <span data-ttu-id="3891d-108">默认邮件存储提供程序还应支持邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3891d-108">Default message store providers should also support message attachments.</span></span> <span data-ttu-id="3891d-109">有关详细信息，请参阅[MAPI Message Classes](mapi-message-classes.md)和[Default Message Stores。](default-message-stores.md)</span><span class="sxs-lookup"><span data-stu-id="3891d-109">For more information, see [MAPI Message Classes](mapi-message-classes.md), and [Default Message Stores](default-message-stores.md).</span></span>
  
<span data-ttu-id="3891d-110">MAPI 支持五种类型的附件：文件附件、数据附件、邮件附件、OLE 对象附件和链接。</span><span class="sxs-lookup"><span data-stu-id="3891d-110">There are five types of attachments that MAPI supports: file attachments, data attachments, message attachments, OLE object attachments, and links.</span></span> <span data-ttu-id="3891d-111">支持每种类型的要求是不同的。</span><span class="sxs-lookup"><span data-stu-id="3891d-111">The requirements for supporting each type are different.</span></span> <span data-ttu-id="3891d-112">客户端通过附件对象的[PidTagAttachMethod PR_ATTACH_METHOD (PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 区分这两种类型的附件。 </span><span class="sxs-lookup"><span data-stu-id="3891d-112">Clients differentiate between the two types of attachments by means of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property on attachment objects.</span></span>
  
<span data-ttu-id="3891d-113">支持附件意味着实现 [IAttach ： IMAPIProp](iattachimapiprop.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="3891d-113">Supporting attachments means implementing the [IAttach : IMAPIProp](iattachimapiprop.md) interface.</span></span> <span data-ttu-id="3891d-114">**IAttach** 接口没有其自己的方法;它只有从 [IMAPIProp](imapipropiunknown.md)接口继承的方法。</span><span class="sxs-lookup"><span data-stu-id="3891d-114">The **IAttach** interface has no methods of its own; it has only methods that are inherited from the [IMAPIProp](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="3891d-115">由于邮件存储提供程序必须已经实现邮件对象的属性，这大大简化了支持附件的任务。</span><span class="sxs-lookup"><span data-stu-id="3891d-115">Because your message store provider must already implement properties for message objects, this greatly simplifies the task of supporting attachments.</span></span> <span data-ttu-id="3891d-116">实现 **IAttach 基本上** 意味着为客户端提供访问邮件上特定附件的属性表的方法。</span><span class="sxs-lookup"><span data-stu-id="3891d-116">Implementing **IAttach** basically means providing a way for clients to access a table of properties for particular attachments on messages.</span></span> 
  
<span data-ttu-id="3891d-117">数据附件只是附件附件的内容直接存储在附件的 PR_ATTACH_DATA_BIN ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 附件。 </span><span class="sxs-lookup"><span data-stu-id="3891d-117">Data attachments are simply attachments for which the contents of the attachment are stored directly in an attachment's **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property.</span></span> <span data-ttu-id="3891d-118">数据附件主要是为了允许客户端在邮件的发件人和收件人无法访问公用文件服务器时将文件附加到邮件。</span><span class="sxs-lookup"><span data-stu-id="3891d-118">Data attachments exist primarily to allow clients to attach files to a message when the sender and the recipient of the message do not have access to a common file server.</span></span> <span data-ttu-id="3891d-119">有关详细信息，请参阅 PR_ATTACH_METHOD  ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3891d-119">For more information, see the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="3891d-120">邮件附件是附件子对象是另一 [个 IMessage ： MAPIProp 对象的](imessageimapiprop.md) 附件。</span><span class="sxs-lookup"><span data-stu-id="3891d-120">Message attachments are attachments for which the attachment subobject is another [IMessage : MAPIProp](imessageimapiprop.md) object.</span></span> <span data-ttu-id="3891d-121">由于邮件存储提供程序已经支持 **IMessage** 接口，因此支持邮件附件并不困难。</span><span class="sxs-lookup"><span data-stu-id="3891d-121">Because message store providers already support the **IMessage** interface, supporting message attachments is not difficult.</span></span> 
  
<span data-ttu-id="3891d-122">支持 OLE 对象附件意味着实现 OLE **IStorage、IStream** 和 **IStreamDocfile** 接口。</span><span class="sxs-lookup"><span data-stu-id="3891d-122">Supporting OLE object attachments means implementing the OLE **IStorage**, **IStream**, and **IStreamDocfile** interfaces.</span></span> <span data-ttu-id="3891d-123">当客户端打开邮件时，邮件存储提供程序必须能够将邮件中存储的 OLE 对象数据转换为活动 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="3891d-123">Your message store provider must be able to convert OLE object data stored in the message into an active OLE object when a client opens the object.</span></span> 
  
<span data-ttu-id="3891d-124">链接有两种类型：指向文件的链接和指向其他邮件的链接。</span><span class="sxs-lookup"><span data-stu-id="3891d-124">Links come in two types: links to files and links to other messages.</span></span> <span data-ttu-id="3891d-125">指向文件的链接使用 **PR_ATTACH_METHOD** 属性的 ATTACH_BY_REF_ONLY 值以及 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或 **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 来指定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="3891d-125">Links to files use the ATTACH_BY_REF_ONLY value for the **PR_ATTACH_METHOD** property along with **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) or **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) to specify the location of a file.</span></span>
  
<span data-ttu-id="3891d-126">实现指向邮件的链接可能取决于本地邮件系统的各个方面，因此无法在此处完整记录。</span><span class="sxs-lookup"><span data-stu-id="3891d-126">How one implements links to messages may depend on aspects of the local messaging system and, as such, cannot be fully documented here.</span></span> <span data-ttu-id="3891d-127">例如，向基于服务器的邮件存储中存储的邮件发送链接通常只是发送链接邮件的条目标识符，只要发件人和收件人都有权访问该服务器。</span><span class="sxs-lookup"><span data-stu-id="3891d-127">For example, sending a link to a message that is stored on a server-based message store is typically just a matter of sending the entry identifier of the linked message, providing that both the sender and recipient have access to that server.</span></span> <span data-ttu-id="3891d-128">其他邮件系统配置对实现指向邮件的链接提出了其他要求和难题。</span><span class="sxs-lookup"><span data-stu-id="3891d-128">Other messaging system configurations present other requirements and challenges for implementing links to messages.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3891d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3891d-129">See also</span></span>



[<span data-ttu-id="3891d-130">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="3891d-130">Message Store Features</span></span>](message-store-features.md)

