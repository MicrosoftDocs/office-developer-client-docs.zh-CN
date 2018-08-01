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
ms.openlocfilehash: 71a8dc6472051e72d990a5c5d6f026ae63f1df25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775816"
---
# <a name="implementing-objects-in-c"></a>在 C 中实现对象

**适用于**： Outlook 
  
客户端应用程序和服务提供商编写 C 中定义 MAPI 对象通过创建的数据结构和数组称为虚拟函数表或 vtable 顺序的函数指针。 一个指向 vtable 必须是第一个数据结构的成员。
  
Vtable 本身，在没有对象支持每个接口中的每个方法的一个指针。 指针的顺序必须遵循的顺序 Mapidefs.h 头文件中发布接口规范中的方法。 Vtable 中的每个函数指针设置为实际方法的实现的地址。 在 c + + 编译器自动设置 vtable。 在 C 中，没有影响。 
  
下图显示了此的工作原理。 最左边框代表需要使用服务提供商对象的客户端。 通过会话，客户端获取指向对象， **lpObject**的指针。 私有数据和方法后跟对象中第一个出现 vtable。 Vtable 指针指向实际 vtable，其中包含指向每个接口中的方法的实现。 
  
**对象实现**
  
![对象实现](media/amapi_42.gif "对象实现")
  
下面的代码示例演示如何 C 服务提供商可以定义一个简单的状态对象。 第一个成员是 vtable 指针;对象的其余数据成员组成。 
  
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

此对象是状态对象，因为 vtable 包含指向每个中的方法的实现[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)界面，以及指向的每个中的基本接口方法实现 — **IUnknown**和**IMAPIProp**。 在 vtable 中的方法的顺序 Mapidefs.h 标头文件中定义匹配指定的顺序。
  
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

客户端和 C 中写入的服务提供商使用通过 vtable 间接对象，并为每个呼叫中的第一个参数添加对象指针。 每次调用 MAPI 接口方法需要对其第一个参数作为这里调用对象的指针。 C + + 定义一个特殊的指针，称为**this**指针实现此目的。 C + + 编译器隐式将**此**指针作为第一个参数添加到每个方法调用。 在 C 没有此类指针;它必须显式添加。 
  
下面的代码演示如何客户端可以向发起呼叫的 MYSTATUSOBJECT 实例：
  
```C
lpMyObj->lpVtbl->ValidateState(lpMyObj, ulUIParam, ulFlags);
 
```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)

