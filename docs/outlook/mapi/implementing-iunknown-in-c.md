---
title: 使用 C 实现 IUnknown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 807b6dc4-cdb7-40a4-87d7-ebc1ad5fab76
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3c634defcad76755fc6604a23d2091bb21e15111
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346772"
---
# <a name="implementing-iunknown-in-c"></a>使用 C 实现 IUnknown

**适用于**：Outlook 2013 | Outlook 2016 
  
c 中[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法的实现与 c + + 实现非常相似。 对于实现, 有两个基本步骤: 
  
1. 验证参数。
    
2. 根据对象支持的接口列表检查所请求接口的标识符, 并返回 E_NO_INTERFACE 值或有效的接口指针。 如果返回接口指针, 则实现还应调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来递增引用计数。 
    
c 和 c + + 中的**QueryInterface**实现之间的主要区别是 c 版本中的额外第一个参数。 由于将对象指针添加到参数列表中, 因此**QueryInterface**的 C 实现必须具有比 c + + 实现更多的参数验证。 用于检查接口标识符、递增引用计数和返回对象指针的逻辑在这两种语言中应相同。 
  
下面的代码示例演示如何在 C 中为 status 对象实现**QueryInterface** 。 
  
```cpp
STDMETHODIMP STATUS_QueryInterface(LPMYSTATUSOBJ lpMyObj, REFIID riid,
                                   LPVOID FAR * lppvObj)
{
    HRESULT hr = hrSuccess;
    // Validate the object pointer.
    if (!lpMyObj || lpMyObj->lpVtbl != &vtblSTATUS )
    {
        hr = ResultFromScode(E_INVALIDARG);
        return hr;
    }
    // Validate other parameters.
    if (!lppvObj)
    {
        hr = ResultFromScode(E_INVALIDARG);
        return hr;
    }
    // Set the output pointer to NULL.
    *lppvObj = NULL;
    // Check the interface identifier.
    if (memcmp(riid, &IID_IUnknown, sizeof(IID)) &&
        memcmp(riid, &IID_IMAPIProp, sizeof(IID)) &&
        memcmp(riid, &IID_IMAPIStatus, sizeof(IID)))
    {
        hr = ResultFromScode(E_NOINTERFACE);
        return hr;
    }
    // The interface is supported. Increment the reference count and return.
    lpMyObj->lpVtbl->AddRef(lpMyObj);
    *lppvObj = lpMyObj;
    return hr;
}

```

尽管 c 中的**AddRef**方法的实现与 c + + 实现类似, 但[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法的 C 实现可能比 c + + 版本更精密。 这是因为释放对象时所涉及的大部分功能可以合并到 c + + 构造函数和析构函数中, 而 C 没有这样的机制。 所有这些功能都必须包含在**Release**方法中。 此外, 由于其他参数及其显式 vtable, 因此需要进行更多的验证。 
  
以下**AddRef**方法调用说明了 status 对象的典型 C 实现。 
  
```cpp
STDMETHODIMP_(ULONG) STATUS_AddRef(LPMYSTATUSOBJ lpMyObj)
{
    LONG cRef;
    // Check to see whether it has a lpVtbl object member.
    if (!lpMyObj || lpMyObj->lpVtbl != &vtblSTATUS)
    {
        return 1;
    }
    // Check the method.
    if (STATUS_AddRef != lpMyObj->lpVtbl->AddRef)
    {
        return 1;
    }
    InterlockedIncrement(lpMyObj->cRef);
    cRef = ++lpMyObj->cRef;
    InterlockedDecrement (lpMyObj->cRef);
    return cRef;
}

```

下面的代码示例演示 C 状态对象的典型**版本**实现。 如果引用计数为0减后, 则 C 状态对象实现应执行以下任务: 
  
- 释放指向对象的任何保留指针。 
    
- 将 vtable 设置为 NULL, 以便在对象的用户调用了**Release**但仍继续尝试使用该对象的情况下便于调试。 
    
- 调用**MAPIFreeBuffer**以释放该对象。 
    
```cpp
STDMETHODIMP_(ULONG) STATUS_Release(LPMYSTATUSOBJ lpMyObj)
{
    LONG cRef;
    // Check the size of the vtable.
    if (!lpMyObj)
    {
        return 1;
    }
    // Check whether the vtable is correct.
    if (lpMyObj->lpVtbl != &vtblSTATUS)
    {
        return 1;
    }
    InterlockedIncrement(lpMyObj->cRef);
    cRef = --lpMyObj->cRef;
    InterlockedIncrement (lpMyObj->cRef);
    if (cRef == 0)
    {
        lpMyObj->lpVtbl->Release(lpMyObj);
        DeleteCriticalSection(&lpMyObj->cs);
        // Release the IMAPIProp pointer.
        lpMyObj->lpProp->Release(lpMyObj->lpProp);
        lpMyObj->lpVtbl = NULL;
        lpMyObj->lpFreeBuff(lpMyObj);
        return 0;
    }
    return cRef;
}

```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)
- [实现 IUnknown 接口](implementing-the-iunknown-interface.md)

