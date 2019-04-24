---
title: 实现示例对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23b6ad1a-0b50-429f-8819-ab72c56581c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a681e68c0718e49da331946d75ecb7b4fab7afe2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332828"
---
# <a name="implementing-a-sample-object"></a><span data-ttu-id="fd8c4-103">实现示例对象</span><span class="sxs-lookup"><span data-stu-id="fd8c4-103">Implementing a sample object</span></span>

<span data-ttu-id="fd8c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd8c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd8c4-105">建议接收器对象 (支持[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口的对象) 是客户端应用程序为处理通知而实现的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-105">Advise sink objects — objects that support the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface — are MAPI objects that client applications implement for processing notifications.</span></span> <span data-ttu-id="fd8c4-106">**IMAPIAdviseSink**直接从[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)继承, 且只包含一个方法**OnNotify**。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-106">**IMAPIAdviseSink** inherits directly from [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) and contains only one method, **OnNotify**.</span></span> <span data-ttu-id="fd8c4-107">因此, 若要实现通知接收器对象, 客户端将为**IUnknown**和[OnNotify](imapiadvisesink-onnotify.md)的三种方法创建代码。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-107">Therefore, to implement an advise sink object, a client creates code for the three methods in **IUnknown** and for [OnNotify](imapiadvisesink-onnotify.md).</span></span>
  
<span data-ttu-id="fd8c4-108">mapidefs.h 头文件使用**DECLARE_MAPI_INTERFACE**定义**IMAPIAdviseSink**接口实现, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="fd8c4-108">The Mapidefs.h header file defines an **IMAPIAdviseSink** interface implementation by using **DECLARE_MAPI_INTERFACE**, as follows:</span></span>
  
```cpp
#define      INTERFACE  IMAPIAdviseSink
DECLARE_MAPI_INTERFACE_(IMAPIAdviseSink, IUnknown)
{
    BEGIN_INTERFACE
    MAPI_IUNKNOWN_METHODS(PURE)
    MAPI_IMAPIADVISESINK_METHODS(PURE)
};
 
```

<span data-ttu-id="fd8c4-109">实现通知接收器对象的客户端可以手动或使用**MAPI_IUNKNOWN_METHODS**和**MAPI_IMAPIADVISESINK_METHODS**宏定义其对象中的接口。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-109">Clients that implement advise sink objects can define their interfaces in their objects manually or with the **MAPI_IUNKNOWN_METHODS** and **MAPI_IMAPIADVISESINK_METHODS** macros.</span></span> <span data-ttu-id="fd8c4-110">对象实施者应尽可能使用接口宏, 以确保对象之间的一致性并节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-110">Object implementers should use the interface macros whenever possible to ensure consistency across objects and to save time and effort.</span></span> 
  
<span data-ttu-id="fd8c4-111">实现[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)和[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法相对简单, 因为通常只需要几行代码。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-111">Implementing the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) and [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) methods is relatively simple because typically only a few lines of code are needed.</span></span> <span data-ttu-id="fd8c4-112">因此, 实现对象的客户端和服务提供程序可以将其**AddRef**和**发布**实现内联。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-112">Therefore, clients and service providers that implement objects can make their **AddRef** and **Release** implementations inline.</span></span> <span data-ttu-id="fd8c4-113">下面的代码演示如何定义包含**AddRef**和**Release**的内联实现的 c + + 通知接收器对象。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-113">The following code shows how to define a C++ advise sink object with inline implementations of **AddRef** and **Release**.</span></span>
  
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

<span data-ttu-id="fd8c4-114">在 C 中, 建议接收器对象由以下元素组成:</span><span class="sxs-lookup"><span data-stu-id="fd8c4-114">In C, the advise sink object is composed of the following elements:</span></span>
  
- <span data-ttu-id="fd8c4-115">指向 vtable 的一种指针, 该指针包含指向**IUnknown**和**IMAPIAdviseSink**中每个方法的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-115">A pointer to a vtable that contains pointers to implementations of each of the methods in **IUnknown** and **IMAPIAdviseSink**.</span></span>
    
- <span data-ttu-id="fd8c4-116">数据成员。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-116">Data members.</span></span>
    
<span data-ttu-id="fd8c4-117">下面的代码示例演示如何在 C 中定义一个建议接收器对象并构造其 vtable。</span><span class="sxs-lookup"><span data-stu-id="fd8c4-117">The following code example shows how to define an advise sink object in C and construct its vtable.</span></span> 
  
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

<span data-ttu-id="fd8c4-118">在 C 中声明一个对象后, 必须通过将 vtable 指针设置为构造的 vtable 的地址来对其进行初始化, 如以下代码所示:</span><span class="sxs-lookup"><span data-stu-id="fd8c4-118">After you declare an object in C, you must initialize it by setting the vtable pointer to the address of the constructed vtable, as shown in the following code:</span></span>
  
```cpp
LPADVISESINK lpMyObj = NULL;
HRESULT hr = (*lpAllocateBuffer) (sizeof(ADVISESINK),
                 (LPVOID *)&lpMyObj);
lpMyObj->lpVtbl = &vtblADVISE;
 
```

## <a name="see-also"></a><span data-ttu-id="fd8c4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8c4-119">See also</span></span>

- [<span data-ttu-id="fd8c4-120">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="fd8c4-120">MAPI Property Overview</span></span>](mapi-property-overview.md)
- [<span data-ttu-id="fd8c4-121">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="fd8c4-121">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

