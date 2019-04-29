---
title: 使用 C++ 实现对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d1a050ff-3cf9-4bf7-812d-b7c1b31056e7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 89247ca1b263d6f06af73f1ffa14709a2aff23de
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432952"
---
# <a name="implementing-objects-in-c"></a>使用 C++ 实现对象

**适用于**：Outlook 2013 | Outlook 2016 
  
c + + 客户端和服务提供程序通过创建从其实现的接口继承的类来定义 MAPI 对象。 每个接口方法都是公共的, 这也是类的构造函数和析构函数。 如果该类具有其他方法, 则它们可以是公共的, 也可以是私有的, 具体取决于实现。 所有数据成员都是私有的。 
  
下面的示例代码演示如何定义 c + + 状态对象。 `CMyMAPIObject`该类继承自[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 此示例中使用的许多宏都是在 OLE 头文件 Compobj 中定义的。 类的第一个成员是基接口的方法, 后跟继承接口的继承方法。 后面的接口定义是任何其他方法, 即构造函数和析构函数以及数据成员。 
  
```cpp
class  CMyMAPIObject : public IMAPIStatus
{
public:
// Methods of IUnknown.
    STDMETHODIMP QueryInterface (REFIID riid, LPVOID * ppvObj);
    STDMETHODIMP_(ULONG) AddRef ();
    STDMETHODIMP_(ULONG) Release ();
    MAPI_IMAPIPROP_METHODS(IMPL);
    MAPI_IMAPISTATUS_METHODS(IMPL);
// Other methods specific to CMyMAPIObject.
    BOOL WINAPI Method1 ();
    void WINAPI Method2 ();
// Constructors and destructors.
public :
    CMyMAPIObject () {};
    ~CMyMAPIObject () {};
// Data members specific to CMyMAPIObject.
private :
    ULONG               m_cRef;
    CAnotherObj *       m_pObj;
};
 
```

若要使用`CMyMAPIObject`类的实例, c + + 客户端或服务提供程序将对其方法之一进行调用, 如下所示: 
  
```cpp
lpMyObj->ValidateState(ulUIParam, ulFlags);

```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)

