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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310185"
---
# <a name="implementing-objects-in-c"></a>使用 C 实现对象

**适用于**：Outlook 2013 | Outlook 2016 
  
在 C 中编写的客户端应用程序和服务提供程序通过创建一个数据结构和一个被排序的函数指针 (称为虚拟函数表) 或 vtable 的数组来定义 MAPI 对象。 指向 vtable 的指针必须是数据结构的第一个成员。
  
在 vtable 本身中, 对象支持的每个接口中的每个方法都有一个指针。 指针的顺序必须遵循在 mapidefs.h 头文件中发布的接口规范中的方法的顺序。 vtable 中的每个函数指针都设置为方法的实际实现的地址。 在 c + + 中, 编译器会自动设置 vtable。 在 C 中, 它不会。 
  
下图显示了这是如何工作的。 最左侧的框表示需要使用服务提供程序对象的客户端。 通过会话, 客户端获取指向对象 ( **lpObject**) 的指针。 vtable 先出现在对象中, 然后是私有数据和方法。 vtable 指针指向实际 vtable, 其中包含指向接口中方法的每个实现的指针。 
  
**对象实现**
  
![对象实现](media/amapi_42.gif "对象实现")
  
下面的代码示例演示 C 服务提供程序如何定义一个简单的 status 对象。 第一个成员是 vtable 指针;对象的其余部分由数据成员组成。 
  
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

由于此对象是一个 status 对象, 因此 vtable 包括指向[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口中每个方法的实现的指针, 以及指向基本接口中每个方法的实现的指针 (IUnknown)。 **** 和**IMAPIProp**。 vtable 中方法的顺序与 mapidefs.h 头文件中定义的指定顺序相匹配。
  
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

使用 C 编写的客户端和服务提供程序通过 vtable 间接使用对象, 并在每次调用中将对象指针添加为第一个参数。 每次调用 MAPI 接口方法时, 都需要一个指向作为其第一个参数调用的对象的指针。 c + + 将一个特殊指针 (称为**this**指针) 定义为实现此目的。 c + + 编译器将**此**指针隐式添加为每个方法调用的第一个参数。 在 C 中, 没有此类指针;必须显式添加它。 
  
下面的代码演示客户端如何调用 MYSTATUSOBJECT 的实例:
  
```C
lpMyObj->lpVtbl->ValidateState(lpMyObj, ulUIParam, ulFlags);
 
```

## <a name="see-also"></a>另请参阅

- [实现 MAPI 对象](implementing-mapi-objects.md)

