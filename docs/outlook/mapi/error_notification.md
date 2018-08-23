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
ms.openlocfilehash: 2405799fa59abf58583553f8e2d3718d68411a19
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574970"
---
# <a name="errornotification"></a>ERROR_NOTIFICATION

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
介绍与错误相关的信息。 这会导致要生成的错误通知。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
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
  
> 由**lpEntryID**指向中的项标识符的字节数。 
    
 **lpEntryID**
  
> 将导致错误的对象的项标识符的指针。
    
 **scode**
  
> 严重错误的错误值。 
    
 **ulFlags**
  
> 用于指定的文本的格式的标志位掩码指向所指的**lpMAPIError**结构中的**lpszError**成员。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 **lpMAPIError**
  
> 指向[MAPIERROR](mapierror.md)结构描述该错误的指针。 
    
## <a name="remarks"></a>注解

**ERROR_NOTIFICATION**结构是联合的结构[通知](notification.md)结构的**信息**成员中包含的成员之一。 如果**通知**结构的**信息**成员包含**ERROR_NOTIFICATION**结构，**通知**结构的**ulEventType**成员设置为_fnevCriticalError_。
  
**CbEntryID**成员和**lpEntryID**成员的值可以是 NULL。 
  
有关通知的详细信息，请参阅下表中所述的主题。
  
|**主题**|**说明**|
|:-----|:-----|
|[MAPI 中的事件通知](event-notification-in-mapi.md) <br/> |通知和通知事件的一般概述。  <br/> |
|[处理通知](handling-notifications.md) <br/> |讨论了客户端应如何处理通知。  <br/> |
|[支持事件通知](supporting-event-notification.md) <br/> |讨论的服务提供程序如何使用**IMAPISupport**方法生成通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIERROR](mapierror.md)
  
[通知](notification.md)


[MAPI 结构](mapi-structures.md)

