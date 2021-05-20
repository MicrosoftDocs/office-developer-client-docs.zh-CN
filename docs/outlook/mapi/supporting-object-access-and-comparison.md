---
title: 支持对象访问和比较
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aac7c6c5-6896-4824-ba36-81bb292777a9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b62f92325fcebf8cd3f0c86d28d98e7ff511ee2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429031"
---
# <a name="supporting-object-access-and-comparison"></a><span data-ttu-id="c2b77-103">支持对象访问和比较</span><span class="sxs-lookup"><span data-stu-id="c2b77-103">Supporting Object Access and Comparison</span></span>

  
  
<span data-ttu-id="c2b77-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c2b77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c2b77-105">服务提供商可以使用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 和 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md) 方法打开并比较属于其提供程序或其他提供程序的对象：</span><span class="sxs-lookup"><span data-stu-id="c2b77-105">Service providers can use the [IMAPISupport::OpenEntry](imapisupport-openentry.md) and [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) methods to open and compare objects that belong to their provider or to other providers:</span></span> 
  
<span data-ttu-id="c2b77-106">与 [适用于客户端的 IMAPISession：：OpenEntry](imapisession-openentry.md) 一样，提供程序可以使用其支持对象的 **OpenEntry** 方法访问任何对象，只要他们知道对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c2b77-106">Like [IMAPISession::OpenEntry](imapisession-openentry.md) for clients, providers can use their support object's **OpenEntry** method to access any object as long they know the object's entry identifier.</span></span> <span data-ttu-id="c2b77-107">与会话方法不同，支持方法要求在  _lpEntryID_ 参数中指定有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c2b77-107">Unlike the session method, the support method requires that you specify a valid entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="c2b77-108">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c2b77-108">It cannot be NULL.</span></span> 
  
<span data-ttu-id="c2b77-109">为了说明传输提供程序如何使用 **IMAPISupport：：OpenEntry，** 请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="c2b77-109">To illustrate how a transport provider might use **IMAPISupport::OpenEntry**, consider the following scenario.</span></span> <span data-ttu-id="c2b77-110">传输提供程序已收到格式为富文本格式的邮件，并且不知道目标收件人是否可以处理此格式。</span><span class="sxs-lookup"><span data-stu-id="c2b77-110">The transport provider has received a message formatted in Rich Text Format and does not know whether the target recipient can handle this format.</span></span> <span data-ttu-id="c2b77-111">在传递邮件之前，传输提供程序需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c2b77-111">Before delivering the message, the transport provider needs to do the following:</span></span>
  
1. <span data-ttu-id="c2b77-112">调用邮件的[IMessage：：GetRecipientTable](imessage-getrecipienttable.md)方法以访问收件人表和收件人的条目标识符、PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="c2b77-112">Call the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method to access the recipient table and the recipient's entry identifier, its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="c2b77-113">将条目标识符传递到 **IMAPISupport：：OpenEntry** 以打开收件人，通常是邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c2b77-113">Pass the entry identifier to **IMAPISupport::OpenEntry** to open the recipient, typically either a messaging user or distribution list.</span></span> <span data-ttu-id="c2b77-114">_lpInterface_ 参数应设置为 NULL，因为提供程序无法提前知道收件人对象类型的名称。</span><span class="sxs-lookup"><span data-stu-id="c2b77-114">The  _lpInterface_ parameter should be set to NULL because the provider cannot know ahead of time the object type of the recipient.</span></span> <span data-ttu-id="c2b77-115">支持对象的 **OpenEntry** 方法调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 来确定负责收件人的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="c2b77-115">The support object's **OpenEntry** method calls [IMAPISession::OpenEntry](imapisession-openentry.md) to determine the address book provider responsible for the recipient.</span></span> <span data-ttu-id="c2b77-116">然后，会话对象调用相应的通讯簿提供程序的 **OpenEntry** 方法以打开收件人，并返回指向传输提供程序的接口指针。</span><span class="sxs-lookup"><span data-stu-id="c2b77-116">The session object then calls the appropriate address book provider's **OpenEntry** method to open the recipient and return an interface pointer to the transport provider.</span></span> 
    
3. <span data-ttu-id="c2b77-117">调用收件人的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来 **检索其** PR_SEND_RICH_INFO ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c2b77-117">Call the recipient's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property.</span></span> <span data-ttu-id="c2b77-118">如果 **PR_SEND_RICH_INFO** 设置为 TRUE，则收件人可以处理格式化的文本。</span><span class="sxs-lookup"><span data-stu-id="c2b77-118">If **PR_SEND_RICH_INFO** is set to TRUE, the recipient can handle formatted text.</span></span> 
    
<span data-ttu-id="c2b77-119">如果您打开了其他提供程序中的多个对象，您可能需要了解两个条目标识符是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="c2b77-119">If you have opened several objects from other providers, you may need to find out whether two entry identifiers refer to the same object.</span></span> <span data-ttu-id="c2b77-120">例如，你可能有一个短期条目标识符和一个长期条目标识符，这些标识符可能标识同一个对象，也可以不标识同一个对象。</span><span class="sxs-lookup"><span data-stu-id="c2b77-120">For example, you may have a short-term entry identifier and a long-term entry identifier and these identifiers may or may not identify the same object.</span></span> <span data-ttu-id="c2b77-121">为了避免冗余处理，请调用 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md) 方法来比较这些条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c2b77-121">To avoid redundant processing, call the [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) method to compare these entry identifiers.</span></span> <span data-ttu-id="c2b77-122">必须使用此方法进行条目标识符比较，因为不能直接比较条目标识符。</span><span class="sxs-lookup"><span data-stu-id="c2b77-122">You must use this method for entry identifier comparison because entry identifiers cannot be compared directly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c2b77-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2b77-123">See also</span></span>



[<span data-ttu-id="c2b77-124">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c2b77-124">MAPI Service Providers</span></span>](mapi-service-providers.md)

