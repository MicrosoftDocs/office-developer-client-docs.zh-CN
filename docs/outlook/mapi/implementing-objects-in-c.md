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
# <a name="implementing-objects-in-c"></a>使用 C 实现对象

**适用于**：Outlook 2013 | Outlook 2016 
  
使用 C 编写的客户端应用程序和服务提供商通过创建数据结构和一组有序函数指针（称为虚拟函数表或 vtable）来定义 MAPI 对象。 指向 vtable 的指针必须是数据结构的第一个成员。
  
在 vtable 本身中，对象支持的每个接口中每个方法都有一个指针。 指针的顺序必须遵循 Mapidefs.h 头文件中发布的接口规范中的方法顺序。 vtable 中的每个函数指针都设置为方法实际实现的地址。 在 C++ 中，编译器会自动设置 vtable。 在 C 中，它不会。 
  
下图演示了此操作的工作原理。 最左侧的框表示需要使用服务提供程序对象的客户端。 通过会话，客户端获取指向对象的指针 **lpObject**。 vtable 首先出现在 对象中，后跟私有数据和方法。 vtable 指针指向实际 vtable，其中包含指向接口中方法的每个实现的指针。 
  
**对象实现**
  
![对象实现](media/amapi_42.gif "对象实现")
  
以下代码示例演示 C 服务提供商如何定义简单的状态对象。 第一个成员是 vtable 指针;对象的其余部分由数据成员组成。 
  
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

由于此对象是状态对象，vtable 包括指向 [IMAPIStatus 中每个方法的实现（IMAPIProp](imapistatusimapiprop.md) 接口）的指针，以及指向基本接口 **（IUnknown** 和 **IMAPIProp）** 中每个方法的实现的指针。 vtable 中的方法顺序与 Mapidefs.h 头文件中定义的指定顺序匹配。
  
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

使用 C 编写的客户端和服务提供商间接通过 vtable 使用对象，并添加对象指针作为每次调用的第一个参数。 每次调用 MAPI 接口方法都需要一个指向要调用的对象的指针作为其第一个参数。 为此，C++ 定义了一个称为 **此指针** 的特殊指针。 C++ 编译器隐式地将 **此** 指针添加为每个方法调用的第一个参数。 在 C 中，没有此类指针;必须显式添加。 
  
以下代码演示客户端如何调用 MYSTATUSOBJECT 的实例：
  
```C
lpMyObj->lpVtbl->ValidateState(lpMyObj, ulUIParam, ulFlags);
 
```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)

