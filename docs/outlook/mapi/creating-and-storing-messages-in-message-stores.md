---
title: 在邮件存储中创建和存储邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc74b31c-d7ed-4fcf-9535-a2f9222901b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7c923a330c542dff8b1bbc476461ccd21680a5b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332898"
---
# <a name="creating-and-storing-messages-in-message-stores"></a><span data-ttu-id="f65a6-103">在邮件存储中创建和存储邮件</span><span class="sxs-lookup"><span data-stu-id="f65a6-103">Creating and Storing Messages in Message Stores</span></span>

  
  
<span data-ttu-id="f65a6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f65a6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f65a6-105">邮件存储提供程序如何在基础存储机制中创建和存储邮件很大程度上取决于基础存储机制本身。</span><span class="sxs-lookup"><span data-stu-id="f65a6-105">How your message store provider creates and stores messages in the underlying storage mechanism depends heavily on the underlying storage mechanism itself.</span></span> <span data-ttu-id="f65a6-106">一般情况下，仅需要编写代码来保存邮件的属性及其值。</span><span class="sxs-lookup"><span data-stu-id="f65a6-106">In general, you need only to write code to preserve the properties of a message and their values.</span></span>
  
<span data-ttu-id="f65a6-107">当邮件存储提供程序创建新邮件时，提供程序需要使用邮件的必需属性创建邮件。</span><span class="sxs-lookup"><span data-stu-id="f65a6-107">When the message store provider creates a new message, the provider needs to create the message with the required properties for messages.</span></span> <span data-ttu-id="f65a6-108">可以在 [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md) 界面的文档中找到这些属性的列表。</span><span class="sxs-lookup"><span data-stu-id="f65a6-108">A list of these properties can be found in the documentation for the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface.</span></span> <span data-ttu-id="f65a6-109">之后，客户端应用程序可使用 [IMAPIProp](imapipropiunknown.md) 方法添加任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="f65a6-109">After that, client applications add any additional properties with [IMAPIProp](imapipropiunknown.md) methods.</span></span> 
  
<span data-ttu-id="f65a6-110">当邮件存储提供程序将邮件保存到基础存储机制时，提供程序需要循环访问该邮件的属性，并将其保存到基础存储机制，以便在稍后打开邮件时可以完全恢复它们。</span><span class="sxs-lookup"><span data-stu-id="f65a6-110">When the message store provider saves a message to the underlying storage mechanism, the provider needs to iterate over the message's properties, and save them to the underlying storage mechanism such that they can be fully recovered if the message is later opened.</span></span>
  
<span data-ttu-id="f65a6-111">MAPI 需要对 [IMessage](imessageimapiprop.md) 界面上的属性进行事务处理，这意味着在邮件对象上调用  [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法之前，对其所作的更改不会永久。</span><span class="sxs-lookup"><span data-stu-id="f65a6-111">MAPI requires that the properties on [IMessage](imessageimapiprop.md) interfaces are transacted, meaning that changes made to them do not become permanent until the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is called on the message object.</span></span> <span data-ttu-id="f65a6-112">邮件存储提供程序负责实现这一行为。</span><span class="sxs-lookup"><span data-stu-id="f65a6-112">The message store provider is responsible for implementing this behavior.</span></span> <span data-ttu-id="f65a6-113">通常这并不困难；这只是意味着在修改属性时将其保留在内存中并在调用 **SaveChanges** 时将它们提交给基础存储机制。</span><span class="sxs-lookup"><span data-stu-id="f65a6-113">Usually this is not difficult; it simply means holding properties in memory while they are being modified and committing them to the underlying storage mechanism when **SaveChanges** is called.</span></span> 
  
<span data-ttu-id="f65a6-114">就 **SaveChanges** 方法而言，邮件对象上的某些属性对客户端应用程序有着特殊的语义，如下：</span><span class="sxs-lookup"><span data-stu-id="f65a6-114">Some properties on message objects have special semantics for client applications with respect to the **SaveChanges** method, as follows:</span></span> 
  
- <span data-ttu-id="f65a6-115">某些属性在调用 **SaveChanges** 之前为读/写，但之后为只读。</span><span class="sxs-lookup"><span data-stu-id="f65a6-115">Some properties should be read/write before **SaveChanges** is called, but read-only afterward.</span></span> <span data-ttu-id="f65a6-116">例如，**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 最初由创建邮件的客户端应用程序设置（因此是读/写），但首次调用 **SaveChanges** 之后无法更改。</span><span class="sxs-lookup"><span data-stu-id="f65a6-116">For example, **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) is set initially by the client application that creates the message (and thus is read/write) but cannot be changed after the first call to **SaveChanges**.</span></span>
    
- <span data-ttu-id="f65a6-117">某些属性与它们所在文件夹上的属性或 **IMAPIFolder** 方法有特殊关系。</span><span class="sxs-lookup"><span data-stu-id="f65a6-117">Some properties have special relations to properties on the folder they are in or to **IMAPIFolder** methods.</span></span> <span data-ttu-id="f65a6-118">例如，**PR_MESSAGE_FLAGS** 属性与 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 调用使用的标签相关。</span><span class="sxs-lookup"><span data-stu-id="f65a6-118">For example, the **PR_MESSAGE_FLAGS** property is related to the flags used on the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) call.</span></span> 
    
- <span data-ttu-id="f65a6-119">某些属性在首次调用 **SaveChanges** 前不可用。</span><span class="sxs-lookup"><span data-stu-id="f65a6-119">Some properties may not be available until **SaveChanges** is called for the first time.</span></span> <span data-ttu-id="f65a6-120">例如，**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性在调用 **SaveChanges** 前不可用。</span><span class="sxs-lookup"><span data-stu-id="f65a6-120">For example, the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property may not be available until **SaveChanges** is called.</span></span> 
    
- <span data-ttu-id="f65a6-121">某些属性可能与邮件对象上的其他属性有特殊关系。</span><span class="sxs-lookup"><span data-stu-id="f65a6-121">Some properties can have special relationships to other properties on the message object.</span></span> <span data-ttu-id="f65a6-122">例如，**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性通常派生自支持 RTF 格式邮件的邮件存储提供程序中的 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f65a6-122">For example, the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property is usually derived from the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property in message store providers that support Rich Text Format messages.</span></span>
    
- <span data-ttu-id="f65a6-123">某些属性用于与邮件存储相关的多个对象类型。</span><span class="sxs-lookup"><span data-stu-id="f65a6-123">Some properties are used by more than one object type related to message stores.</span></span> <span data-ttu-id="f65a6-124">例如，**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性在文件夹和邮件对象以及以及邮件存储对象上都是必需的。</span><span class="sxs-lookup"><span data-stu-id="f65a6-124">For example, the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property is required on folder and message objects as well as message store objects.</span></span>
    
<span data-ttu-id="f65a6-125">邮件存储提供程序有责任实现这些属性的正确语义。</span><span class="sxs-lookup"><span data-stu-id="f65a6-125">It is the responsibility of the message store provider to implement the correct semantics for such properties.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f65a6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f65a6-126">See also</span></span>



[<span data-ttu-id="f65a6-127">实现邮件存储中的邮件</span><span class="sxs-lookup"><span data-stu-id="f65a6-127">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

