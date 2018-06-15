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
ms.openlocfilehash: bf72e6f182f67861f909e21f0ec1871d76617974
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775268"
---
# <a name="iaddrbookunadvise"></a><span data-ttu-id="9cc5c-103">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="9cc5c-103">IAddrBook::Unadvise</span></span>

  
  
<span data-ttu-id="9cc5c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9cc5c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9cc5c-105">取消以前建立的通讯簿条目的通知注册。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-105">Cancels a notification registration previously established for an address book entry.</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="9cc5c-106">参数</span><span class="sxs-lookup"><span data-stu-id="9cc5c-106">Parameters</span></span>

 <span data-ttu-id="9cc5c-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="9cc5c-107">_ulConnection_</span></span>
  
> <span data-ttu-id="9cc5c-108">[in]代表要取消注册连接数。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-108">[in] A connection number that represents the registration to be canceled.</span></span> <span data-ttu-id="9cc5c-109">_UlConnection_参数应包含以前调用[IAddrBook::Advise](iaddrbook-advise.md)方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-109">The  _ulConnection_ parameter should contain a value returned by a prior call to the [IAddrBook::Advise](iaddrbook-advise.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="9cc5c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9cc5c-110">Return value</span></span>

<span data-ttu-id="9cc5c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cc5c-111">S_OK</span></span> 
  
> <span data-ttu-id="9cc5c-112">成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9cc5c-113">备注</span><span class="sxs-lookup"><span data-stu-id="9cc5c-113">Remarks</span></span>

<span data-ttu-id="9cc5c-114">客户端调用**Unadvise**方法停止接收有关到特定的通讯簿条目的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-114">Clients call the **Unadvise** method to stop receiving notifications about changes to a particular address book entry.</span></span> <span data-ttu-id="9cc5c-115">取消通知注册时，它的指针到呼叫者的建议接收器地址簿提供程序版本。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-115">When a notification registration is canceled, the address book provider releases its pointer to the caller's advise sink.</span></span> <span data-ttu-id="9cc5c-116">但是，发布**Unadvise**呼叫过程中或在某些更高版本的时候，如果出现另一个线程正在调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-116">However, the release can occur during the **Unadvise** call or at some later point, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="9cc5c-117">通知时，直至**OnNotify**方法返回延迟版本。</span><span class="sxs-lookup"><span data-stu-id="9cc5c-117">When a notification is in progress, the release is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9cc5c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cc5c-118">See also</span></span>



[<span data-ttu-id="9cc5c-119">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="9cc5c-119">IAddrBook::Advise</span></span>](iaddrbook-advise.md)
  
[<span data-ttu-id="9cc5c-120">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="9cc5c-120">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="9cc5c-121">IAddrBook: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9cc5c-121">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

