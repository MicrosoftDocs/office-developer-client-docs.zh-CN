---
title: 支持对象访问和比较
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aac7c6c5-6896-4824-ba36-81bb292777a9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2152cfbb91f2e343ebcee3f5b717a29805df1d25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778938"
---
# <a name="supporting-object-access-and-comparison"></a><span data-ttu-id="35dd3-103">支持对象访问和比较</span><span class="sxs-lookup"><span data-stu-id="35dd3-103">Supporting Object Access and Comparison</span></span>

  
  
<span data-ttu-id="35dd3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="35dd3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="35dd3-105">服务提供商可以使用[IMAPISupport::OpenEntry](imapisupport-openentry.md)和[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)方法打开和比较属于其提供程序或其他提供程序的对象：</span><span class="sxs-lookup"><span data-stu-id="35dd3-105">Service providers can use the [IMAPISupport::OpenEntry](imapisupport-openentry.md) and [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) methods to open and compare objects that belong to their provider or to other providers:</span></span> 
  
<span data-ttu-id="35dd3-106">客户端[IMAPISession::OpenEntry](imapisession-openentry.md) ，如提供程序可以使用其支持对象的**OpenEntry**方法来访问任何对象，如长他们知道对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="35dd3-106">Like [IMAPISession::OpenEntry](imapisession-openentry.md) for clients, providers can use their support object's **OpenEntry** method to access any object as long they know the object's entry identifier.</span></span> <span data-ttu-id="35dd3-107">会话与方法不同，支持方法需要_lpEntryID_参数中指定一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="35dd3-107">Unlike the session method, the support method requires that you specify a valid entry identifier in the  _lpEntryID_ parameter.</span></span> <span data-ttu-id="35dd3-108">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="35dd3-108">It cannot be NULL.</span></span> 
  
<span data-ttu-id="35dd3-109">为了说明如何传输提供程序可能使用**IMAPISupport::OpenEntry**，请考虑下面的方案。</span><span class="sxs-lookup"><span data-stu-id="35dd3-109">To illustrate how a transport provider might use **IMAPISupport::OpenEntry**, consider the following scenario.</span></span> <span data-ttu-id="35dd3-110">传输提供程序已收到邮件格式的富文本格式，并不知道目标接收人是否可以处理此格式。</span><span class="sxs-lookup"><span data-stu-id="35dd3-110">The transport provider has received a message formatted in Rich Text Format and does not know whether the target recipient can handle this format.</span></span> <span data-ttu-id="35dd3-111">邮件传递之前, 传输提供程序需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="35dd3-111">Before delivering the message, the transport provider needs to do the following:</span></span>
  
1. <span data-ttu-id="35dd3-112">调用消息的[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法，以访问收件人表和收件人的项标识符，其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="35dd3-112">Call the message's [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method to access the recipient table and the recipient's entry identifier, its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="35dd3-113">向**IMAPISupport::OpenEntry**打开收件人，通常任一消息的用户或通讯组列表传递的项标识符。</span><span class="sxs-lookup"><span data-stu-id="35dd3-113">Pass the entry identifier to **IMAPISupport::OpenEntry** to open the recipient, typically either a messaging user or distribution list.</span></span> <span data-ttu-id="35dd3-114">_LpInterface_参数应设置为 NULL，因为提供程序无法知道提早制定的收件人对象类型。</span><span class="sxs-lookup"><span data-stu-id="35dd3-114">The  _lpInterface_ parameter should be set to NULL because the provider cannot know ahead of time the object type of the recipient.</span></span> <span data-ttu-id="35dd3-115">支持对象的**OpenEntry**方法调用[IMAPISession::OpenEntry](imapisession-openentry.md)确定负责收件人的地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="35dd3-115">The support object's **OpenEntry** method calls [IMAPISession::OpenEntry](imapisession-openentry.md) to determine the address book provider responsible for the recipient.</span></span> <span data-ttu-id="35dd3-116">会话对象将调用相应的通讯簿提供程序的**OpenEntry**方法以打开收件人，并返回到传输提供程序的接口指针。</span><span class="sxs-lookup"><span data-stu-id="35dd3-116">The session object then calls the appropriate address book provider's **OpenEntry** method to open the recipient and return an interface pointer to the transport provider.</span></span> 
    
3. <span data-ttu-id="35dd3-117">调用收件人的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="35dd3-117">Call the recipient's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property.</span></span> <span data-ttu-id="35dd3-118">如果**PR_SEND_RICH_INFO**设置为 TRUE，则收件人可处理带格式的文本。</span><span class="sxs-lookup"><span data-stu-id="35dd3-118">If **PR_SEND_RICH_INFO** is set to TRUE, the recipient can handle formatted text.</span></span> 
    
<span data-ttu-id="35dd3-119">如果您已经从其他提供程序打开多个对象，您可能需要以找出两个条目标识符是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="35dd3-119">If you have opened several objects from other providers, you may need to find out whether two entry identifiers refer to the same object.</span></span> <span data-ttu-id="35dd3-120">例如，您可能遇到的短期条目标识符和长期的项标识符和这些标识符可能也可能未识别相同的对象。</span><span class="sxs-lookup"><span data-stu-id="35dd3-120">For example, you may have a short-term entry identifier and a long-term entry identifier and these identifiers may or may not identify the same object.</span></span> <span data-ttu-id="35dd3-121">若要避免冗余处理，调用[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)方法以比较这些条目标识符。</span><span class="sxs-lookup"><span data-stu-id="35dd3-121">To avoid redundant processing, call the [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md) method to compare these entry identifiers.</span></span> <span data-ttu-id="35dd3-122">您必须使用此方法的项标识符比较，因为条目标识符不能直接进行比较。</span><span class="sxs-lookup"><span data-stu-id="35dd3-122">You must use this method for entry identifier comparison because entry identifiers cannot be compared directly.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="35dd3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35dd3-123">See also</span></span>



[<span data-ttu-id="35dd3-124">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="35dd3-124">MAPI Service Providers</span></span>](mapi-service-providers.md)

