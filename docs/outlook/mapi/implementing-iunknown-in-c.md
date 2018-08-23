---
title: 使用 C 实现 IUnknown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 807b6dc4-cdb7-40a4-87d7-ebc1ad5fab76
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bdc81d78927e530037c65ca7fd61d722cd96bab7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581438"
---
# <a name="implementing-iunknown-in-c"></a>使用 C 实现 IUnknown

**适用于**： Outlook 2013 |Outlook 2016 
  
C 中的[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法的实现都是非常类似于 c + + 实现的。 有的实现的两个基本步骤： 
  
1. 正在验证参数。
    
2. 检查的接口对象支持的列表对请求的接口的标识符和返回 E_NO_INTERFACE 值或有效的接口指针。 如果返回的接口指针，实现还应调用[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法，以增加引用计数。 
    
**QueryInterface** C 中实现和 c + + 的主要区别是 C 版本中的其他第一个参数。 因为对象指针添加到参数列表中， **QueryInterface** C 实现必须具有比 c + + 实施的多个参数验证。 检查接口标识符、 增加引用计数，以及返回一个对象指针的逻辑应在两种语言相同。 
  
下面的代码示例演示如何实现状态对象中 C **QueryInterface** 。 
  
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

类似于 c + + 实现 c **AddRef**方法的实现，而[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法的 C 实现可以获得更精细比 c + + 版本。 这是因为的许多功能所涉及释放对象可以并入 c + + 构造函数和对析构函数，并且 C 已没有这种机制。 所有这些功能必须包含**Release**方法。 此外，由于其他参数以及其显式 vtable 详细验证是所需的。 
  
下面的**AddRef**方法调用演示了一个典型的 C 实现状态对象。 
  
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

下面的代码示例演示 C 状态对象的**版本**的典型的实现。 如果引用计数递减后为 0，C 状态对象实现应执行以下任务： 
  
- 释放到对象中任何暂的指针。 
    
- 设置为 NULL，从而推动在其中调用**版本**的对象的用户尚未继续尝试使用对象的情况下调试 vtable。 
    
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
- [实施 IUnknown 接口](implementing-the-iunknown-interface.md)

