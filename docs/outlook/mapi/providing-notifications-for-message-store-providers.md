---
title: 为邮件存储提供程序提供通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0e1cdba-ceb6-4a3f-8449-79d1a0ad1adf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a28e6e6f008517a6b1c2c82dfa391b478963880f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419931"
---
# <a name="providing-notifications-for-message-store-providers"></a><span data-ttu-id="ea4ea-103">为邮件存储提供程序提供通知</span><span class="sxs-lookup"><span data-stu-id="ea4ea-103">Providing Notifications for Message Store Providers</span></span>

  
  
<span data-ttu-id="ea4ea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ea4ea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ea4ea-105">虽然通知是可选的, 但它们是良好邮件存储提供程序的一个非常重要的部分。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-105">While notifications are optional, they are a very important part of a good message store provider.</span></span> <span data-ttu-id="ea4ea-106">在提交传出邮件或接收传入邮件时, 客户端应用程序和 MAPI 后台处理程序依赖来自邮件存储提供程序的通知, 以获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-106">Client applications and the MAPI spooler rely on notifications from the message store provider to get good performance when submitting outgoing messages or receiving incoming messages.</span></span> <span data-ttu-id="ea4ea-107">客户端和 MAPI 后台处理程序可以正常运行, 而无需接收来自邮件存储提供程序的通知, 但他们无法通知用户邮件存储区中的更改。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-107">Clients and the MAPI spooler can function without receiving notifications from the message store provider, but they will not be able to inform users of changes in the message store without them.</span></span> <span data-ttu-id="ea4ea-108">通常情况下, 这意味着用户将无法看到新邮件已到达, 直到其客户端下一步打开邮件存储的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-108">Typically, this means that users will be unable to see that a new message has arrived until their client next opens the message store's receive folder.</span></span>
  
<span data-ttu-id="ea4ea-109">客户端通过调用[IMsgStore:: Advise](imsgstore-advise.md)方法注册通知。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-109">Clients register for notifications by calling the [IMsgStore::Advise](imsgstore-advise.md) method.</span></span> <span data-ttu-id="ea4ea-110">客户端在[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口中传递, 指示客户端所要接收的通知类型的位掩码, 以及指示邮件存储中的哪个对象的**条目**。**建议**请求适用于。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-110">The client passes in an [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface, a bitmask that indicates what type of notifications the client is interested in receiving, and an **EntryID** that indicates which object in the message store the **Advise** request applies to.</span></span> <span data-ttu-id="ea4ea-111">当对象中发生相关事件时 (例如, 当新邮件到达邮件存储区中的接收文件夹时), 邮件存储提供程序或对象本身应调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的所有\*\*\*\* 已为该事件类型注册的 IMAPIAdviseSink 对象。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-111">When relevant events occur in the object (for example, when a new message arrives in the receive folder in the message store), the message store provider or the object itself should call the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for all of the **IMAPIAdviseSink** objects that have registered for that event type.</span></span> 
  
<span data-ttu-id="ea4ea-112">即使您的邮件存储提供程序永远不会向其他 MAPI 组件通知邮件存储区中发生的更改, 它仍应实现**IMsgStore:: 建议**返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-112">Even if your message store provider never notifies other MAPI components of changes in the message store, it should still implement **IMsgStore::Advise** to return MAPI_E_NO_SUPPORT.</span></span> <span data-ttu-id="ea4ea-113">这会通知其他组件不会收到来自邮件存储提供程序的通知。</span><span class="sxs-lookup"><span data-stu-id="ea4ea-113">This informs other components not to expect notifications from the message store provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ea4ea-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea4ea-114">See also</span></span>



[<span data-ttu-id="ea4ea-115">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="ea4ea-115">Message Store Features</span></span>](message-store-features.md)

