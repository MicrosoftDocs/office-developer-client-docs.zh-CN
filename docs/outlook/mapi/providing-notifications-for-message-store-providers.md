---
title: 提供通知消息存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0e1cdba-ceb6-4a3f-8449-79d1a0ad1adf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3abb4ba67ff5f0cf2284fa9286b6968698877b84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778579"
---
# <a name="providing-notifications-for-message-store-providers"></a><span data-ttu-id="b5edb-103">提供通知消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="b5edb-103">Providing Notifications for Message Store Providers</span></span>

  
  
<span data-ttu-id="b5edb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b5edb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b5edb-105">可选通知时，它们是非常重要一部分正确消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="b5edb-105">While notifications are optional, they are a very important part of a good message store provider.</span></span> <span data-ttu-id="b5edb-106">客户端应用程序和 MAPI 后台处理程序都依赖从消息存储提供程序的通知，以提交传出消息或接收的传入消息时获得良好的性能。</span><span class="sxs-lookup"><span data-stu-id="b5edb-106">Client applications and the MAPI spooler rely on notifications from the message store provider to get good performance when submitting outgoing messages or receiving incoming messages.</span></span> <span data-ttu-id="b5edb-107">客户端和 MAPI 后台处理程序可以正常而不会收到通知从消息存储提供程序，但它们不将能够向用户告知没有它们的消息存储中的更改。</span><span class="sxs-lookup"><span data-stu-id="b5edb-107">Clients and the MAPI spooler can function without receiving notifications from the message store provider, but they will not be able to inform users of changes in the message store without them.</span></span> <span data-ttu-id="b5edb-108">通常，这意味着用户将无法看到他们的客户端下一步将打开的消息存储之前，已到达新邮件的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="b5edb-108">Typically, this means that users will be unable to see that a new message has arrived until their client next opens the message store's receive folder.</span></span>
  
<span data-ttu-id="b5edb-109">通过调用[IMsgStore::Advise](imsgstore-advise.md)方法，客户端注册通知。</span><span class="sxs-lookup"><span data-stu-id="b5edb-109">Clients register for notifications by calling the [IMsgStore::Advise](imsgstore-advise.md) method.</span></span> <span data-ttu-id="b5edb-110">客户端传入[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口，一个位掩码，指示哪种类型的通知客户端是有兴趣接收，并指示邮件中的对象的**EntryID**存储**Advise**应用于请求。</span><span class="sxs-lookup"><span data-stu-id="b5edb-110">The client passes in an [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface, a bitmask that indicates what type of notifications the client is interested in receiving, and an **EntryID** that indicates which object in the message store the **Advise** request applies to.</span></span> <span data-ttu-id="b5edb-111">相关事件发生时 （例如，当新邮件的接收文件夹中的消息存储到达） 对象中，消息存储提供程序或对象本身应调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的**所有IMAPIAdviseSink** ，已注册的事件类型的对象。</span><span class="sxs-lookup"><span data-stu-id="b5edb-111">When relevant events occur in the object (for example, when a new message arrives in the receive folder in the message store), the message store provider or the object itself should call the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for all of the **IMAPIAdviseSink** objects that have registered for that event type.</span></span> 
  
<span data-ttu-id="b5edb-112">即使您的消息存储提供程序从不通知中的邮件存储区中，更改其他 MAPI 组件仍应该实现**IMsgStore::Advise**返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="b5edb-112">Even if your message store provider never notifies other MAPI components of changes in the message store, it should still implement **IMsgStore::Advise** to return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="b5edb-113">这将通知其他组件不希望从邮件的通知存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="b5edb-113">This informs other components not to expect notifications from the message store provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b5edb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5edb-114">See also</span></span>



[<span data-ttu-id="b5edb-115">消息存储功能</span><span class="sxs-lookup"><span data-stu-id="b5edb-115">Message Store Features</span></span>](message-store-features.md)

