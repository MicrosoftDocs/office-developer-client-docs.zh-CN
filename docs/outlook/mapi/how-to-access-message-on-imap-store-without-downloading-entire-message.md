---
title: 访问 IMAP 存储上的邮件（不下载整个邮件）
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2a93ab3e-798f-5741-d5e0-bba8c6b437c7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 194131148cc36dfff791b4cfae01862e8bbef5cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299074"
---
# <a name="access-a-message-on-an-imap-store-without-downloading-the-entire-message"></a>访问 IMAP 存储上的邮件（不下载整个邮件）

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题显示了一个 C++ 代码示例，该示例查询 **[IProxyStoreObject](iproxystoreobject.md)** 接口的邮件存储，并使用返回的指针和 **[IProxyStoreObject：：UnwrapNoRef](iproxystoreobject-unwrapnoref.md)** 函数获取指向已取消包装的 IMAP 存储对象的指针。 使用此未包存储允许访问当前状态的邮件，而无需调用整个邮件的下载。 
  
由于 **UnwrapNoRef** 不增加指向未包装存储对象的此新指针的引用计数，因此在成功调用 **UnwrapNoRef** 后，必须调用 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 以保持引用计数。 
  
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


