---
title: 实现示例对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23b6ad1a-0b50-429f-8819-ab72c56581c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7d2f5fc2f26019902b27750613f7c360a751cd51
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582929"
---
# <a name="implementing-a-sample-object"></a><span data-ttu-id="07267-103">实现示例对象</span><span class="sxs-lookup"><span data-stu-id="07267-103">Implementing a sample object</span></span>

<span data-ttu-id="07267-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07267-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07267-105">建议接收器对象 — 对象支持的[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口 — 是 MAPI 对象客户端应用程序实现处理通知。</span><span class="sxs-lookup"><span data-stu-id="07267-105">Advise sink objects — objects that support the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface — are MAPI objects that client applications implement for processing notifications.</span></span> <span data-ttu-id="07267-106">**IMAPIAdviseSink**直接从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)继承，并且只包含一个方法， **OnNotify**。</span><span class="sxs-lookup"><span data-stu-id="07267-106">**IMAPIAdviseSink** inherits directly from [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) and contains only one method, **OnNotify**.</span></span> <span data-ttu-id="07267-107">因此，若要实现接收器 advise 对象，客户端创建代码**IUnknown**中的三种方法和[OnNotify](imapiadvisesink-onnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="07267-107">Therefore, to implement an advise sink object, a client creates code for the three methods in **IUnknown** and for [OnNotify](imapiadvisesink-onnotify.md).</span></span>
  
<span data-ttu-id="07267-108">Mapidefs.h 头文件，如下所示使用**DECLARE_MAPI_INTERFACE**，定义**IMAPIAdviseSink**接口实现：</span><span class="sxs-lookup"><span data-stu-id="07267-108">The Mapidefs.h header file defines an **IMAPIAdviseSink** interface implementation by using **DECLARE_MAPI_INTERFACE**, as follows:</span></span>
  
```cpp
#define      INTERFACE  IMAPIAdviseSink
DECLARE_MAPI_INTERFACE_(IMAPIAdviseSink, IUnknown)
{
    BEGIN_INTERFACE
    MAPI_IUNKNOWN_METHODS(PURE)
    MAPI_IMAPIADVISESINK_METHODS(PURE)
};
 
```

<span data-ttu-id="07267-109">实施客户端建议接收器对象可以定义其接口其对象中手动或**MAPI_IUNKNOWN_METHODS**和**MAPI_IMAPIADVISESINK_METHODS**宏。</span><span class="sxs-lookup"><span data-stu-id="07267-109">Clients that implement advise sink objects can define their interfaces in their objects manually or with the **MAPI_IUNKNOWN_METHODS** and **MAPI_IMAPIADVISESINK_METHODS** macros.</span></span> <span data-ttu-id="07267-110">对象实施应使用尽可能以确保跨对象的一致性并节省时间和精力接口宏。</span><span class="sxs-lookup"><span data-stu-id="07267-110">Object implementers should use the interface macros whenever possible to ensure consistency across objects and to save time and effort.</span></span> 
  
<span data-ttu-id="07267-111">实现的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)和[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法是相对简单，因为通常需仅几行代码。</span><span class="sxs-lookup"><span data-stu-id="07267-111">Implementing the [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) and [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) methods is relatively simple because typically only a few lines of code are needed.</span></span> <span data-ttu-id="07267-112">因此，客户端和实现对象的服务提供商可以使其**AddRef**和**Release**实现内嵌。</span><span class="sxs-lookup"><span data-stu-id="07267-112">Therefore, clients and service providers that implement objects can make their **AddRef** and **Release** implementations inline.</span></span> <span data-ttu-id="07267-113">下面的代码演示如何定义 c + + 建议的**AddRef**和**Release**的内嵌实现接收器对象。</span><span class="sxs-lookup"><span data-stu-id="07267-113">The following code shows how to define a C++ advise sink object with inline implementations of **AddRef** and **Release**.</span></span>
  
```cpp
class  CMAPIAdviseSink : public IMAPIAdviseSink
{
public:
    STDMETHODIMP QueryInterface
                    (REFIID                     riid,
                     LPVOID *                   ppvObj);
    inline STDMETHODIMP_(ULONG) AddRef
                    () { InterlockedIncrement(m_cRef);
                         ++m_cRef;
                         InterlockedDecrement(m_cRef);
                         return m_cRef; };
    inline STDMETHODIMP_(ULONG) Release
                    () { InterlockedIncrement(m_cRef);
                         ULONG ulCount = --m_cRef;
                         InterlockedDecrement(m_cRef);
                         if (!ulCount)  delete this;
                         return ulCount;};
    MAPI_IMAPIADVISESINK_METHODS(IMPL);
    BOOL WINAPI AddConnection (LPMDB pMDBObj, ULONG ulConnection);
    void WINAPI RemoveAllLinks (LPMDB pMDBObj);
// Constructors and destructors.
public :
    inline CMAPIAdviseSink  (CStoreClient * pStore)
                            { m_cRef = 1;
                              m_ulConnection = 0;
                              m_pStore = pStore;
                              AddRef;};
    ~CMAPIAdviseSink () {Release};
private :
    ULONG               m_cRef;
    CStoreClient *      m_pStore;
    ULONG               m_ulConnection;
};
 
```

<span data-ttu-id="07267-114">在 C 中，advise 接收器对象组成的以下元素：</span><span class="sxs-lookup"><span data-stu-id="07267-114">In C, the advise sink object is composed of the following elements:</span></span>
  
- <span data-ttu-id="07267-115">指向包含指向每个**IUnknown**和**IMAPIAdviseSink**方法的实现 vtable 的指针。</span><span class="sxs-lookup"><span data-stu-id="07267-115">A pointer to a vtable that contains pointers to implementations of each of the methods in **IUnknown** and **IMAPIAdviseSink**.</span></span>
    
- <span data-ttu-id="07267-116">数据成员。</span><span class="sxs-lookup"><span data-stu-id="07267-116">Data members.</span></span>
    
<span data-ttu-id="07267-117">下面的代码示例演示如何 C 中定义 advise 接收器对象并构建其 vtable。</span><span class="sxs-lookup"><span data-stu-id="07267-117">The following code example shows how to define an advise sink object in C and construct its vtable.</span></span> 
  
```cpp
// Object definition.
typedef struct _ADVISESINK
{
    const ADVISE_Vtbl FAR *    lpVtbl;
    ULONG             cRef;
    STORECLIENT      *pStore;
    ULONG             ulConnection;
} ADVISESINK, *LPADVISESINK;
// vtable definition.
static const ADVISE_Vtbl vtblADVISE =
{
    ADVISE_QueryInterface,
    ADVISE_AddRef,
    ADVISE_Release,
    ADVISE_OnNotify
};
 
```

<span data-ttu-id="07267-118">声明中 C 对象后，必须初始化通过设置 vtable 指针的地址的构造 vtable，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="07267-118">After you declare an object in C, you must initialize it by setting the vtable pointer to the address of the constructed vtable, as shown in the following code:</span></span>
  
```cpp
LPADVISESINK lpMyObj = NULL;
HRESULT hr = (*lpAllocateBuffer) (sizeof(ADVISESINK),
                 (LPVOID *)&lpMyObj);
lpMyObj->lpVtbl = &vtblADVISE;
 
```

## <a name="see-also"></a><span data-ttu-id="07267-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07267-119">See also</span></span>

- [<span data-ttu-id="07267-120">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="07267-120">MAPI Property Overview</span></span>](mapi-property-overview.md)
- [<span data-ttu-id="07267-121">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="07267-121">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

