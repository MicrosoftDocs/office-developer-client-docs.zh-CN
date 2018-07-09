---
title: 在 C 中实现 IUnknown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 807b6dc4-cdb7-40a4-87d7-ebc1ad5fab76
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d12201d8476d15021e896a44797ae5fc21178802
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775815"
---
# <a name="implementing-iunknown-in-c"></a><span data-ttu-id="59c33-103">在 C 中实现 IUnknown</span><span class="sxs-lookup"><span data-stu-id="59c33-103">Implementing IUnknown in C</span></span>

<span data-ttu-id="59c33-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="59c33-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59c33-105">C 中的[IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx)方法的实现都是非常类似于 c + + 实现的。</span><span class="sxs-lookup"><span data-stu-id="59c33-105">Implementations of the [IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx) method in C are very similar to C++ implementations.</span></span> <span data-ttu-id="59c33-106">有的实现的两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="59c33-106">There are two basic steps to the implementation:</span></span> 
  
1. <span data-ttu-id="59c33-107">正在验证参数。</span><span class="sxs-lookup"><span data-stu-id="59c33-107">Validating parameters.</span></span>
    
2. <span data-ttu-id="59c33-108">检查的接口对象支持的列表对请求的接口的标识符和返回 E_NO_INTERFACE 值或有效的接口指针。</span><span class="sxs-lookup"><span data-stu-id="59c33-108">Checking the identifier of the requested interface against the list of interfaces supported by the object and returning either the E_NO_INTERFACE value or a valid interface pointer.</span></span> <span data-ttu-id="59c33-109">如果返回的接口指针，实现还应调用[IUnknown::AddRef](http://msdn.microsoft.com/zh-cn/library/ms691379%28v=VS.85%29.aspx)方法，以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="59c33-109">If an interface pointer is returned, the implementation should also call the [IUnknown::AddRef](http://msdn.microsoft.com/zh-cn/library/ms691379%28v=VS.85%29.aspx) method to increment the reference count.</span></span> 
    
<span data-ttu-id="59c33-110">**QueryInterface** C 中实现和 c + + 的主要区别是 C 版本中的其他第一个参数。</span><span class="sxs-lookup"><span data-stu-id="59c33-110">The main difference between an implementation of **QueryInterface** in C and C++ is the additional first parameter in the C version.</span></span> <span data-ttu-id="59c33-111">因为对象指针添加到参数列表中， **QueryInterface** C 实现必须具有比 c + + 实施的多个参数验证。</span><span class="sxs-lookup"><span data-stu-id="59c33-111">Because the object pointer is added to the parameter list, a C implementation of **QueryInterface** must have more parameter validation than a C++ implementation.</span></span> <span data-ttu-id="59c33-112">检查接口标识符、 增加引用计数，以及返回一个对象指针的逻辑应在两种语言相同。</span><span class="sxs-lookup"><span data-stu-id="59c33-112">The logic for checking the interface identifier, incrementing the reference count, and returning an object pointer should be identical in both languages.</span></span> 
  
<span data-ttu-id="59c33-113">下面的代码示例演示如何实现状态对象中 C **QueryInterface** 。</span><span class="sxs-lookup"><span data-stu-id="59c33-113">The following code example shows how to implement **QueryInterface** in C for a status object.</span></span> 
  
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

<span data-ttu-id="59c33-114">类似于 c + + 实现 c **AddRef**方法的实现，而[IUnknown::Release](http://msdn.microsoft.com/zh-cn/library/ms682317%28v=VS.85%29.aspx)方法的 C 实现可以获得更精细比 c + + 版本。</span><span class="sxs-lookup"><span data-stu-id="59c33-114">Whereas the implementation of the **AddRef** method in C is similar to a C++ implementation, a C implementation of the [IUnknown::Release](http://msdn.microsoft.com/zh-cn/library/ms682317%28v=VS.85%29.aspx) method can get more elaborate than a C++ version.</span></span> <span data-ttu-id="59c33-115">这是因为的许多功能所涉及释放对象可以并入 c + + 构造函数和对析构函数，并且 C 已没有这种机制。</span><span class="sxs-lookup"><span data-stu-id="59c33-115">This is because much of the functionality involved with freeing an object can be incorporated into the C++ constructor and destructor, and C has no such mechanism.</span></span> <span data-ttu-id="59c33-116">所有这些功能必须包含**Release**方法。</span><span class="sxs-lookup"><span data-stu-id="59c33-116">All of this functionality must be included in the **Release** method.</span></span> <span data-ttu-id="59c33-117">此外，由于其他参数以及其显式 vtable 详细验证是所需的。</span><span class="sxs-lookup"><span data-stu-id="59c33-117">Also, because of the additional parameter and its explicit vtable, more validation is required.</span></span> 
  
<span data-ttu-id="59c33-118">下面的**AddRef**方法调用演示了一个典型的 C 实现状态对象。</span><span class="sxs-lookup"><span data-stu-id="59c33-118">The following **AddRef** method call illustrates a typical C implementation for a status object.</span></span> 
  
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

<span data-ttu-id="59c33-119">下面的代码示例演示 C 状态对象的**版本**的典型的实现。</span><span class="sxs-lookup"><span data-stu-id="59c33-119">The following code example shows a typical implementation of **Release** for a C status object.</span></span> <span data-ttu-id="59c33-120">如果引用计数递减后为 0，C 状态对象实现应执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="59c33-120">If the reference count is 0 after it is decremented, a C status object implementation should perform the following tasks:</span></span> 
  
- <span data-ttu-id="59c33-121">释放到对象中任何暂的指针。</span><span class="sxs-lookup"><span data-stu-id="59c33-121">Release any held pointers to objects.</span></span> 
    
- <span data-ttu-id="59c33-122">设置为 NULL，从而推动在其中调用**版本**的对象的用户尚未继续尝试使用对象的情况下调试 vtable。</span><span class="sxs-lookup"><span data-stu-id="59c33-122">Set the vtable to NULL, facilitating debugging in the case where an object's user called **Release** yet continued to try to use the object.</span></span> 
    
- <span data-ttu-id="59c33-123">调用**MAPIFreeBuffer**以释放该对象。</span><span class="sxs-lookup"><span data-stu-id="59c33-123">Call **MAPIFreeBuffer** to free the object.</span></span> 
    
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

## <a name="see-also"></a><span data-ttu-id="59c33-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59c33-124">See also</span></span>

- [<span data-ttu-id="59c33-125">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="59c33-125">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)
- [<span data-ttu-id="59c33-126">实现 IUnknown 接口</span><span class="sxs-lookup"><span data-stu-id="59c33-126">Implementing the IUnknown Interface</span></span>](implementing-the-iunknown-interface.md)

