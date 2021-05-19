---
title: IMAPISessionUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Unadvise
api_type:
- COM
ms.assetid: 5e608cb0-808d-4418-8521-71dcbce8cdff
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98a5faca00f5877eb10110406875b46a69244d94
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335698"
---
# <a name="imapisessionunadvise"></a><span data-ttu-id="dc426-103">IMAPISession::Unadvise</span><span class="sxs-lookup"><span data-stu-id="dc426-103">IMAPISession::Unadvise</span></span>

  
  
<span data-ttu-id="dc426-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc426-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc426-105">取消发送以前通过调用 [IMAPISession：：Advise](imapisession-advise.md) 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="dc426-105">Cancels the sending of notifications previously set up with a call to the [IMAPISession::Advise](imapisession-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="dc426-106">参数</span><span class="sxs-lookup"><span data-stu-id="dc426-106">Parameters</span></span>

 <span data-ttu-id="dc426-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="dc426-107">_ulConnection_</span></span>
  
> <span data-ttu-id="dc426-108">[in]与活动通知注册关联的连接号。</span><span class="sxs-lookup"><span data-stu-id="dc426-108">[in] A connection number associated with an active notification registration.</span></span> <span data-ttu-id="dc426-109">_ulConnection 的值必须已_ 由上一次对 **IMAPISession：：Advise 的调用返回**。</span><span class="sxs-lookup"><span data-stu-id="dc426-109">The value of  _ulConnection_ must have been returned by a previous call to **IMAPISession::Advise**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dc426-110">返回值</span><span class="sxs-lookup"><span data-stu-id="dc426-110">Return value</span></span>

<span data-ttu-id="dc426-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc426-111">S_OK</span></span> 
  
> <span data-ttu-id="dc426-112">注册已成功取消。</span><span class="sxs-lookup"><span data-stu-id="dc426-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dc426-113">备注</span><span class="sxs-lookup"><span data-stu-id="dc426-113">Remarks</span></span>

<span data-ttu-id="dc426-114">**IMAPISession：：Unadvise** 方法取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="dc426-114">The **IMAPISession::Unadvise** method cancels a registration for notification.</span></span> <span data-ttu-id="dc426-115">**非advise** 将释放指向调用方的建议接收器的指针，它会在用于注册的 **Advise** 调用中收到通知接收器。</span><span class="sxs-lookup"><span data-stu-id="dc426-115">**Unadvise** releases its pointer to the caller's advise sink, which it received in the **Advise** call used for registration.</span></span> 
  
<span data-ttu-id="dc426-116">通常 **，Unadvise** 在 **Unadvise** 调用期间调用通知接收器 [的 IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="dc426-116">Generally, **Unadvise** calls the advise sink's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method during the **Unadvise** call.</span></span> <span data-ttu-id="dc426-117">但是，如果另一个线程正在调用通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法， **则 Release** 调用将延迟到 **OnNotify** 方法返回。</span><span class="sxs-lookup"><span data-stu-id="dc426-117">However, if another thread is in the process of calling the advise sink's [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dc426-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc426-118">See also</span></span>



[<span data-ttu-id="dc426-119">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="dc426-119">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="dc426-120">IMAPISession::Advise</span><span class="sxs-lookup"><span data-stu-id="dc426-120">IMAPISession::Advise</span></span>](imapisession-advise.md)
  
[<span data-ttu-id="dc426-121">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dc426-121">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)

