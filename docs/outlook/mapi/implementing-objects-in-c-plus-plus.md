---
title: 在 c + + 中实现对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d1a050ff-3cf9-4bf7-812d-b7c1b31056e7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4c233f9855674080496b2e54ba9548a53738ead8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574725"
---
# <a name="implementing-objects-in-c"></a>在 c + + 中实现对象

**适用于**： Outlook 2013 |Outlook 2016 
  
C + + 客户端和服务提供商定义 MAPI 对象通过创建继承他们要实现的接口的类。 每个接口的方法是公共构造函数和类的析构函数。 如果类具有其他方法，它们可以是公共或专用，具体取决于实现。 所有数据成员都都专用。 
  
下面的代码示例演示如何定义 c + + 状态对象。 `CMyMAPIObject`类继承自[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 此示例中使用宏的许多 OLE 标头文件 Compobj.h 中定义。 第一个类的成员的是基本接口后, 跟继承顺序中的继承接口方法的方法。 关注接口定义是任何其他方法，该构造函数和析构函数，数据成员。 
  
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

若要使用的实例`CMyMAPIObject`类、 c + + 客户端或服务提供商进行调用的方法之一，如下所示： 
  
```cpp
lpMyObj->ValidateState(ulUIParam, ulFlags);

```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)

