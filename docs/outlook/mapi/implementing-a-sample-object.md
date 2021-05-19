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
# <a name="implementing-a-sample-object"></a>实现示例对象

**适用于**：Outlook 2013 | Outlook 2016 
  
建议接收对象（支持 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口的对象）是客户端应用程序为处理通知而实现 MAPI 对象。 **IMAPIAdviseSink** 直接从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 继承，并且仅包含一个方法 **OnNotify**。 因此，为了实施建议接收对象，客户端在 **IUnknown** 和 [OnNotify](imapiadvisesink-onnotify.md)中为三个方法创建代码。
  
Mapidefs.h 头文件通过使用 DECLARE_MAPI_INTERFACE **定义****IMAPIAdviseSink** 接口实现，如下所示：
  
```cpp
#define      INTERFACE  IMAPIAdviseSink
DECLARE_MAPI_INTERFACE_(IMAPIAdviseSink, IUnknown)
{
    BEGIN_INTERFACE
    MAPI_IUNKNOWN_METHODS(PURE)
    MAPI_IMAPIADVISESINK_METHODS(PURE)
};
 
```

实现建议接收对象的客户端可以手动定义其对象中的接口，或者使用 MAPI_IUNKNOWN_METHODS 和MAPI_IMAPIADVISESINK_METHODS **定义接口**。 对象实现者应尽可能使用接口宏，以确保对象之间的一致性并节省时间和精力。 
  
实现 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) 和 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法相对简单，因为通常只需要几行代码。 因此，实现对象的客户端和服务提供商可以内联实现 **其 AddRef** 和 **Release。** 以下代码演示如何使用 **AddRef** 和 Release 的内联实现定义 C++ 建议接收 **对象**。
  
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

在 C 中，建议接收对象由以下元素组成：
  
- 指向包含指向 **IUnknown** 和 **IMAPIAdviseSink** 中每个方法的实现指针的 vtable 的指针。
    
- 数据成员。
    
下面的代码示例演示如何使用 C 定义建议接收器对象并构造其 vtable。 
  
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

在 C 中声明对象后，必须通过将 vtable 指针设置为构造的 vtable 的地址来初始化该对象，如以下代码所示：
  
```cpp
LPADVISESINK lpMyObj = NULL;
HRESULT hr = (*lpAllocateBuffer) (sizeof(ADVISESINK),
                 (LPVOID *)&lpMyObj);
lpMyObj->lpVtbl = &vtblADVISE;
 
```

## <a name="see-also"></a>另请参阅

- [MAPI 属性概述](mapi-property-overview.md)
- [实现 MAPI 对象](implementing-mapi-objects.md)

