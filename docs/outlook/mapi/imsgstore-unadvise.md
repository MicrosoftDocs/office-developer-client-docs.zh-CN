---
title: IMsgStoreUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Unadvise
api_type:
- COM
ms.assetid: 1394039b-d509-49a5-8421-b7362d906879
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f85b662b7fe710c66a2e69dd3cd3db22e3283ddb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309721"
---
# <a name="imsgstoreunadvise"></a><span data-ttu-id="d24aa-103">IMsgStore::Unadvise</span><span class="sxs-lookup"><span data-stu-id="d24aa-103">IMsgStore::Unadvise</span></span>

  
  
<span data-ttu-id="d24aa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d24aa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d24aa-105">取消之前通过调用[IMsgStore:: Advise](imsgstore-advise.md)方法设置的通知发送。</span><span class="sxs-lookup"><span data-stu-id="d24aa-105">Cancels the sending of notifications previously set up with a call to the [IMsgStore::Advise](imsgstore-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="d24aa-106">参数</span><span class="sxs-lookup"><span data-stu-id="d24aa-106">Parameters</span></span>

 <span data-ttu-id="d24aa-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="d24aa-107">_ulConnection_</span></span>
  
> <span data-ttu-id="d24aa-108">实时与活动通知注册相关联的连接号码。</span><span class="sxs-lookup"><span data-stu-id="d24aa-108">[in] The connection number associated with an active notification registration.</span></span> <span data-ttu-id="d24aa-109">_ulConnection_的值必须已由以前对**IMsgStore:: Advise**方法的调用返回。</span><span class="sxs-lookup"><span data-stu-id="d24aa-109">The value of  _ulConnection_ must have been returned by a previous call to the **IMsgStore::Advise** method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d24aa-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d24aa-110">Return value</span></span>

<span data-ttu-id="d24aa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d24aa-111">S_OK</span></span> 
  
> <span data-ttu-id="d24aa-112">已成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="d24aa-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d24aa-113">注解</span><span class="sxs-lookup"><span data-stu-id="d24aa-113">Remarks</span></span>

<span data-ttu-id="d24aa-114">**IMsgStore:: Unadvise**方法取消注册通知。</span><span class="sxs-lookup"><span data-stu-id="d24aa-114">The **IMsgStore::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="d24aa-115">**Unadvise**释放其指向呼叫者通知接收器的指针, 该接收器在用于注册的**通知**呼叫中收到。</span><span class="sxs-lookup"><span data-stu-id="d24aa-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="d24aa-116">通常情况下, **Unadvise**在**Unadvise**调用过程中调用通知接收器的[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="d24aa-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="d24aa-117">但是, 如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则**释放**调用将延迟到**OnNotify**方法返回为止。</span><span class="sxs-lookup"><span data-stu-id="d24aa-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d24aa-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d24aa-118">See also</span></span>



[<span data-ttu-id="d24aa-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="d24aa-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="d24aa-120">IMsgStore::Advise</span><span class="sxs-lookup"><span data-stu-id="d24aa-120">IMsgStore::Advise</span></span>](imsgstore-advise.md)
  
[<span data-ttu-id="d24aa-121">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d24aa-121">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

