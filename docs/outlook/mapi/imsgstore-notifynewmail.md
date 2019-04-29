---
title: IMsgStoreNotifyNewMail
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.NotifyNewMail
api_type:
- COM
ms.assetid: d0d003b0-f12f-4422-b71f-26886169461f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a8ec06fd0401a129e08a06acdb1c18785f90d4a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431776"
---
# <a name="imsgstorenotifynewmail"></a><span data-ttu-id="c825e-103">IMsgStore::NotifyNewMail</span><span class="sxs-lookup"><span data-stu-id="c825e-103">IMsgStore::NotifyNewMail</span></span>

  
  
<span data-ttu-id="c825e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c825e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c825e-105">通知邮件存储区新邮件已到达。</span><span class="sxs-lookup"><span data-stu-id="c825e-105">Informs the message store that a new message has arrived.</span></span> <span data-ttu-id="c825e-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="c825e-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT NotifyNewMail(
  LPNOTIFICATION lpNotification
);
```

## <a name="parameters"></a><span data-ttu-id="c825e-107">参数</span><span class="sxs-lookup"><span data-stu-id="c825e-107">Parameters</span></span>

 <span data-ttu-id="c825e-108">_lpNotification_</span><span class="sxs-lookup"><span data-stu-id="c825e-108">_lpNotification_</span></span>
  
> <span data-ttu-id="c825e-109">实时指向描述新邮件通知的[通知](notification.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="c825e-109">[in] A pointer to a [NOTIFICATION](notification.md) structure that describes the new message notification.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c825e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c825e-110">Return value</span></span>

<span data-ttu-id="c825e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c825e-111">S_OK</span></span> 
  
> <span data-ttu-id="c825e-112">成功通知邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="c825e-112">The message store was successfully notified.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c825e-113">说明</span><span class="sxs-lookup"><span data-stu-id="c825e-113">Remarks</span></span>

<span data-ttu-id="c825e-114">MAPI 后台处理程序调用**IMsgStore:: NotifyNewMail**方法, 以通知邮件存储区邮件已准备好传递。</span><span class="sxs-lookup"><span data-stu-id="c825e-114">The **IMsgStore::NotifyNewMail** method is called by the MAPI spooler to inform the message store that a message is ready for delivery.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="c825e-115">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="c825e-115">Notes to implementers</span></span>

<span data-ttu-id="c825e-116">调用**NotifyNewMail**时, 向所有已注册的客户端发送新邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c825e-116">When **NotifyNewMail** is called, send a new mail notification to all registered clients.</span></span> <span data-ttu-id="c825e-117">如果选择使用支持对象方法, 或使用自己的实现, 则可以通过调用[IMAPISupport:: Notify](imapisupport-notify.md)来发送通知。</span><span class="sxs-lookup"><span data-stu-id="c825e-117">You can send the notification by calling [IMAPISupport::Notify](imapisupport-notify.md), if you elect to use the support object methods, or by using your own implementation.</span></span> <span data-ttu-id="c825e-118">已注册的客户端是已调用[IMsgStore:: 建议](imsgstore-advise.md), 并将_lpEntryID_参数设置为 NULL, 并将_ulEventMask_参数设置为_fnevNewMail_。</span><span class="sxs-lookup"><span data-stu-id="c825e-118">A registered client is one that has called [IMsgStore::Advise](imsgstore-advise.md) and set the  _lpEntryID_ parameter to NULL and the  _ulEventMask_ parameter to  _fnevNewMail_.</span></span> 
  
<span data-ttu-id="c825e-119">请勿修改或释放描述新邮件通知的[通知](notification.md)结构的内存。</span><span class="sxs-lookup"><span data-stu-id="c825e-119">Do not modify or free the memory for the [NOTIFICATION](notification.md) structure that describes the new mail notification.</span></span> <span data-ttu-id="c825e-120">通过调用实用工具函数[ScCopyNotifications](sccopynotifications.md)来复制**通知**结构, 以使用其成员中的信息。</span><span class="sxs-lookup"><span data-stu-id="c825e-120">Copy the **NOTIFICATION** structure by calling the utility function [ScCopyNotifications](sccopynotifications.md) to make use of the information in its members.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c825e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c825e-121">See also</span></span>



[<span data-ttu-id="c825e-122">IMAPISupport::Subscribe</span><span class="sxs-lookup"><span data-stu-id="c825e-122">IMAPISupport::Subscribe</span></span>](imapisupport-subscribe.md)
  
[<span data-ttu-id="c825e-123">IMAPISupport::Unsubscribe</span><span class="sxs-lookup"><span data-stu-id="c825e-123">IMAPISupport::Unsubscribe</span></span>](imapisupport-unsubscribe.md)
  
[<span data-ttu-id="c825e-124">NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="c825e-124">NOTIFICATION</span></span>](notification.md)
  
[<span data-ttu-id="c825e-125">ScCopyNotifications</span><span class="sxs-lookup"><span data-stu-id="c825e-125">ScCopyNotifications</span></span>](sccopynotifications.md)
  
[<span data-ttu-id="c825e-126">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c825e-126">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

