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
# <a name="implementing-a-sample-object"></a><span data-ttu-id="82329-103">实现示例对象</span><span class="sxs-lookup"><span data-stu-id="82329-103">Implementing a sample object</span></span>

<span data-ttu-id="82329-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82329-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82329-105">建议接收对象（支持 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口的对象）是客户端应用程序为处理通知而实现 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="82329-105">Advise sink objects — objects that support the [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md) interface — are MAPI objects that client applications implement for processing notifications.</span></span> <span data-ttu-id="82329-106">**IMAPIAdviseSink** 直接从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 继承，并且仅包含一个方法 **OnNotify**。</span><span class="sxs-lookup"><span data-stu-id="82329-106">**IMAPIAdviseSink** inherits directly from [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) and contains only one method, **OnNotify**.</span></span> <span data-ttu-id="82329-107">因此，为了实施建议接收对象，客户端在 **IUnknown** 和 [OnNotify](imapiadvisesink-onnotify.md)中为三个方法创建代码。</span><span class="sxs-lookup"><span data-stu-id="82329-107">Therefore, to implement an advise sink object, a client creates code for the three methods in **IUnknown** and for [OnNotify](imapiadvisesink-onnotify.md).</span></span>
  
<span data-ttu-id="82329-108">Mapidefs.h 头文件通过使用 DECLARE_MAPI_INTERFACE **定义\*\*\*\*IMAPIAdviseSink** 接口实现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="82329-108">The Mapidefs.h header file defines an **IMAPIAdviseSink** interface implementation by using **DECLARE_MAPI_INTERFACE**, as follows:</span></span>
  
```cpp
#define      INTERFACE  IMAPIAdviseSink
DECLARE_MAPI_INTERFACE_(IMAPIAdviseSink, IUnknown)
{
    BEGIN_INTERFACE
    MAPI_IUNKNOWN_METHODS(PURE)
    MAPI_IMAPIADVISESINK_METHODS(PURE)
};
 
```

<span data-ttu-id="82329-109">实现建议接收对象的客户端可以手动定义其对象中的接口，或者使用 MAPI_IUNKNOWN_METHODS 和MAPI_IMAPIADVISESINK_METHODS **定义接口**。</span><span class="sxs-lookup"><span data-stu-id="82329-109">Clients that implement advise sink objects can define their interfaces in their objects manually or with the **MAPI_IUNKNOWN_METHODS** and **MAPI_IMAPIADVISESINK_METHODS** macros.</span></span> <span data-ttu-id="82329-110">对象实现者应尽可能使用接口宏，以确保对象之间的一致性并节省时间和精力。</span><span class="sxs-lookup"><span data-stu-id="82329-110">Object implementers should use the interface macros whenever possible to ensure consistency across objects and to save time and effort.</span></span> 
  
<span data-ttu-id="82329-111">实现 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) 和 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法相对简单，因为通常只需要几行代码。</span><span class="sxs-lookup"><span data-stu-id="82329-111">Implementing the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) and [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) methods is relatively simple because typically only a few lines of code are needed.</span></span> <span data-ttu-id="82329-112">因此，实现对象的客户端和服务提供商可以内联实现 **其 AddRef** 和 **Release。**</span><span class="sxs-lookup"><span data-stu-id="82329-112">Therefore, clients and service providers that implement objects can make their **AddRef** and **Release** implementations inline.</span></span> <span data-ttu-id="82329-113">以下代码演示如何使用 **AddRef** 和 Release 的内联实现定义 C++ 建议接收 **对象**。</span><span class="sxs-lookup"><span data-stu-id="82329-113">The following code shows how to define a C++ advise sink object with inline implementations of **AddRef** and **Release**.</span></span>
  
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

<span data-ttu-id="82329-114">在 C 中，建议接收对象由以下元素组成：</span><span class="sxs-lookup"><span data-stu-id="82329-114">In C, the advise sink object is composed of the following elements:</span></span>
  
- <span data-ttu-id="82329-115">指向包含指向 **IUnknown** 和 **IMAPIAdviseSink** 中每个方法的实现指针的 vtable 的指针。</span><span class="sxs-lookup"><span data-stu-id="82329-115">A pointer to a vtable that contains pointers to implementations of each of the methods in **IUnknown** and **IMAPIAdviseSink**.</span></span>
    
- <span data-ttu-id="82329-116">数据成员。</span><span class="sxs-lookup"><span data-stu-id="82329-116">Data members.</span></span>
    
<span data-ttu-id="82329-117">下面的代码示例演示如何使用 C 定义建议接收器对象并构造其 vtable。</span><span class="sxs-lookup"><span data-stu-id="82329-117">The following code example shows how to define an advise sink object in C and construct its vtable.</span></span> 
  
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

<span data-ttu-id="82329-118">在 C 中声明对象后，必须通过将 vtable 指针设置为构造的 vtable 的地址来初始化该对象，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="82329-118">After you declare an object in C, you must initialize it by setting the vtable pointer to the address of the constructed vtable, as shown in the following code:</span></span>
  
```cpp
LPADVISESINK lpMyObj = NULL;
HRESULT hr = (*lpAllocateBuffer) (sizeof(ADVISESINK),
                 (LPVOID *)&lpMyObj);
lpMyObj->lpVtbl = &vtblADVISE;
 
```

## <a name="see-also"></a><span data-ttu-id="82329-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82329-119">See also</span></span>

- [<span data-ttu-id="82329-120">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="82329-120">MAPI Property Overview</span></span>](mapi-property-overview.md)
- [<span data-ttu-id="82329-121">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="82329-121">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

