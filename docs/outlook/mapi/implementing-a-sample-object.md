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
# <a name="implementing-a-sample-object"></a>实现示例对象

**适用于**： Outlook 2013 |Outlook 2016 
  
建议接收器对象 — 对象支持的[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口 — 是 MAPI 对象客户端应用程序实现处理通知。 **IMAPIAdviseSink**直接从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)继承，并且只包含一个方法， **OnNotify**。 因此，若要实现接收器 advise 对象，客户端创建代码**IUnknown**中的三种方法和[OnNotify](imapiadvisesink-onnotify.md)。
  
Mapidefs.h 头文件，如下所示使用**DECLARE_MAPI_INTERFACE**，定义**IMAPIAdviseSink**接口实现：
  
```cpp
#define      INTERFACE  IMAPIAdviseSink
DECLARE_MAPI_INTERFACE_(IMAPIAdviseSink, IUnknown)
{
    BEGIN_INTERFACE
    MAPI_IUNKNOWN_METHODS(PURE)
    MAPI_IMAPIADVISESINK_METHODS(PURE)
};
 
```

实施客户端建议接收器对象可以定义其接口其对象中手动或**MAPI_IUNKNOWN_METHODS**和**MAPI_IMAPIADVISESINK_METHODS**宏。 对象实施应使用尽可能以确保跨对象的一致性并节省时间和精力接口宏。 
  
实现的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)和[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法是相对简单，因为通常需仅几行代码。 因此，客户端和实现对象的服务提供商可以使其**AddRef**和**Release**实现内嵌。 下面的代码演示如何定义 c + + 建议的**AddRef**和**Release**的内嵌实现接收器对象。
  
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

在 C 中，advise 接收器对象组成的以下元素：
  
- 指向包含指向每个**IUnknown**和**IMAPIAdviseSink**方法的实现 vtable 的指针。
    
- 数据成员。
    
下面的代码示例演示如何 C 中定义 advise 接收器对象并构建其 vtable。 
  
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

声明中 C 对象后，必须初始化通过设置 vtable 指针的地址的构造 vtable，如下面的代码中所示：
  
```cpp
LPADVISESINK lpMyObj = NULL;
HRESULT hr = (*lpAllocateBuffer) (sizeof(ADVISESINK),
                 (LPVOID *)&lpMyObj);
lpMyObj->lpVtbl = &vtblADVISE;
 
```

## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)
- [实现 MAPI 对象](implementing-mapi-objects.md)

