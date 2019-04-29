---
title: 使用 C 实现对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 24fc4d78-726d-40ff-bad2-25dc298bd51a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6026e697cc31545bf7ef518fcbd33ea8db48af5d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414940"
---
# <a name="implementing-objects-in-c"></a><span data-ttu-id="cf8a0-103">使用 C 实现对象</span><span class="sxs-lookup"><span data-stu-id="cf8a0-103">Implementing objects in C</span></span>

<span data-ttu-id="cf8a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf8a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf8a0-105">在 C 中编写的客户端应用程序和服务提供程序通过创建一个数据结构和一个被排序的函数指针 (称为虚拟函数表) 或 vtable 的数组来定义 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-105">Client applications and service providers written in C define MAPI objects by creating a data structure and an array of ordered function pointers known as a virtual function table, or vtable.</span></span> <span data-ttu-id="cf8a0-106">指向 vtable 的指针必须是数据结构的第一个成员。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-106">A pointer to the vtable must be the first member of the data structure.</span></span>
  
<span data-ttu-id="cf8a0-107">在 vtable 本身中, 对象支持的每个接口中的每个方法都有一个指针。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-107">In the vtable itself, there is one pointer for every method in each interface supported by the object.</span></span> <span data-ttu-id="cf8a0-108">指针的顺序必须遵循在 mapidefs.h 头文件中发布的接口规范中的方法的顺序。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-108">The order of the pointers must follow the order of the methods in the interface specification published in the Mapidefs.h header file.</span></span> <span data-ttu-id="cf8a0-109">vtable 中的每个函数指针都设置为方法的实际实现的地址。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-109">Each function pointer in the vtable is set to the address of the actual implementation of the method.</span></span> <span data-ttu-id="cf8a0-110">在 c + + 中, 编译器会自动设置 vtable。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-110">In C++, the compiler automatically sets up the vtable.</span></span> <span data-ttu-id="cf8a0-111">在 C 中, 它不会。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-111">In C, it does not.</span></span> 
  
<span data-ttu-id="cf8a0-112">下图显示了这是如何工作的。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-112">The following illustration shows how this works.</span></span> <span data-ttu-id="cf8a0-113">最左侧的框表示需要使用服务提供程序对象的客户端。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-113">The box on the far left represents a client that needs to use a service provider object.</span></span> <span data-ttu-id="cf8a0-114">通过会话, 客户端获取指向对象 ( **lpObject**) 的指针。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-114">Through the session, the client obtains a pointer to the object, **lpObject**.</span></span> <span data-ttu-id="cf8a0-115">vtable 先出现在对象中, 然后是私有数据和方法。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-115">The vtable appears first in the object followed by private data and methods.</span></span> <span data-ttu-id="cf8a0-116">vtable 指针指向实际 vtable, 其中包含指向接口中方法的每个实现的指针。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-116">The vtable pointer points to the actual vtable, which contains pointers to each of the implementations of the methods in the interface.</span></span> 
  
<span data-ttu-id="cf8a0-117">**对象实现**</span><span class="sxs-lookup"><span data-stu-id="cf8a0-117">**Object implementation**</span></span>
  
<span data-ttu-id="cf8a0-118">![对象实现](media/amapi_42.gif "对象实现")</span><span class="sxs-lookup"><span data-stu-id="cf8a0-118">![Object implementation](media/amapi_42.gif "Object implementation")</span></span>
  
<span data-ttu-id="cf8a0-119">下面的代码示例演示 C 服务提供程序如何定义一个简单的 status 对象。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-119">The following code example shows how a C service provider can define a simple status object.</span></span> <span data-ttu-id="cf8a0-120">第一个成员是 vtable 指针;对象的其余部分由数据成员组成。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-120">The first member is the vtable pointer; the rest of the object is made up of data members.</span></span> 
  
```C
typedef struct _MYSTATUSOBJECT
{
    const STATUS_Vtbl FAR *lpVtbl;
    ULONG              cRef;
    ANOTHEROBJ        *pObj;
    LPMAPIPROP         lpProp;
    LPFREEBUFFER       lpFreeBuf;
} MYSTATUSOBJECT, *LPMYSTATUSOBJ;
 
```

<span data-ttu-id="cf8a0-121">由于此对象是一个 status 对象, 因此 vtable 包括指向[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口中每个方法的实现的指针, 以及指向基本接口中每个方法的实现的指针 (IUnknown)。 \*\*\*\* 和**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-121">Because this object is a status object, the vtable includes pointers to implementations of each of the methods in the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface, as well as pointers to implementations of each of the methods in the base interfaces — **IUnknown** and **IMAPIProp**.</span></span> <span data-ttu-id="cf8a0-122">vtable 中方法的顺序与 mapidefs.h 头文件中定义的指定顺序相匹配。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-122">The order of methods in the vtable matches the specified order as defined in the Mapidefs.h header file.</span></span>
  
```js
static const MYOBJECT_Vtbl vtblSTATUS =
{
    STATUS_QueryInterface,
    STATUS_AddRef,
    STATUS_Release,
    STATUS_GetLastError,
    STATUS_SaveChanges,
    STATUS_GetProps,
    STATUS_GetPropList,
    STATUS_OpenProperty,
    STATUS_SetProps,
    STATUS_DeleteProps,
    STATUS_CopyTo,
    STATUS_CopyProps,
    STATUS_GetNamesFromIDs,
    STATUS_GetIDsFromNames,
    STATUS_ValidateState,
    STATUS_SettingsDialog,
    STATUS_ChangePassword,
    STATUS_FlushQueues
};
 
```

<span data-ttu-id="cf8a0-123">使用 C 编写的客户端和服务提供程序通过 vtable 间接使用对象, 并在每次调用中将对象指针添加为第一个参数。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-123">Clients and service providers written in C use objects indirectly through the vtable and add an object pointer as the first parameter in every call.</span></span> <span data-ttu-id="cf8a0-124">每次调用 MAPI 接口方法时, 都需要一个指向作为其第一个参数调用的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-124">Every call to a MAPI interface method requires a pointer to the object being called as its first parameter.</span></span> <span data-ttu-id="cf8a0-125">c + + 将一个特殊指针 (称为**this**指针) 定义为实现此目的。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-125">C++ defines a special pointer known as the **this** pointer for this purpose.</span></span> <span data-ttu-id="cf8a0-126">c + + 编译器将**此**指针隐式添加为每个方法调用的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-126">The C++ compiler implicitly adds the **this** pointer as the first parameter to every method call.</span></span> <span data-ttu-id="cf8a0-127">在 C 中, 没有此类指针;必须显式添加它。</span><span class="sxs-lookup"><span data-stu-id="cf8a0-127">In C there is no such pointer; it must be explicitly added.</span></span> 
  
<span data-ttu-id="cf8a0-128">下面的代码演示客户端如何调用 MYSTATUSOBJECT 的实例:</span><span class="sxs-lookup"><span data-stu-id="cf8a0-128">The following code demonstrates how a client can make a call to an instance of MYSTATUSOBJECT:</span></span>
  
```C
lpMyObj->lpVtbl->ValidateState(lpMyObj, ulUIParam, ulFlags);
 
```

## <a name="see-also"></a><span data-ttu-id="cf8a0-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8a0-129">See also</span></span>

- [<span data-ttu-id="cf8a0-130">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="cf8a0-130">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

