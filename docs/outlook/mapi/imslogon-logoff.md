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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 66ba27d1d333be3217f2a22ca5d53449372c1f31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348872"
---
# <a name="imslogonlogoff"></a><span data-ttu-id="38077-103">IMSLogon::Logoff</span><span class="sxs-lookup"><span data-stu-id="38077-103">IMSLogon::Logoff</span></span>

  
  
<span data-ttu-id="38077-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38077-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38077-105">注销邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="38077-105">Logs off a message store provider.</span></span> 
  
```cpp
HRESULT Logoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="38077-106">参数</span><span class="sxs-lookup"><span data-stu-id="38077-106">Parameters</span></span>

 <span data-ttu-id="38077-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="38077-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="38077-108">[in]保留;必须是指向零的指针。</span><span class="sxs-lookup"><span data-stu-id="38077-108">[in] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="38077-109">返回值</span><span class="sxs-lookup"><span data-stu-id="38077-109">Return value</span></span>

<span data-ttu-id="38077-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="38077-110">S_OK</span></span> 
  
> <span data-ttu-id="38077-111">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="38077-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="38077-112">备注</span><span class="sxs-lookup"><span data-stu-id="38077-112">Remarks</span></span>

<span data-ttu-id="38077-113">邮件存储提供程序实现 **IMSLogon：：Logoff** 方法以强制关闭邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="38077-113">Message store providers implement the **IMSLogon::Logoff** method to forcibly shut down a message store provider.</span></span> <span data-ttu-id="38077-114">**在下列情况下调用 IMSLogon：：Logoff：**</span><span class="sxs-lookup"><span data-stu-id="38077-114">**IMSLogon::Logoff** is called in the following situations:</span></span> 
  
- <span data-ttu-id="38077-115">调用 [IMAPISession：：Logoff 方法后，MAPI](imapisession-logoff.md) 正在注销客户端。</span><span class="sxs-lookup"><span data-stu-id="38077-115">While MAPI is logging off a client after a call to the [IMAPISession::Logoff](imapisession-logoff.md) method.</span></span> 
    
- <span data-ttu-id="38077-116">在 MAPI 注销邮件存储提供程序时。</span><span class="sxs-lookup"><span data-stu-id="38077-116">While MAPI is logging off a message store provider.</span></span> <span data-ttu-id="38077-117">在这种情况下 **，IMSLogon：：Logoff** 是 MAPI 处理消息存储提供程序在处理消息存储对象上的 [IMsgStore：：StoreLogoff](imsgstore-storelogoff.md)或 **IUnknown：：Release** 方法调用时所创建的支持对象的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法的一部分调用的。</span><span class="sxs-lookup"><span data-stu-id="38077-117">In this case, **IMSLogon::Logoff** is called as part of MAPI processing the [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method of the support object that the message store provider creates while it is processing an [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) or **IUnknown::Release** method call on a message store object.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="38077-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38077-118">See also</span></span>



[<span data-ttu-id="38077-119">IMAPISession::Logoff</span><span class="sxs-lookup"><span data-stu-id="38077-119">IMAPISession::Logoff</span></span>](imapisession-logoff.md)
  
[<span data-ttu-id="38077-120">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="38077-120">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
  
[<span data-ttu-id="38077-121">IMsgStore::StoreLogoff</span><span class="sxs-lookup"><span data-stu-id="38077-121">IMsgStore::StoreLogoff</span></span>](imsgstore-storelogoff.md)
  
[<span data-ttu-id="38077-122">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="38077-122">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="38077-123">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="38077-123">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="38077-124">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="38077-124">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

