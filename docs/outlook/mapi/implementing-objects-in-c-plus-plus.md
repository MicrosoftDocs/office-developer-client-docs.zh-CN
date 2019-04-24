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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310148"
---
# <a name="implementing-objects-in-c"></a><span data-ttu-id="e5501-103">使用 C++ 实现对象</span><span class="sxs-lookup"><span data-stu-id="e5501-103">Implementing objects in C++</span></span>

<span data-ttu-id="e5501-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e5501-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e5501-105">c + + 客户端和服务提供程序通过创建从其实现的接口继承的类来定义 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="e5501-105">C++ clients and service providers define MAPI objects by creating classes that inherit from the interfaces they are implementing.</span></span> <span data-ttu-id="e5501-106">每个接口方法都是公共的, 这也是类的构造函数和析构函数。</span><span class="sxs-lookup"><span data-stu-id="e5501-106">Each of the interface methods is public, as are the constructor and destructor for the class.</span></span> <span data-ttu-id="e5501-107">如果该类具有其他方法, 则它们可以是公共的, 也可以是私有的, 具体取决于实现。</span><span class="sxs-lookup"><span data-stu-id="e5501-107">If the class has additional methods, they can be public or private, depending on the implementation.</span></span> <span data-ttu-id="e5501-108">所有数据成员都是私有的。</span><span class="sxs-lookup"><span data-stu-id="e5501-108">All data members are private.</span></span> 
  
<span data-ttu-id="e5501-109">下面的示例代码演示如何定义 c + + 状态对象。</span><span class="sxs-lookup"><span data-stu-id="e5501-109">The following example code shows how to define a C++ status object.</span></span> <span data-ttu-id="e5501-110">`CMyMAPIObject`该类继承自[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e5501-110">The  `CMyMAPIObject` class inherits from the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="e5501-111">此示例中使用的许多宏都是在 OLE 头文件 Compobj 中定义的。</span><span class="sxs-lookup"><span data-stu-id="e5501-111">Many of the macros used in this example are defined in the OLE header file Compobj.h.</span></span> <span data-ttu-id="e5501-112">类的第一个成员是基接口的方法, 后跟继承接口的继承方法。</span><span class="sxs-lookup"><span data-stu-id="e5501-112">The first members of the class are the methods of the base interface, followed by the methods of the inherited interfaces in order of inheritance.</span></span> <span data-ttu-id="e5501-113">后面的接口定义是任何其他方法, 即构造函数和析构函数以及数据成员。</span><span class="sxs-lookup"><span data-stu-id="e5501-113">Following the interface definitions are any additional methods, the constructor and destructor, and the data members.</span></span> 
  
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

<span data-ttu-id="e5501-114">若要使用`CMyMAPIObject`类的实例, c + + 客户端或服务提供程序将对其方法之一进行调用, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="e5501-114">To use an instance of the  `CMyMAPIObject` class, C++ clients or service providers make a call to one of its methods as follows:</span></span> 
  
```cpp
lpMyObj->ValidateState(ulUIParam, ulFlags);

```

## <a name="see-also"></a><span data-ttu-id="e5501-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5501-115">See also</span></span>

- [<span data-ttu-id="e5501-116">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="e5501-116">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

