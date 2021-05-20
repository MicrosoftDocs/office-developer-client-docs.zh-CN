---
title: OBJECT_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OBJECT_NOTIFICATION
api_type:
- COM
ms.assetid: de3a2297-e0cc-427b-a978-52bade4d9bce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c637b3b03a22f208123397f7277cf8968f2509a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430166"
---
# <a name="object_notification"></a>OBJECT_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关已进行更改的对象的信息，例如正在复制或修改。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _OBJECT_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  ULONG ulObjType;
  ULONG cbParentID;
  LPENTRYID lpParentID;
  ULONG cbOldID;
  LPENTRYID lpOldID;
  ULONG cbOldParentID;
  LPENTRYID lpOldParentID;
  LPSPropTagArray lpPropTagArray;
} OBJECT_NOTIFICATION;

```

## <a name="members"></a>Members

 **cbEntryID**
  
> **lpEntryID** 成员指向的条目标识符中的字节数。 
    
 **lpEntryID**
  
> 指向受影响对象的条目标识符的指针。
    
 **ulObjType**
  
> 受影响对象的类型。 可能的类型如下所示：
    
MAPI_STORE 
  
> 邮件存储。 
    
MAPI_ADDRBOOK 
  
> 通讯簿。 
    
MAPI_FOLDER 
  
> 文件夹。
    
MAPI_ABCONT 
  
> 通讯簿容器。
    
MAPI_MESSAGE 
  
> 消息。
    
MAPI_MAILUSER 
  
> 消息用户。
    
MAPI_ATTACH 
  
> 附件。
    
MAPI_DISTLIST 
  
> 通讯组列表。
    
MAPI_PROFSECT 
  
> "配置文件"部分。
    
MAPI_STATUS 
  
> Status 对象。
    
MAPI_SESSION 
  
> Session 对象。
    
 **cbParentID**
  
> **lpParentID** 成员指向的条目标识符中的字节数。 
    
 **lpParentID**
  
> 指向受影响对象的父级的条目标识符的指针。
    
 **cbOldID**
  
> **lpOldID** 成员指向的条目标识符中的字节数。 
    
 **lpOldID**
  
> 指向原始对象的条目标识符的指针。 如果事件不需要原始对象，则此指针可以是 NULL。
    
 **cbOldParentID**
  
> **lpOldParentID** 成员指向的条目标识符中的字节数。 
    
 **lpOldParentID**
  
> 指向原始对象的父对象的条目标识符的指针。 如果事件不需要原始对象，则此指针可以是 NULL。
    
 **lpPropTagArray**
  
> 指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含标识受事件影响的属性的属性标记。 
    
## <a name="remarks"></a>备注

the **OBJECT_NOTIFICATION** structure is one of the union of structures included in the **info** member of the [NOTIFICATION](notification.md) structure. 当 **NOTIFICATION** 结构的信息成员包含一个OBJECT_NOTIFICATION 结构时 **，NOTIFICATION** 结构的 **ulEventType** 成员将设置为以下类型的事件之一： 
  
- fnevObjectCreated
    
- fnevObjectModified
    
- fnevObjectDeleted
    
- fnevObjectMoved
    
- fnevObjectCopied
    
- fnevSearchComplete
    
搜索完成事件（由 fnevSearchComplete 事件类型表示）指示一个搜索文件夹的域的初始搜索已完成。
  
以下包含有关原始对象的信息的成员仅用于移动和复制事件。 
  
- **cbOldID**
    
- **lpOldID**
    
- **cbOldParentID**
    
- **lpOldParentID**
    
这些成员不适用于其他类型的事件。
  
有关通知详细信息，请参阅下表中介绍的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论服务提供商如何使用 [IMAPISupport](imapisupportiunknown.md) 方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[SPropTagArray](sproptagarray.md)


[MAPI 结构](mapi-structures.md)

