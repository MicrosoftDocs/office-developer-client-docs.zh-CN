---
title: IMSLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Logoff
api_type:
- COM
ms.assetid: 1b0d1b52-6651-4de3-9381-86772d9d52a1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e72c947a6e0d4052d3335c3e3cfaf5ffb94da669
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593002"
---
# <a name="imslogonlogoff"></a><span data-ttu-id="f4dee-103">IMSLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="f4dee-103">IMSLogon::Logoff</span></span>

  
  
<span data-ttu-id="f4dee-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4dee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4dee-105">注销一条消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="f4dee-105">Logs off a message store provider.</span></span> 
  
```cpp
HRESULT Logoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="f4dee-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4dee-106">Parameters</span></span>

 <span data-ttu-id="f4dee-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="f4dee-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="f4dee-108">[in]保留;必须为零的指针。</span><span class="sxs-lookup"><span data-stu-id="f4dee-108">[in] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f4dee-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f4dee-109">Return value</span></span>

<span data-ttu-id="f4dee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4dee-110">S_OK</span></span> 
  
> <span data-ttu-id="f4dee-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f4dee-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f4dee-112">注解</span><span class="sxs-lookup"><span data-stu-id="f4dee-112">Remarks</span></span>

<span data-ttu-id="f4dee-113">消息存储提供程序实现**IMSLogon::Logoff**方法以强制关闭消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="f4dee-113">Message store providers implement the **IMSLogon::Logoff** method to forcibly shut down a message store provider.</span></span> <span data-ttu-id="f4dee-114">在下列情况下调用**IMSLogon::Logoff** :</span><span class="sxs-lookup"><span data-stu-id="f4dee-114">**IMSLogon::Logoff** is called in the following situations:</span></span> 
  
- <span data-ttu-id="f4dee-115">同时给[IMAPISession::Logoff](imapisession-logoff.md)方法调用后 MAPI 正在注销客户端。</span><span class="sxs-lookup"><span data-stu-id="f4dee-115">While MAPI is logging off a client after a call to the [IMAPISession::Logoff](imapisession-logoff.md) method.</span></span> 
    
- <span data-ttu-id="f4dee-116">MAPI 注销消息存储提供程序时。</span><span class="sxs-lookup"><span data-stu-id="f4dee-116">While MAPI is logging off a message store provider.</span></span> <span data-ttu-id="f4dee-117">在这种情况下， **IMSLogon::Logoff**称为 MAPI 处理的消息存储提供程序创建处理[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)或**IUnknown 时支持对象的[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法的一部分::发行版**消息存储对象上的方法调用。</span><span class="sxs-lookup"><span data-stu-id="f4dee-117">In this case, **IMSLogon::Logoff** is called as part of MAPI processing the [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method of the support object that the message store provider creates while it is processing an [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) or **IUnknown::Release** method call on a message store object.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f4dee-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4dee-118">See also</span></span>



[<span data-ttu-id="f4dee-119">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="f4dee-119">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
  
[<span data-ttu-id="f4dee-120">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f4dee-120">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
  
[<span data-ttu-id="f4dee-121">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="f4dee-121">IMsgStore::StoreLogoff</span></span>](imsgstore-storelogoff.md)
  
[<span data-ttu-id="f4dee-122">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="f4dee-122">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="f4dee-123">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f4dee-123">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="f4dee-124">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f4dee-124">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

