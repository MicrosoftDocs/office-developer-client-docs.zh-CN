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
# <a name="iaddrbookunadvise"></a><span data-ttu-id="e4e72-103">IAddrBook::Unadvise</span><span class="sxs-lookup"><span data-stu-id="e4e72-103">IAddrBook::Unadvise</span></span>

  
  
<span data-ttu-id="e4e72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4e72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4e72-105">取消以前为通讯簿条目建立的通知注册。</span><span class="sxs-lookup"><span data-stu-id="e4e72-105">Cancels a notification registration previously established for an address book entry.</span></span>
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a><span data-ttu-id="e4e72-106">参数</span><span class="sxs-lookup"><span data-stu-id="e4e72-106">Parameters</span></span>

 <span data-ttu-id="e4e72-107">_ulConnection_</span><span class="sxs-lookup"><span data-stu-id="e4e72-107">_ulConnection_</span></span>
  
> <span data-ttu-id="e4e72-108">[in]表示要取消的注册的连接号码。</span><span class="sxs-lookup"><span data-stu-id="e4e72-108">[in] A connection number that represents the registration to be canceled.</span></span> <span data-ttu-id="e4e72-109">_ulConnection_ 参数应包含之前调用 [IAddrBook：：Advise](iaddrbook-advise.md)方法时返回的值。</span><span class="sxs-lookup"><span data-stu-id="e4e72-109">The  _ulConnection_ parameter should contain a value returned by a prior call to the [IAddrBook::Advise](iaddrbook-advise.md) method.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e4e72-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e4e72-110">Return value</span></span>

<span data-ttu-id="e4e72-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4e72-111">S_OK</span></span> 
  
> <span data-ttu-id="e4e72-112">注册已成功取消。</span><span class="sxs-lookup"><span data-stu-id="e4e72-112">The registration was successfully canceled.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e4e72-113">备注</span><span class="sxs-lookup"><span data-stu-id="e4e72-113">Remarks</span></span>

<span data-ttu-id="e4e72-114">客户端调用 **Unadvise** 方法来停止接收有关对特定通讯簿条目的更改的通知。</span><span class="sxs-lookup"><span data-stu-id="e4e72-114">Clients call the **Unadvise** method to stop receiving notifications about changes to a particular address book entry.</span></span> <span data-ttu-id="e4e72-115">当通知注册被取消时，通讯簿提供程序会释放指向呼叫者的建议接收器的指针。</span><span class="sxs-lookup"><span data-stu-id="e4e72-115">When a notification registration is canceled, the address book provider releases its pointer to the caller's advise sink.</span></span> <span data-ttu-id="e4e72-116">但是，如果其他线程正在调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法，则版本可能会发生在 **Unadvise** 调用期间或稍后的一些时间点。</span><span class="sxs-lookup"><span data-stu-id="e4e72-116">However, the release can occur during the **Unadvise** call or at some later point, if another thread is in the process of calling the [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) method.</span></span> <span data-ttu-id="e4e72-117">当通知正在进行时，发布将延迟到 **OnNotify 方法** 返回。</span><span class="sxs-lookup"><span data-stu-id="e4e72-117">When a notification is in progress, the release is delayed until the **OnNotify** method returns.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e4e72-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4e72-118">See also</span></span>



[<span data-ttu-id="e4e72-119">IAddrBook::Advise</span><span class="sxs-lookup"><span data-stu-id="e4e72-119">IAddrBook::Advise</span></span>](iaddrbook-advise.md)
  
[<span data-ttu-id="e4e72-120">IMAPIAdviseSink::OnNotify</span><span class="sxs-lookup"><span data-stu-id="e4e72-120">IMAPIAdviseSink::OnNotify</span></span>](imapiadvisesink-onnotify.md)
  
[<span data-ttu-id="e4e72-121">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e4e72-121">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

