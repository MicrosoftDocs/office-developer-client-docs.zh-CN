---
title: ERROR_NOTIFICATION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ERROR_NOTIFICATION
api_type:
- COM
ms.assetid: 6c5bb383-f8e2-4d79-bcf2-aa86c130e8b1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f8d4fb6b8cd7ad0ebf1e7660a0f3c0602274fa10
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425440"
---
# <a name="errornotification"></a>ERROR_NOTIFICATION

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍与严重错误相关的信息。 这将导致生成错误通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _ERROR_NOTIFICATION
{
  ULONG cbEntryID;
  LPENTRYID lpEntryID;
  SCODE scode;
  ULONG ulFlags;
  LPMAPIERROR lpMAPIError;
} ERROR_NOTIFICATION;
```

## <a name="members"></a>Members

 **cbEntryID**
  
> 由**lpEntryID**指向的条目标识符中的字节数。 
    
 **lpEntryID**
  
> 指向导致错误的对象的条目标识符的指针。
    
 **scode**
  
> 严重错误的错误值。 
    
 **ulFlags**
  
> 标志的位掩码, 用于指定由**lpMAPIError**指向的结构中的**lpszError**成员所指向的文本的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 **lpMAPIError**
  
> 指向描述错误的[MAPIERROR](mapierror.md)结构的指针。 
    
## <a name="remarks"></a>说明

**ERROR_NOTIFICATION**结构是[通知](notification.md)结构的**info**成员中包含的结构联合的成员之一。 当**通知**结构的**info**成员包含**ERROR_NOTIFICATION**结构时,**通知**结构的**ulEventType**成员将设置为_fnevCriticalError_。
  
**cbEntryID**成员和**lpEntryID**成员的值可以为 NULL。 
  
有关通知的详细信息, 请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论了如何使用**IMAPISupport**方法生成通知的服务提供商。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[NOTIFICATION](notification.md)


[MAPI 结构](mapi-structures.md)

