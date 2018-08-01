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
ms.openlocfilehash: 71e0a08436c925f0d68d63111722cc01bd73cc5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778894"
---
# <a name="statusobjectnotification"></a>STATUS_OBJECT_NOTIFICATION

  
  
**适用于**： Outlook 
  
介绍受更改状态对象。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 由**lpEntryID**成员指向中的项标识符的字节数。 
    
 **lpEntryID**
  
> 更改的状态对象的项标识符的指针。
    
 **cValues**
  
> 由**lpPropVals**成员指向[SPropValue](spropvalue.md)结构数组中的计数。 
    
 **lpPropVals**
  
> 指向介绍已更改的状态对象的属性的**SPropValue**结构的数组。 
    
## <a name="remarks"></a>说明

**STATUS_OBJECT_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。 包含状态的对象通知事件的类型_fnevStatusObjectModified_ **STATUS_OBJECT_NOTIFICATION**结构。 状态对象通知是内部的 MAPI 通知;客户端与服务提供程序无法为其注册和服务提供程序无法生成它。
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用**IMAPISupport**方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

