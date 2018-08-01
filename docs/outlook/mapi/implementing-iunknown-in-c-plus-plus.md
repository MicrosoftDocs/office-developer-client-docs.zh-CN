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
ms.openlocfilehash: c899eb0afd123b26e12081f5157be3bae7917813
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775813"
---
# <a name="implementing-iunknown-in-c"></a><span data-ttu-id="3eaba-103">使用 C++ 实现 IUnknown</span><span class="sxs-lookup"><span data-stu-id="3eaba-103">Implementing IUnknown in C++</span></span>

<span data-ttu-id="3eaba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3eaba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3eaba-105">在 c + + 中实现的[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)接口[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)、 [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)和[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法是相当简单。</span><span class="sxs-lookup"><span data-stu-id="3eaba-105">Implementing the [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx), [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx), and [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) methods of the [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) interface in C++ is fairly simple.</span></span> <span data-ttu-id="3eaba-106">后的参数中传递的一些标准验证， **QueryInterface**实现检查的受支持接口的列表对请求的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="3eaba-106">After some standard validation of the parameters that are passed in, an implementation of **QueryInterface** checks the identifier of the requested interface against the list of supported interfaces.</span></span> <span data-ttu-id="3eaba-107">如果之间所支持的请求的标识符， **AddRef**称为，则返回**此**指针。</span><span class="sxs-lookup"><span data-stu-id="3eaba-107">If the requested identifier is among those supported, **AddRef** is called and the **this** pointer is returned.</span></span> <span data-ttu-id="3eaba-108">如果请求的标识符不在受支持的列表中，将输出指针设置为 NULL，并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 值。</span><span class="sxs-lookup"><span data-stu-id="3eaba-108">If the requested identifier is not on the supported list, the output pointer is set to NULL and the MAPI_E_INTERFACE_NOT_SUPPORTED value is returned.</span></span> 
  
<span data-ttu-id="3eaba-109">下面的代码示例演示如何实现**QueryInterface** c + + 中对于状态对象，一个对象，它的一个子类[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="3eaba-109">The following code example shows how you can implement **QueryInterface** in C++ for a status object, an object that is a subclass of the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="3eaba-110">**IMAPIStatus**继承通过的**IUnknown** [IMAPIProp: IUnknown](imapipropiunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="3eaba-110">**IMAPIStatus** inherits from **IUnknown** through [IMAPIProp : IUnknown](imapipropiunknown.md).</span></span> <span data-ttu-id="3eaba-111">因此，如果呼叫者要求的任何这些接口，**该**指针可以返回，因为通过继承相关的接口。</span><span class="sxs-lookup"><span data-stu-id="3eaba-111">Therefore, if a caller asks for any of these interfaces, the **this** pointer can be returned because the interfaces are related through inheritance.</span></span> 
  
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

<span data-ttu-id="3eaba-112">下面的代码示例演示如何实现**AddRef**和**Release**的方法，用于`CMyMAPIObject`对象。</span><span class="sxs-lookup"><span data-stu-id="3eaba-112">The following code example shows how to implement the **AddRef** and **Release** methods for the  `CMyMAPIObject` object.</span></span> <span data-ttu-id="3eaba-113">由于实现**AddRef**和**Release**很简单，许多服务提供商选择实现它们内嵌。</span><span class="sxs-lookup"><span data-stu-id="3eaba-113">Because implementing **AddRef** and **Release** is straightforward, many service providers choose to implement them inline.</span></span> <span data-ttu-id="3eaba-114">对**InterlockedIncrement**和**InterlockedDecrement** Win32 函数的调用确保线程安全。</span><span class="sxs-lookup"><span data-stu-id="3eaba-114">The calls to the Win32 functions **InterlockedIncrement** and **InterlockedDecrement** ensure thread safety.</span></span> <span data-ttu-id="3eaba-115">通过对析构函数，调用**Release**方法删除该对象时释放对象的内存。</span><span class="sxs-lookup"><span data-stu-id="3eaba-115">The memory for the object is freed by the destructor, which is called when the **Release** method deletes the object.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="3eaba-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3eaba-116">See also</span></span>

- [<span data-ttu-id="3eaba-117">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="3eaba-117">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)
- [<span data-ttu-id="3eaba-118">实施 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="3eaba-118">Implementing the IUnknown Interface</span></span>](implementing-the-iunknown-interface.md)

