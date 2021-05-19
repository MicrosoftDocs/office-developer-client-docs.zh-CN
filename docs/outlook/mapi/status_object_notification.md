---
title: STATUS_OBJECT_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STATUS_OBJECT_NOTIFICATION
api_type:
- COM
ms.assetid: 2872130d-a36b-46ea-bfd1-4700fe3dd41b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84b44b4b054a2b2617502a6a463a6d4a89546804
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426266"
---
# <a name="status_object_notification"></a>STATUS_OBJECT_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述受更改影响的状态对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG cValues;
  LPSPropValue lpPropVals;
} STATUS_OBJECT_NOTIFICATION;

```

## <a name="members"></a>Members

 **cbEntryID**
  
> **lpEntryID** 成员指向的条目标识符中的字节数。 
    
 **lpEntryID**
  
> 指向已更改状态对象的条目标识符的指针。
    
 **cValues**
  
> [lpPropVals](spropvalue.md)成员指向的数组中的 **SPropValue** 结构计数。 
    
 **lpPropVals**
  
> 指向描述已更改状态对象的属性 **的 SPropValue** 结构的数组的指针。 
    
## <a name="remarks"></a>备注

the **STATUS_OBJECT_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure. the **STATUS_OBJECT_NOTIFICATION** structure is included with a status object notification for an event of type  _fnevStatusObjectModified_. 状态对象通知是一个内部 MAPI 通知;客户端和服务提供商无法注册它，服务提供商无法生成它。
  
有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 **IMAPISupport** 方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

