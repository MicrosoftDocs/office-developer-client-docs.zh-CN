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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2988f1fc149bbfc2d724b62b12bd12ae4f4664a6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436151"
---
# <a name="iaddrbookunadvise"></a><span data-ttu-id="77e17-103">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="77e17-103">IAddrBook::Unadvise</span></span>

  
  
<span data-ttu-id="77e17-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77e17-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77e17-105">取消之前为通讯簿条目建立的通知注册。</span><span class="sxs-lookup"><span data-stu-id="77e17-105">Cancels a notification registration previously established for an address book entry.</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="77e17-106">参数</span><span class="sxs-lookup"><span data-stu-id="77e17-106">Parameters</span></span>

 <span data-ttu-id="77e17-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="77e17-107">_ulConnection_</span></span>
  
> <span data-ttu-id="77e17-108">实时一个代表要取消的注册的连接号。</span><span class="sxs-lookup"><span data-stu-id="77e17-108">[in] A connection number that represents the registration to be canceled.</span></span> <span data-ttu-id="77e17-109">_ulConnection_参数应包含以前调用[IAddrBook:: Advise](iaddrbook-advise.md)方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="77e17-109">The  _ulConnection_ parameter should contain a value returned by a prior call to the [IAddrBook::Advise](iaddrbook-advise.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="77e17-110">返回值</span><span class="sxs-lookup"><span data-stu-id="77e17-110">Return value</span></span>

<span data-ttu-id="77e17-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="77e17-111">S_OK</span></span> 
  
> <span data-ttu-id="77e17-112">已成功取消注册。</span><span class="sxs-lookup"><span data-stu-id="77e17-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="77e17-113">说明</span><span class="sxs-lookup"><span data-stu-id="77e17-113">Remarks</span></span>

<span data-ttu-id="77e17-114">客户端调用**Unadvise**方法以停止接收有关特定通讯簿条目更改的通知。</span><span class="sxs-lookup"><span data-stu-id="77e17-114">Clients call the **Unadvise** method to stop receiving notifications about changes to a particular address book entry.</span></span> <span data-ttu-id="77e17-115">当取消通知注册时, 通讯簿提供程序释放其指向呼叫者的通知接收器的指针。</span><span class="sxs-lookup"><span data-stu-id="77e17-115">When a notification registration is canceled, the address book provider releases its pointer to the caller's advise sink.</span></span> <span data-ttu-id="77e17-116">但是, 如果另一个线程正在调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则可以在**Unadvise**调用过程中或在稍后的某个时间点进行释放。</span><span class="sxs-lookup"><span data-stu-id="77e17-116">However, the release can occur during the **Unadvise** call or at some later point, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="77e17-117">当通知正在进行时, 释放将延迟到**OnNotify**方法返回。</span><span class="sxs-lookup"><span data-stu-id="77e17-117">When a notification is in progress, the release is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77e17-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77e17-118">See also</span></span>



[<span data-ttu-id="77e17-119">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="77e17-119">IAddrBook::Advise</span></span>](iaddrbook-advise.md)
  
[<span data-ttu-id="77e17-120">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="77e17-120">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="77e17-121">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="77e17-121">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

