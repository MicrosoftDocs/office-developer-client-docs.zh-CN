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
ms.openlocfilehash: 1593152786a3345827089e5f6702454896944b1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776545"
---
# <a name="objectnotification"></a>OBJECT_NOTIFICATION

  
  
**适用于**： Outlook 
  
包含有关对象已进行更改，如正在复制或修改的信息。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 由**lpEntryID**成员指向中的项标识符的字节数。 
    
 **lpEntryID**
  
> 受影响的对象的项标识符的指针。
    
 **ulObjType**
  
> 受影响的对象类型。 可能的类型如下所示：
    
MAPI_STORE 
  
> 邮件存储区。 
    
MAPI_ADDRBOOK 
  
> 通讯簿。 
    
MAPI_FOLDER 
  
> 文件夹。
    
MAPI_ABCONT 
  
> 通讯簿容器。
    
MAPI_MESSAGE 
  
> 消息。
    
MAPI_MAILUSER 
  
> 邮件用户。
    
MAPI_ATTACH 
  
> 附件。
    
MAPI_DISTLIST 
  
> 通讯组列表。
    
MAPI_PROFSECT 
  
> 配置文件一节。
    
MAPI_STATUS 
  
> 状态对象。
    
MAPI_SESSION 
  
> 会话对象。
    
 **cbParentID**
  
> 由**lpParentID**成员指向中的项标识符的字节数。 
    
 **lpParentID**
  
> 受影响的对象的父对象的项标识符的指针。
    
 **cbOldID**
  
> 由**lpOldID**成员指向中的项标识符的字节数。 
    
 **lpOldID**
  
> 指向原始对象的项标识符的指针。 如果事件不需要原始对象，该指针可以为 NULL。
    
 **cbOldParentID**
  
> 由**lpOldParentID**成员指向中的项标识符的字节数。 
    
 **lpOldParentID**
  
> 指向原始对象的父对象的项标识符的指针。 如果事件不需要原始对象，该指针可以为 NULL。
    
 **lpPropTagArray**
  
> 指向包含属性标记标识受影响的事件属性[SPropTagArray](sproptagarray.md)结构。 
    
## <a name="remarks"></a>说明

**OBJECT_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。 如果**通知**结构的**信息**成员包含**OBJECT_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为以下类型的事件之一： 
  
- fnevObjectCreated
    
- fnevObjectModified
    
- fnevObjectDeleted
    
- fnevObjectMoved
    
- fnevObjectCopied
    
- fnevSearchComplete
    
搜索完整事件，由 fnevSearchComplete 事件类型，表示一个搜索文件夹的域的初始搜索已完成。
  
仅在移动和复制事件中使用包含有关原始对象的以下成员。 
  
- **cbOldID**
    
- **lpOldID**
    
- **cbOldParentID**
    
- **lpOldParentID**
    
这些成员不适用于其他类型的事件。
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用[IMAPISupport](imapisupportiunknown.md)方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[NOTIFICATION](notification.md)
  
[SPropTagArray](sproptagarray.md)


[MAPI 结构](mapi-structures.md)

