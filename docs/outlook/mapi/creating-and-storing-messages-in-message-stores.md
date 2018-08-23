---
title: 在邮件存储区中创建和存储邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc74b31c-d7ed-4fcf-9535-a2f9222901b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: be718ea3ef4da91d2f85a0229f5a506198a2527f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589173"
---
# <a name="creating-and-storing-messages-in-message-stores"></a><span data-ttu-id="d7595-103">在邮件存储区中创建和存储邮件</span><span class="sxs-lookup"><span data-stu-id="d7595-103">Creating and Storing Messages in Message Stores</span></span>

  
  
<span data-ttu-id="d7595-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7595-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7595-105">消息存储提供程序如何创建和基础存储机制中存储的消息取决于主要基础存储机制本身。</span><span class="sxs-lookup"><span data-stu-id="d7595-105">How your message store provider creates and stores messages in the underlying storage mechanism depends heavily on the underlying storage mechanism itself.</span></span> <span data-ttu-id="d7595-106">一般情况下，则只需编写代码以保留的一条消息，及其值的属性。</span><span class="sxs-lookup"><span data-stu-id="d7595-106">In general, you need only to write code to preserve the properties of a message and their values.</span></span>
  
<span data-ttu-id="d7595-107">当邮件存储提供程序创建一个新的邮件，提供程序需要创建具有所需属性的邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="d7595-107">When the message store provider creates a new message, the provider needs to create the message with the required properties for messages.</span></span> <span data-ttu-id="d7595-108">有关的文档中找不到这些属性的列表[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d7595-108">A list of these properties can be found in the documentation for the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface.</span></span> <span data-ttu-id="d7595-109">之后，客户端应用程序使用[IMAPIProp](imapipropiunknown.md)方法添加的任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="d7595-109">After that, client applications add any additional properties with [IMAPIProp](imapipropiunknown.md) methods.</span></span> 
  
<span data-ttu-id="d7595-110">当邮件存储提供程序保存到基础存储机制一条消息时，提供程序需要循环访问该消息的属性，并将其保存到基础存储机制，以便他们可以完全恢复如果以后打开邮件。</span><span class="sxs-lookup"><span data-stu-id="d7595-110">When the message store provider saves a message to the underlying storage mechanism, the provider needs to iterate over the message's properties, and save them to the underlying storage mechanism such that they can be fully recovered if the message is later opened.</span></span>
  
<span data-ttu-id="d7595-111">MAPI 需要的[IMessage](imessageimapiprop.md)接口上的属性进行事务处理，这意味着，对它们进行更改之前，不会永久消息对象上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d7595-111">MAPI requires that the properties on [IMessage](imessageimapiprop.md) interfaces are transacted, meaning that changes made to them do not become permanent until the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called on the message object.</span></span> <span data-ttu-id="d7595-112">消息存储提供程序负责为实现此行为。</span><span class="sxs-lookup"><span data-stu-id="d7595-112">The message store provider is responsible for implementing this behavior.</span></span> <span data-ttu-id="d7595-113">通常是不变得比较困难;它就意味着修改它们时，在内存中按住属性并将它们提交给基础存储机制，调用**SaveChanges**时。</span><span class="sxs-lookup"><span data-stu-id="d7595-113">Usually this is not difficult; it simply means holding properties in memory while they are being modified and committing them to the underlying storage mechanism when **SaveChanges** is called.</span></span> 
  
<span data-ttu-id="d7595-114">消息对象的某些属性具有特殊的语义相对于**SaveChanges**方法中，客户端应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7595-114">Some properties on message objects have special semantics for client applications with respect to the **SaveChanges** method, as follows:</span></span> 
  
- <span data-ttu-id="d7595-115">**SaveChanges**调用之前，但只读此后，某些属性应为读/写。</span><span class="sxs-lookup"><span data-stu-id="d7595-115">Some properties should be read/write before **SaveChanges** is called, but read-only afterward.</span></span> <span data-ttu-id="d7595-116">例如， **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 的客户端应用程序创建邮件 （并因此是可读写） 最初设置但不能更改后**SaveChanges**为第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7595-116">For example, **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) is set initially by the client application that creates the message (and thus is read/write) but cannot be changed after the first call to **SaveChanges**.</span></span>
    
- <span data-ttu-id="d7595-117">有些属性具有特殊关系与属性，它们是在或给**IMAPIFolder**方法的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d7595-117">Some properties have special relations to properties on the folder they are in or to **IMAPIFolder** methods.</span></span> <span data-ttu-id="d7595-118">例如， **PR_MESSAGE_FLAGS**属性与[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)呼叫使用的标志。</span><span class="sxs-lookup"><span data-stu-id="d7595-118">For example, the **PR_MESSAGE_FLAGS** property is related to the flags used on the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) call.</span></span> 
    
- <span data-ttu-id="d7595-119">一些属性可能不可用，直到**SaveChanges**称为第一次。</span><span class="sxs-lookup"><span data-stu-id="d7595-119">Some properties may not be available until **SaveChanges** is called for the first time.</span></span> <span data-ttu-id="d7595-120">例如， **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性可能不可用调用**SaveChanges**之前。</span><span class="sxs-lookup"><span data-stu-id="d7595-120">For example, the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property may not be available until **SaveChanges** is called.</span></span> 
    
- <span data-ttu-id="d7595-121">有些属性可以 message 对象上具有特殊关系的其他属性。</span><span class="sxs-lookup"><span data-stu-id="d7595-121">Some properties can have special relationships to other properties on the message object.</span></span> <span data-ttu-id="d7595-122">例如， **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性通常源自消息存储提供程序支持富文本格式的邮件中的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d7595-122">For example, the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property is usually derived from the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property in message store providers that support Rich Text Format messages.</span></span>
    
- <span data-ttu-id="d7595-123">某些属性使用多个与邮件存储相关的对象类型。</span><span class="sxs-lookup"><span data-stu-id="d7595-123">Some properties are used by more than one object type related to message stores.</span></span> <span data-ttu-id="d7595-124">例如上的文件夹和对象以及消息存储对象的邮件需要**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d7595-124">For example, the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property is required on folder and message objects as well as message store objects.</span></span>
    
<span data-ttu-id="d7595-125">它是要实现此类属性的正确语义消息存储提供程序的责任。</span><span class="sxs-lookup"><span data-stu-id="d7595-125">It is the responsibility of the message store provider to implement the correct semantics for such properties.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7595-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7595-126">See also</span></span>



[<span data-ttu-id="d7595-127">实现邮件存储区中的邮件</span><span class="sxs-lookup"><span data-stu-id="d7595-127">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

