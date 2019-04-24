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
# <a name="implementing-iunknown-in-c"></a><span data-ttu-id="bebc0-103">使用 C 实现 IUnknown</span><span class="sxs-lookup"><span data-stu-id="bebc0-103">Implementing IUnknown in C</span></span>

<span data-ttu-id="bebc0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bebc0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bebc0-105">c 中[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法的实现与 c + + 实现非常相似。</span><span class="sxs-lookup"><span data-stu-id="bebc0-105">Implementations of the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method in C are very similar to C++ implementations.</span></span> <span data-ttu-id="bebc0-106">对于实现, 有两个基本步骤:</span><span class="sxs-lookup"><span data-stu-id="bebc0-106">There are two basic steps to the implementation:</span></span> 
  
1. <span data-ttu-id="bebc0-107">验证参数。</span><span class="sxs-lookup"><span data-stu-id="bebc0-107">Validating parameters.</span></span>
    
2. <span data-ttu-id="bebc0-108">根据对象支持的接口列表检查所请求接口的标识符, 并返回 E_NO_INTERFACE 值或有效的接口指针。</span><span class="sxs-lookup"><span data-stu-id="bebc0-108">Checking the identifier of the requested interface against the list of interfaces supported by the object and returning either the E_NO_INTERFACE value or a valid interface pointer.</span></span> <span data-ttu-id="bebc0-109">如果返回接口指针, 则实现还应调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来递增引用计数。</span><span class="sxs-lookup"><span data-stu-id="bebc0-109">If an interface pointer is returned, the implementation should also call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method to increment the reference count.</span></span> 
    
<span data-ttu-id="bebc0-110">c 和 c + + 中的**QueryInterface**实现之间的主要区别是 c 版本中的额外第一个参数。</span><span class="sxs-lookup"><span data-stu-id="bebc0-110">The main difference between an implementation of **QueryInterface** in C and C++ is the additional first parameter in the C version.</span></span> <span data-ttu-id="bebc0-111">由于将对象指针添加到参数列表中, 因此**QueryInterface**的 C 实现必须具有比 c + + 实现更多的参数验证。</span><span class="sxs-lookup"><span data-stu-id="bebc0-111">Because the object pointer is added to the parameter list, a C implementation of **QueryInterface** must have more parameter validation than a C++ implementation.</span></span> <span data-ttu-id="bebc0-112">用于检查接口标识符、递增引用计数和返回对象指针的逻辑在这两种语言中应相同。</span><span class="sxs-lookup"><span data-stu-id="bebc0-112">The logic for checking the interface identifier, incrementing the reference count, and returning an object pointer should be identical in both languages.</span></span> 
  
<span data-ttu-id="bebc0-113">下面的代码示例演示如何在 C 中为 status 对象实现**QueryInterface** 。</span><span class="sxs-lookup"><span data-stu-id="bebc0-113">The following code example shows how to implement **QueryInterface** in C for a status object.</span></span> 
  
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

<span data-ttu-id="bebc0-114">尽管 c 中的**AddRef**方法的实现与 c + + 实现类似, 但[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法的 C 实现可能比 c + + 版本更精密。</span><span class="sxs-lookup"><span data-stu-id="bebc0-114">Whereas the implementation of the **AddRef** method in C is similar to a C++ implementation, a C implementation of the [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method can get more elaborate than a C++ version.</span></span> <span data-ttu-id="bebc0-115">这是因为释放对象时所涉及的大部分功能可以合并到 c + + 构造函数和析构函数中, 而 C 没有这样的机制。</span><span class="sxs-lookup"><span data-stu-id="bebc0-115">This is because much of the functionality involved with freeing an object can be incorporated into the C++ constructor and destructor, and C has no such mechanism.</span></span> <span data-ttu-id="bebc0-116">所有这些功能都必须包含在**Release**方法中。</span><span class="sxs-lookup"><span data-stu-id="bebc0-116">All of this functionality must be included in the **Release** method.</span></span> <span data-ttu-id="bebc0-117">此外, 由于其他参数及其显式 vtable, 因此需要进行更多的验证。</span><span class="sxs-lookup"><span data-stu-id="bebc0-117">Also, because of the additional parameter and its explicit vtable, more validation is required.</span></span> 
  
<span data-ttu-id="bebc0-118">以下**AddRef**方法调用说明了 status 对象的典型 C 实现。</span><span class="sxs-lookup"><span data-stu-id="bebc0-118">The following **AddRef** method call illustrates a typical C implementation for a status object.</span></span> 
  
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

<span data-ttu-id="bebc0-119">下面的代码示例演示 C 状态对象的典型**版本**实现。</span><span class="sxs-lookup"><span data-stu-id="bebc0-119">The following code example shows a typical implementation of **Release** for a C status object.</span></span> <span data-ttu-id="bebc0-120">如果引用计数为0减后, 则 C 状态对象实现应执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="bebc0-120">If the reference count is 0 after it is decremented, a C status object implementation should perform the following tasks:</span></span> 
  
- <span data-ttu-id="bebc0-121">释放指向对象的任何保留指针。</span><span class="sxs-lookup"><span data-stu-id="bebc0-121">Release any held pointers to objects.</span></span> 
    
- <span data-ttu-id="bebc0-122">将 vtable 设置为 NULL, 以便在对象的用户调用了**Release**但仍继续尝试使用该对象的情况下便于调试。</span><span class="sxs-lookup"><span data-stu-id="bebc0-122">Set the vtable to NULL, facilitating debugging in the case where an object's user called **Release** yet continued to try to use the object.</span></span> 
    
- <span data-ttu-id="bebc0-123">调用**MAPIFreeBuffer**以释放该对象。</span><span class="sxs-lookup"><span data-stu-id="bebc0-123">Call **MAPIFreeBuffer** to free the object.</span></span> 
    
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

## <a name="see-also"></a><span data-ttu-id="bebc0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bebc0-124">See also</span></span>

- [<span data-ttu-id="bebc0-125">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="bebc0-125">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)
- [<span data-ttu-id="bebc0-126">实现 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="bebc0-126">Implementing the IUnknown Interface</span></span>](implementing-the-iunknown-interface.md)

