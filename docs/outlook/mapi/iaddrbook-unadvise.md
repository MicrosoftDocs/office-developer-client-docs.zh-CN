---
title: IAddrBookUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Unadvise
api_type:
- COM
ms.assetid: e0db9e86-9528-43de-b8ba-a5af8b7bda4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e06f78317a1e98d47a37cb7059042b254567fe8b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573682"
---
# <a name="iaddrbookunadvise"></a><span data-ttu-id="21aab-103">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="21aab-103">IAddrBook::Unadvise</span></span>

  
  
<span data-ttu-id="21aab-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21aab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21aab-105">取消以前建立的通讯簿条目的通知注册。</span><span class="sxs-lookup"><span data-stu-id="21aab-105">Cancels a notification registration previously established for an address book entry.</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="21aab-106">参数</span><span class="sxs-lookup"><span data-stu-id="21aab-106">Parameters</span></span>

 <span data-ttu-id="21aab-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="21aab-107">_ulConnection_</span></span>
  
> <span data-ttu-id="21aab-108">[in]代表要取消注册连接数。</span><span class="sxs-lookup"><span data-stu-id="21aab-108">[in] A connection number that represents the registration to be canceled.</span></span> <span data-ttu-id="21aab-109">_UlConnection_参数应包含以前调用[IAddrBook::Advise](iaddrbook-advise.md)方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="21aab-109">The  _ulConnection_ parameter should contain a value returned by a prior call to the [IAddrBook::Advise](iaddrbook-advise.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="21aab-110">返回值</span><span class="sxs-lookup"><span data-stu-id="21aab-110">Return value</span></span>

<span data-ttu-id="21aab-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="21aab-111">S_OK</span></span> 
  
> <span data-ttu-id="21aab-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="21aab-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="21aab-113">注解</span><span class="sxs-lookup"><span data-stu-id="21aab-113">Remarks</span></span>

<span data-ttu-id="21aab-114">客户端调用**Unadvise**方法停止接收有关到特定的通讯簿条目的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="21aab-114">Clients call the **Unadvise** method to stop receiving notifications about changes to a particular address book entry.</span></span> <span data-ttu-id="21aab-115">取消通知注册时，它的指针到呼叫者的建议接收器地址簿提供程序版本。</span><span class="sxs-lookup"><span data-stu-id="21aab-115">When a notification registration is canceled, the address book provider releases its pointer to the caller's advise sink.</span></span> <span data-ttu-id="21aab-116">但是，发布**Unadvise**呼叫过程中或在某些更高版本的时候，如果出现另一个线程正在调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="21aab-116">However, the release can occur during the **Unadvise** call or at some later point, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="21aab-117">通知时，直至**OnNotify**方法返回延迟版本。</span><span class="sxs-lookup"><span data-stu-id="21aab-117">When a notification is in progress, the release is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="21aab-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21aab-118">See also</span></span>



[<span data-ttu-id="21aab-119">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="21aab-119">IAddrBook::Advise</span></span>](iaddrbook-advise.md)
  
[<span data-ttu-id="21aab-120">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="21aab-120">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="21aab-121">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="21aab-121">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

