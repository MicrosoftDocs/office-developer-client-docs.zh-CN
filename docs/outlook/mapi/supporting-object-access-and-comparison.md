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
# <a name="supporting-object-access-and-comparison"></a><span data-ttu-id="0ef63-103">支持对象访问和比较</span><span class="sxs-lookup"><span data-stu-id="0ef63-103">Supporting Object Access and Comparison</span></span>

  
  
<span data-ttu-id="0ef63-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ef63-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ef63-105">服务提供程序可以使用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)和[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)方法打开并比较属于其提供程序的对象或其他提供程序:</span><span class="sxs-lookup"><span data-stu-id="0ef63-105">Service providers can use the [IMAPISupport::OpenEntry](imapisupport-openentry.md) and [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) methods to open and compare objects that belong to their provider or to other providers:</span></span> 
  
<span data-ttu-id="0ef63-106">与[IMAPISession:: OpenEntry](imapisession-openentry.md) for 客户端一样, 提供程序可以使用其支持对象的**OpenEntry**方法访问任何对象, 只要他们知道对象的条目标识符即可。</span><span class="sxs-lookup"><span data-stu-id="0ef63-106">Like [IMAPISession::OpenEntry](imapisession-openentry.md) for clients, providers can use their support object's **OpenEntry** method to access any object as long they know the object's entry identifier.</span></span> <span data-ttu-id="0ef63-107">与 session 方法不同, 支持方法要求您在_lpEntryID_参数中指定一个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0ef63-107">Unlike the session method, the support method requires that you specify a valid entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="0ef63-108">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0ef63-108">It cannot be NULL.</span></span> 
  
<span data-ttu-id="0ef63-109">若要说明传输提供程序如何使用**IMAPISupport:: OpenEntry**, 请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="0ef63-109">To illustrate how a transport provider might use **IMAPISupport::OpenEntry**, consider the following scenario.</span></span> <span data-ttu-id="0ef63-110">传输提供程序收到了格式为 rtf 格式的邮件, 并不知道目标收件人是否可以处理此格式。</span><span class="sxs-lookup"><span data-stu-id="0ef63-110">The transport provider has received a message formatted in Rich Text Format and does not know whether the target recipient can handle this format.</span></span> <span data-ttu-id="0ef63-111">在传递邮件之前, 传输提供程序需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="0ef63-111">Before delivering the message, the transport provider needs to do the following:</span></span>
  
1. <span data-ttu-id="0ef63-112">调用邮件的[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法以访问收件人表和收件人的条目标识符, 其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0ef63-112">Call the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method to access the recipient table and the recipient's entry identifier, its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="0ef63-113">将条目标识符传递给**IMAPISupport:: OpenEntry**以打开收件人, 通常是邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="0ef63-113">Pass the entry identifier to **IMAPISupport::OpenEntry** to open the recipient, typically either a messaging user or distribution list.</span></span> <span data-ttu-id="0ef63-114">应将_lpInterface_参数设置为 NULL, 因为提供程序无法提前知道收件人的对象类型。</span><span class="sxs-lookup"><span data-stu-id="0ef63-114">The  _lpInterface_ parameter should be set to NULL because the provider cannot know ahead of time the object type of the recipient.</span></span> <span data-ttu-id="0ef63-115">支持对象的**OpenEntry**方法调用[IMAPISession:: OpenEntry](imapisession-openentry.md)以确定负责收件人的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ef63-115">The support object's **OpenEntry** method calls [IMAPISession::OpenEntry](imapisession-openentry.md) to determine the address book provider responsible for the recipient.</span></span> <span data-ttu-id="0ef63-116">然后, session 对象将调用相应的通讯簿提供程序的**OpenEntry**方法, 以打开收件人并将接口指针返回到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ef63-116">The session object then calls the appropriate address book provider's **OpenEntry** method to open the recipient and return an interface pointer to the transport provider.</span></span> 
    
3. <span data-ttu-id="0ef63-117">调用收件人的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0ef63-117">Call the recipient's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property.</span></span> <span data-ttu-id="0ef63-118">如果将**PR_SEND_RICH_INFO**设置为 TRUE, 则收件人可以处理带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="0ef63-118">If **PR_SEND_RICH_INFO** is set to TRUE, the recipient can handle formatted text.</span></span> 
    
<span data-ttu-id="0ef63-119">如果您已从其他提供程序中打开了多个对象, 则可能需要了解两个条目标识符是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="0ef63-119">If you have opened several objects from other providers, you may need to find out whether two entry identifiers refer to the same object.</span></span> <span data-ttu-id="0ef63-120">例如, 您可能有一个短期条目标识符和一个长期条目标识符, 并且这些标识符可以标识同一个对象, 也可以不标识。</span><span class="sxs-lookup"><span data-stu-id="0ef63-120">For example, you may have a short-term entry identifier and a long-term entry identifier and these identifiers may or may not identify the same object.</span></span> <span data-ttu-id="0ef63-121">若要避免冗余处理, 请调用[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)方法来比较这些条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0ef63-121">To avoid redundant processing, call the [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) method to compare these entry identifiers.</span></span> <span data-ttu-id="0ef63-122">由于条目标识符不能直接进行比较, 因此您必须使用此方法进行条目标识符比较。</span><span class="sxs-lookup"><span data-stu-id="0ef63-122">You must use this method for entry identifier comparison because entry identifiers cannot be compared directly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0ef63-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef63-123">See also</span></span>



[<span data-ttu-id="0ef63-124">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0ef63-124">MAPI Service Providers</span></span>](mapi-service-providers.md)

