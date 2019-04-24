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
  
本主题显示了一个 c + + 中的代码示例, 该示例在邮件存储区中查询**[IProxyStoreObject](iproxystoreobject.md)** 接口, 并使用返回的指针和**[IProxyStoreObject:: UnwrapNoRef](iproxystoreobject-unwrapnoref.md)** 函数获取指向 IMAP 存储对象的指针, 该对象已换. 使用此解出的存储允许访问当前状态的邮件, 而无需调用整个邮件的下载。 
  
由于**UnwrapNoRef**不会将此新指针的引用计数增加到已解包的 store 对象, 因此在成功调用**UnwrapNoRef**后, 必须调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)来维护引用计数。 
  
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


