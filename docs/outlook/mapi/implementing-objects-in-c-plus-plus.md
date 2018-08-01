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
ms.openlocfilehash: ea9f37183f33459b09f2730b3efbb7afed3d4766
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775806"
---
# <a name="implementing-objects-in-c"></a><span data-ttu-id="88332-103">在 c + + 中实现对象</span><span class="sxs-lookup"><span data-stu-id="88332-103">Implementing objects in C++</span></span>

<span data-ttu-id="88332-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="88332-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="88332-105">C + + 客户端和服务提供商定义 MAPI 对象通过创建继承他们要实现的接口的类。</span><span class="sxs-lookup"><span data-stu-id="88332-105">C++ clients and service providers define MAPI objects by creating classes that inherit from the interfaces they are implementing.</span></span> <span data-ttu-id="88332-106">每个接口的方法是公共构造函数和类的析构函数。</span><span class="sxs-lookup"><span data-stu-id="88332-106">Each of the interface methods is public, as are the constructor and destructor for the class.</span></span> <span data-ttu-id="88332-107">如果类具有其他方法，它们可以是公共或专用，具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="88332-107">If the class has additional methods, they can be public or private, depending on the implementation.</span></span> <span data-ttu-id="88332-108">所有数据成员都都专用。</span><span class="sxs-lookup"><span data-stu-id="88332-108">All data members are private.</span></span> 
  
<span data-ttu-id="88332-109">下面的代码示例演示如何定义 c + + 状态对象。</span><span class="sxs-lookup"><span data-stu-id="88332-109">The following example code shows how to define a C++ status object.</span></span> <span data-ttu-id="88332-110">`CMyMAPIObject`类继承自[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="88332-110">The  `CMyMAPIObject` class inherits from the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="88332-111">此示例中使用宏的许多 OLE 标头文件 Compobj.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="88332-111">Many of the macros used in this example are defined in the OLE header file Compobj.h.</span></span> <span data-ttu-id="88332-112">第一个类的成员的是基本接口后, 跟继承顺序中的继承接口方法的方法。</span><span class="sxs-lookup"><span data-stu-id="88332-112">The first members of the class are the methods of the base interface, followed by the methods of the inherited interfaces in order of inheritance.</span></span> <span data-ttu-id="88332-113">关注接口定义是任何其他方法，该构造函数和析构函数，数据成员。</span><span class="sxs-lookup"><span data-stu-id="88332-113">Following the interface definitions are any additional methods, the constructor and destructor, and the data members.</span></span> 
  
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

<span data-ttu-id="88332-114">若要使用的实例`CMyMAPIObject`类、 c + + 客户端或服务提供商进行调用的方法之一，如下所示：</span><span class="sxs-lookup"><span data-stu-id="88332-114">To use an instance of the  `CMyMAPIObject` class, C++ clients or service providers make a call to one of its methods as follows:</span></span> 
  
```cpp
lpMyObj->ValidateState(ulUIParam, ulFlags);

```

## <a name="see-also"></a><span data-ttu-id="88332-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88332-115">See also</span></span>

- [<span data-ttu-id="88332-116">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="88332-116">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

