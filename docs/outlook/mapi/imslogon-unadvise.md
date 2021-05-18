---
title: IMSLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Unadvise
api_type:
- COM
ms.assetid: 440d61c4-b69a-4010-a22b-0c9c5c376fbc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9172d4956e78ac31cd15d69e70d05c127a474ca5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317274"
---
# <a name="imslogonunadvise"></a><span data-ttu-id="f0d68-103">IMSLogon::Unadvise</span><span class="sxs-lookup"><span data-stu-id="f0d68-103">IMSLogon::Unadvise</span></span>

  
  
<span data-ttu-id="f0d68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0d68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0d68-105">通过调用 [IMSLogon：：Advise](imslogon-advise.md) 方法，删除对象对之前建立的邮件存储更改通知的注册。</span><span class="sxs-lookup"><span data-stu-id="f0d68-105">Removes an object's registration for notification of message store changes previously established by using a call to the [IMSLogon::Advise](imslogon-advise.md) method.</span></span> 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="f0d68-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0d68-106">Parameters</span></span>

 <span data-ttu-id="f0d68-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="f0d68-107">_ulConnection_</span></span>
  
> <span data-ttu-id="f0d68-108">[in]通过调用 **IMSLogon：：Advise** 返回的注册连接数。</span><span class="sxs-lookup"><span data-stu-id="f0d68-108">[in] The number of the registration connection returned by a call to **IMSLogon::Advise**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f0d68-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f0d68-109">Return value</span></span>

<span data-ttu-id="f0d68-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0d68-110">S_OK</span></span> 
  
> <span data-ttu-id="f0d68-111">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="f0d68-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f0d68-112">备注</span><span class="sxs-lookup"><span data-stu-id="f0d68-112">Remarks</span></span>

<span data-ttu-id="f0d68-113">消息存储提供程序实现 **IMSLogon：：Unadvise** 方法，以释放指向在上一次调用 **IMSLogon：：Advise** 时传入 _lpAdviseSink_ 参数中的通知接收对象的指针，从而取消通知注册。</span><span class="sxs-lookup"><span data-stu-id="f0d68-113">Message store providers implement the **IMSLogon::Unadvise** method to release the pointer to the advise sink object passed in the  _lpAdviseSink_ parameter in the previous call to **IMSLogon::Advise**, thereby canceling a notification registration.</span></span> <span data-ttu-id="f0d68-114">作为放弃指向建议接收对象的指针的一部分，将调用对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="f0d68-114">As part of discarding the pointer to the advise sink object, the object's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method is called.</span></span> <span data-ttu-id="f0d68-115">通常， **在** 非企业调用 **期间调用** Release。</span><span class="sxs-lookup"><span data-stu-id="f0d68-115">Generally, **Release** is called during the **Unadvise** call.</span></span> <span data-ttu-id="f0d68-116">但是，如果另一个线程正在调用通知接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法， **则 Release** 调用将延迟到 **OnNotify** 方法返回。</span><span class="sxs-lookup"><span data-stu-id="f0d68-116">However, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method for the advise sink object, the **Release** call is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f0d68-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0d68-117">See also</span></span>



[<span data-ttu-id="f0d68-118">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="f0d68-118">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="f0d68-119">IMSLogon::Advise</span><span class="sxs-lookup"><span data-stu-id="f0d68-119">IMSLogon::Advise</span></span>](imslogon-advise.md)
  
[<span data-ttu-id="f0d68-120">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f0d68-120">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

