---
title: 使用 C++ 实现 IUnknown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 68519f6c-fba8-47f5-9401-316e276f770e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 08f3f3f937320d8a986b2002c761a37f0f749227
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397833"
---
# <a name="implementing-iunknown-in-c"></a><span data-ttu-id="acbe0-103">使用 C++ 实现 IUnknown</span><span class="sxs-lookup"><span data-stu-id="acbe0-103">Implementing IUnknown in C++</span></span>

<span data-ttu-id="acbe0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="acbe0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="acbe0-105">在 c + + 中实现的[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)、 [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)和[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法是相当简单。</span><span class="sxs-lookup"><span data-stu-id="acbe0-105">Implementing the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx), [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx), and [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) methods of the [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) interface in C++ is fairly simple.</span></span> <span data-ttu-id="acbe0-106">后的参数中传递的一些标准验证， **QueryInterface**实现检查的受支持接口的列表对请求的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="acbe0-106">After some standard validation of the parameters that are passed in, an implementation of **QueryInterface** checks the identifier of the requested interface against the list of supported interfaces.</span></span> <span data-ttu-id="acbe0-107">如果之间所支持的请求的标识符， **AddRef**称为，则返回**此**指针。</span><span class="sxs-lookup"><span data-stu-id="acbe0-107">If the requested identifier is among those supported, **AddRef** is called and the **this** pointer is returned.</span></span> <span data-ttu-id="acbe0-108">如果请求的标识符不在受支持的列表中，将输出指针设置为 NULL，并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 值。</span><span class="sxs-lookup"><span data-stu-id="acbe0-108">If the requested identifier is not on the supported list, the output pointer is set to NULL and the MAPI_E_INTERFACE_NOT_SUPPORTED value is returned.</span></span> 
  
<span data-ttu-id="acbe0-109">下面的代码示例演示如何实现**QueryInterface** c + + 中对于状态对象，一个对象，它的一个子类[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="acbe0-109">The following code example shows how you can implement **QueryInterface** in C++ for a status object, an object that is a subclass of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="acbe0-110">**IMAPIStatus**继承通过的**IUnknown** [IMAPIProp: IUnknown](imapipropiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="acbe0-110">**IMAPIStatus** inherits from **IUnknown** through [IMAPIProp : IUnknown](imapipropiunknown.md).</span></span> <span data-ttu-id="acbe0-111">因此，如果呼叫者要求的任何这些接口，**该**指针可以返回，因为通过继承相关的接口。</span><span class="sxs-lookup"><span data-stu-id="acbe0-111">Therefore, if a caller asks for any of these interfaces, the **this** pointer can be returned because the interfaces are related through inheritance.</span></span> 
  
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

<span data-ttu-id="acbe0-112">下面的代码示例演示如何实现**AddRef**和**Release**的方法，用于`CMyMAPIObject`对象。</span><span class="sxs-lookup"><span data-stu-id="acbe0-112">The following code example shows how to implement the **AddRef** and **Release** methods for the  `CMyMAPIObject` object.</span></span> <span data-ttu-id="acbe0-113">由于实现**AddRef**和**Release**很简单，许多服务提供商选择实现它们内嵌。</span><span class="sxs-lookup"><span data-stu-id="acbe0-113">Because implementing **AddRef** and **Release** is straightforward, many service providers choose to implement them inline.</span></span> <span data-ttu-id="acbe0-114">对**InterlockedIncrement**和**InterlockedDecrement** Win32 函数的调用确保线程安全。</span><span class="sxs-lookup"><span data-stu-id="acbe0-114">The calls to the Win32 functions **InterlockedIncrement** and **InterlockedDecrement** ensure thread safety.</span></span> <span data-ttu-id="acbe0-115">通过对析构函数，调用**Release**方法删除该对象时释放对象的内存。</span><span class="sxs-lookup"><span data-stu-id="acbe0-115">The memory for the object is freed by the destructor, which is called when the **Release** method deletes the object.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="acbe0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acbe0-116">See also</span></span>

- [<span data-ttu-id="acbe0-117">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="acbe0-117">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)
- [<span data-ttu-id="acbe0-118">实施 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="acbe0-118">Implementing the IUnknown Interface</span></span>](implementing-the-iunknown-interface.md)

