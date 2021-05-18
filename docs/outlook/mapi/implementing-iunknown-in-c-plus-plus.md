---
title: 使用 C++ 实现 IUnknown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 68519f6c-fba8-47f5-9401-316e276f770e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 08f3f3f937320d8a986b2002c761a37f0f749227
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330175"
---
# <a name="implementing-iunknown-in-c"></a>使用 C++ 实现 IUnknown

**适用于**：Outlook 2013 | Outlook 2016 
  
在 C++ 中实现[IUnknown 接口的 IUnknown：：QueryInterface、IUnknown：：AddRef](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)和[](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)[IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法相当简单。 [](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 对传入的参数进行一些标准验证后 **，QueryInterface** 的实现将针对受支持的接口列表检查请求的接口的标识符。 如果请求的标识符在受支持的标识符中，将调用 **AddRef** 并 **返回此** 指针。 如果请求的标识符不在受支持的列表中，则输出指针将设置为 NULL，MAPI_E_INTERFACE_NOT_SUPPORTED返回值。 
  
以下代码示例演示如何在 C++ 中为状态对象（作为 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md)接口的子类的对象）实现 **QueryInterface。** **IMAPIStatus** 通过 [IMAPIProp 继承](imapipropiunknown.md)自 **IUnknown** ： IUnknown 。 因此，如果调用方请求这些接口中的任意一个，可以返回此指针，因为接口通过继承相关。 
  
```cpp
HRESULT CMyMAPIObject::QueryInterface (REFIID   riid,
                                       LPVOID * ppvObj)
{
    // Always set out parameter to NULL, validating it first.
    if (!ppvObj)
        return E_INVALIDARG;
    *ppvObj = NULL;
    if (riid == IID_IUnknown || riid == IID_IMAPIProp ||
        riid == IID_IMAPIStatus)
    {
        // Increment the reference count and return the pointer.
        *ppvObj = (LPVOID)this;
        AddRef();
        return NOERROR;
    }
    return E_NOINTERFACE;
}

```

以下代码示例演示如何为对象实现 **AddRef** 和 **Release**  `CMyMAPIObject` 方法。 由于实现 **AddRef 和** **Release** 非常简单，因此许多服务提供商选择内联实现它们。 调用 Win32 函数 **的 InterlockedIncrement** 和 **InterlockedDecrement** 可确保线程安全。 对象的内存由析构函数释放，当 **Release** 方法删除对象时调用该函数。 
  
```cpp
ULONG CMyMAPIObject::AddRef()
{
    InterlockedIncrement(m_cRef);
    return m_cRef;
}
ULONG CMyMAPIObject::Release()
{
    // Decrement the object's internal counter.
    ULONG ulRefCount = InterlockedDecrement(m_cRef);
    if (0 == m_cRef)
    {
        delete this;
    }
    return ulRefCount;
}
 
```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)
- [实现 IUnknown 接口](implementing-the-iunknown-interface.md)

