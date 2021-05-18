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
# <a name="implementing-iunknown-in-c"></a><span data-ttu-id="8693b-103">使用 C++ 实现 IUnknown</span><span class="sxs-lookup"><span data-stu-id="8693b-103">Implementing IUnknown in C++</span></span>

<span data-ttu-id="8693b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8693b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8693b-105">在 C++ 中实现[IUnknown 接口的 IUnknown：：QueryInterface、IUnknown：：AddRef](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)和[](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)[IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法相当简单。 [](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8693b-105">Implementing the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx), [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx), and [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) methods of the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface in C++ is fairly simple.</span></span> <span data-ttu-id="8693b-106">对传入的参数进行一些标准验证后 **，QueryInterface** 的实现将针对受支持的接口列表检查请求的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="8693b-106">After some standard validation of the parameters that are passed in, an implementation of **QueryInterface** checks the identifier of the requested interface against the list of supported interfaces.</span></span> <span data-ttu-id="8693b-107">如果请求的标识符在受支持的标识符中，将调用 **AddRef** 并 **返回此** 指针。</span><span class="sxs-lookup"><span data-stu-id="8693b-107">If the requested identifier is among those supported, **AddRef** is called and the **this** pointer is returned.</span></span> <span data-ttu-id="8693b-108">如果请求的标识符不在受支持的列表中，则输出指针将设置为 NULL，MAPI_E_INTERFACE_NOT_SUPPORTED返回值。</span><span class="sxs-lookup"><span data-stu-id="8693b-108">If the requested identifier is not on the supported list, the output pointer is set to NULL and the MAPI_E_INTERFACE_NOT_SUPPORTED value is returned.</span></span> 
  
<span data-ttu-id="8693b-109">以下代码示例演示如何在 C++ 中为状态对象（作为 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md)接口的子类的对象）实现 **QueryInterface。**</span><span class="sxs-lookup"><span data-stu-id="8693b-109">The following code example shows how you can implement **QueryInterface** in C++ for a status object, an object that is a subclass of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="8693b-110">**IMAPIStatus** 通过 [IMAPIProp 继承](imapipropiunknown.md)自 **IUnknown** ： IUnknown 。</span><span class="sxs-lookup"><span data-stu-id="8693b-110">**IMAPIStatus** inherits from **IUnknown** through [IMAPIProp : IUnknown](imapipropiunknown.md).</span></span> <span data-ttu-id="8693b-111">因此，如果调用方请求这些接口中的任意一个，可以返回此指针，因为接口通过继承相关。</span><span class="sxs-lookup"><span data-stu-id="8693b-111">Therefore, if a caller asks for any of these interfaces, the **this** pointer can be returned because the interfaces are related through inheritance.</span></span> 
  
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

<span data-ttu-id="8693b-112">以下代码示例演示如何为对象实现 **AddRef** 和 **Release**  `CMyMAPIObject` 方法。</span><span class="sxs-lookup"><span data-stu-id="8693b-112">The following code example shows how to implement the **AddRef** and **Release** methods for the  `CMyMAPIObject` object.</span></span> <span data-ttu-id="8693b-113">由于实现 **AddRef 和** **Release** 非常简单，因此许多服务提供商选择内联实现它们。</span><span class="sxs-lookup"><span data-stu-id="8693b-113">Because implementing **AddRef** and **Release** is straightforward, many service providers choose to implement them inline.</span></span> <span data-ttu-id="8693b-114">调用 Win32 函数 **的 InterlockedIncrement** 和 **InterlockedDecrement** 可确保线程安全。</span><span class="sxs-lookup"><span data-stu-id="8693b-114">The calls to the Win32 functions **InterlockedIncrement** and **InterlockedDecrement** ensure thread safety.</span></span> <span data-ttu-id="8693b-115">对象的内存由析构函数释放，当 **Release** 方法删除对象时调用该函数。</span><span class="sxs-lookup"><span data-stu-id="8693b-115">The memory for the object is freed by the destructor, which is called when the **Release** method deletes the object.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="8693b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8693b-116">See also</span></span>

- [<span data-ttu-id="8693b-117">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="8693b-117">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)
- [<span data-ttu-id="8693b-118">实现 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="8693b-118">Implementing the IUnknown Interface</span></span>](implementing-the-iunknown-interface.md)

