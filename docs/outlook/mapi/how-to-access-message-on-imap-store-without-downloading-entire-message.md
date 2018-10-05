---
title: 无须下载整个邮件访问 IMAP 存储区上的消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2a93ab3e-798f-5741-d5e0-bba8c6b437c7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 194131148cc36dfff791b4cfae01862e8bbef5cb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398442"
---
# <a name="access-a-message-on-an-imap-store-without-downloading-the-entire-message"></a><span data-ttu-id="70f76-103">无须下载整个邮件访问 IMAP 存储区上的消息</span><span class="sxs-lookup"><span data-stu-id="70f76-103">Access a message on an IMAP store without downloading the entire message</span></span>

<span data-ttu-id="70f76-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70f76-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70f76-105">本主题演示在 c + + 的查询的消息存储**[IProxyStoreObject](iproxystoreobject.md)** 的接口，并使用返回的指针和**[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md)** 函数来获取已 IMAP 存储对象的指针的代码示例解包。</span><span class="sxs-lookup"><span data-stu-id="70f76-105">This topic shows a code sample in C++ that queries a message store for the **[IProxyStoreObject](iproxystoreobject.md)** interface, and uses the returned pointer and the **[IProxyStoreObject::UnwrapNoRef](iproxystoreobject-unwrapnoref.md)** function to obtain a pointer to an IMAP store object that has been unwrapped.</span></span> <span data-ttu-id="70f76-106">使用此解包的存储而无需调用的整个邮件下载允许访问其当前状态中的邮件。</span><span class="sxs-lookup"><span data-stu-id="70f76-106">Using this unwrapped store allows access to a message in its current state without invoking a download of the entire message.</span></span> 
  
<span data-ttu-id="70f76-107">由于**UnwrapNoRef**不会增加到解包的存储对象，此新指针的引用计数成功调用**UnwrapNoRef**后，必须调用[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)维护引用计数。</span><span class="sxs-lookup"><span data-stu-id="70f76-107">Because **UnwrapNoRef** does not increment the reference count for this new pointer to the unwrapped store object, after successfully calling **UnwrapNoRef**, you must call [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) to maintain the reference count.</span></span> 
  
```cpp
HRESULT HrUnWrapMDB(LPMDB lpMDBIn, LPMDB* lppMDBOut) 
{ 
    HRESULT hRes = S_OK; 
    IProxyStoreObject* lpProxyObj = NULL; 
    LPMDB lpUnwrappedMDB = NULL; 
    hRes = lpMDBIn->QueryInterface(IID_IProxyStoreObject,(void**)&lpProxyObj); 
    if (SUCCEEDED(hRes) && lpProxyObj) 
    { 
        hRes = lpProxyObj->UnwrapNoRef((LPVOID*)&lpUnwrappedMDB); 
        if (SUCCEEDED(hRes) && lpUnwrappedMDB) 
        { 
            // UnwrapNoRef doesn't addref, so do it here 
            lpUnwrappedMDB->AddRef(); 
            (*lppMDBOut) = lpUnwrappedMDB; 
        } 
    } 
    if (lpProxyObj) lpProxyObj->Release(); 
    return hRes; 
}
```


