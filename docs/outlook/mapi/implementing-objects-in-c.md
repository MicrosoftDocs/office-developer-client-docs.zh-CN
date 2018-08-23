---
title: 在 C 中实现对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 24fc4d78-726d-40ff-bad2-25dc298bd51a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d07d756abded137d3268daf7dd0998f0c953cb1d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563945"
---
# <a name="implementing-objects-in-c"></a><span data-ttu-id="e0a10-103">在 C 中实现对象</span><span class="sxs-lookup"><span data-stu-id="e0a10-103">Implementing objects in C</span></span>

<span data-ttu-id="e0a10-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0a10-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0a10-105">客户端应用程序和服务提供商编写 C 中定义 MAPI 对象通过创建的数据结构和数组称为虚拟函数表或 vtable 顺序的函数指针。</span><span class="sxs-lookup"><span data-stu-id="e0a10-105">Client applications and service providers written in C define MAPI objects by creating a data structure and an array of ordered function pointers known as a virtual function table, or vtable.</span></span> <span data-ttu-id="e0a10-106">一个指向 vtable 必须是第一个数据结构的成员。</span><span class="sxs-lookup"><span data-stu-id="e0a10-106">A pointer to the vtable must be the first member of the data structure.</span></span>
  
<span data-ttu-id="e0a10-107">Vtable 本身，在没有对象支持每个接口中的每个方法的一个指针。</span><span class="sxs-lookup"><span data-stu-id="e0a10-107">In the vtable itself, there is one pointer for every method in each interface supported by the object.</span></span> <span data-ttu-id="e0a10-108">指针的顺序必须遵循的顺序 Mapidefs.h 头文件中发布接口规范中的方法。</span><span class="sxs-lookup"><span data-stu-id="e0a10-108">The order of the pointers must follow the order of the methods in the interface specification published in the Mapidefs.h header file.</span></span> <span data-ttu-id="e0a10-109">Vtable 中的每个函数指针设置为实际方法的实现的地址。</span><span class="sxs-lookup"><span data-stu-id="e0a10-109">Each function pointer in the vtable is set to the address of the actual implementation of the method.</span></span> <span data-ttu-id="e0a10-110">在 c + + 编译器自动设置 vtable。</span><span class="sxs-lookup"><span data-stu-id="e0a10-110">In C++, the compiler automatically sets up the vtable.</span></span> <span data-ttu-id="e0a10-111">在 C 中，没有影响。</span><span class="sxs-lookup"><span data-stu-id="e0a10-111">In C, it does not.</span></span> 
  
<span data-ttu-id="e0a10-112">下图显示了此的工作原理。</span><span class="sxs-lookup"><span data-stu-id="e0a10-112">The following illustration shows how this works.</span></span> <span data-ttu-id="e0a10-113">最左边框代表需要使用服务提供商对象的客户端。</span><span class="sxs-lookup"><span data-stu-id="e0a10-113">The box on the far left represents a client that needs to use a service provider object.</span></span> <span data-ttu-id="e0a10-114">通过会话，客户端获取指向对象， **lpObject**的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a10-114">Through the session, the client obtains a pointer to the object, **lpObject**.</span></span> <span data-ttu-id="e0a10-115">私有数据和方法后跟对象中第一个出现 vtable。</span><span class="sxs-lookup"><span data-stu-id="e0a10-115">The vtable appears first in the object followed by private data and methods.</span></span> <span data-ttu-id="e0a10-116">Vtable 指针指向实际 vtable，其中包含指向每个接口中的方法的实现。</span><span class="sxs-lookup"><span data-stu-id="e0a10-116">The vtable pointer points to the actual vtable, which contains pointers to each of the implementations of the methods in the interface.</span></span> 
  
<span data-ttu-id="e0a10-117">**对象实现**</span><span class="sxs-lookup"><span data-stu-id="e0a10-117">**Object implementation**</span></span>
  
<span data-ttu-id="e0a10-118">![对象实现](media/amapi_42.gif "对象实现")</span><span class="sxs-lookup"><span data-stu-id="e0a10-118">![Object implementation](media/amapi_42.gif "Object implementation")</span></span>
  
<span data-ttu-id="e0a10-119">下面的代码示例演示如何 C 服务提供商可以定义一个简单的状态对象。</span><span class="sxs-lookup"><span data-stu-id="e0a10-119">The following code example shows how a C service provider can define a simple status object.</span></span> <span data-ttu-id="e0a10-120">第一个成员是 vtable 指针;对象的其余数据成员组成。</span><span class="sxs-lookup"><span data-stu-id="e0a10-120">The first member is the vtable pointer; the rest of the object is made up of data members.</span></span> 
  
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

<span data-ttu-id="e0a10-121">此对象是状态对象，因为 vtable 包含指向每个中的方法的实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)界面，以及指向的每个中的基本接口方法实现 — **IUnknown**和**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="e0a10-121">Because this object is a status object, the vtable includes pointers to implementations of each of the methods in the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface, as well as pointers to implementations of each of the methods in the base interfaces — **IUnknown** and **IMAPIProp**.</span></span> <span data-ttu-id="e0a10-122">在 vtable 中的方法的顺序 Mapidefs.h 标头文件中定义匹配指定的顺序。</span><span class="sxs-lookup"><span data-stu-id="e0a10-122">The order of methods in the vtable matches the specified order as defined in the Mapidefs.h header file.</span></span>
  
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

<span data-ttu-id="e0a10-123">客户端和 C 中写入的服务提供商使用通过 vtable 间接对象，并为每个呼叫中的第一个参数添加对象指针。</span><span class="sxs-lookup"><span data-stu-id="e0a10-123">Clients and service providers written in C use objects indirectly through the vtable and add an object pointer as the first parameter in every call.</span></span> <span data-ttu-id="e0a10-124">每次调用 MAPI 接口方法需要对其第一个参数作为这里调用对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e0a10-124">Every call to a MAPI interface method requires a pointer to the object being called as its first parameter.</span></span> <span data-ttu-id="e0a10-125">C + + 定义一个特殊的指针，称为**this**指针实现此目的。</span><span class="sxs-lookup"><span data-stu-id="e0a10-125">C++ defines a special pointer known as the **this** pointer for this purpose.</span></span> <span data-ttu-id="e0a10-126">C + + 编译器隐式将**此**指针作为第一个参数添加到每个方法调用。</span><span class="sxs-lookup"><span data-stu-id="e0a10-126">The C++ compiler implicitly adds the **this** pointer as the first parameter to every method call.</span></span> <span data-ttu-id="e0a10-127">在 C 没有此类指针;它必须显式添加。</span><span class="sxs-lookup"><span data-stu-id="e0a10-127">In C there is no such pointer; it must be explicitly added.</span></span> 
  
<span data-ttu-id="e0a10-128">下面的代码演示如何客户端可以向发起呼叫的 MYSTATUSOBJECT 实例：</span><span class="sxs-lookup"><span data-stu-id="e0a10-128">The following code demonstrates how a client can make a call to an instance of MYSTATUSOBJECT:</span></span>
  
```C
lpMyObj->lpVtbl->ValidateState(lpMyObj, ulUIParam, ulFlags);
 
```

## <a name="see-also"></a><span data-ttu-id="e0a10-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a10-129">See also</span></span>

- [<span data-ttu-id="e0a10-130">实现 MAPI 对象</span><span class="sxs-lookup"><span data-stu-id="e0a10-130">Implementing MAPI Objects</span></span>](implementing-mapi-objects.md)

