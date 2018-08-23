---
title: IAddrBookAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Advise
api_type:
- COM
ms.assetid: 2def89ed-e4ce-446a-8b80-132d11ae8f8b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 43569b22cace7b2700d37ace49fd734b45fec73c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580878"
---
# <a name="iaddrbookadvise"></a>IAddrBook::Advise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
注册接收有关对一个或多个条目的更改的通知通讯簿中的客户端或服务提供程序。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向通讯簿容器，消息用户或通讯组列表的_ulEventMask_参数中描述的类型发生更改时，将生成通知的项标识符的指针。 
    
 _ulEventMask_
  
> [in]呼叫者注册接收的一个或多个通知事件。 每个事件相关联的特定通知结构包含有关发生的更改的信息。 下表列出的有效值_ulEventMask_和其对应的结构。 
    
|**通知事件**|**相应的结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectModified** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectCopied** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectMoved** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevTableModified** <br/> |[TABLE_NOTIFICATION](table_notification.md) <br/> |
   
 _lpAdviseSink_
  
> [in]指向要为其请求通知事件发生时调用的 advise 接收器对象的指针。
    
 _lpulConnection_
  
> [输出]一个指向代表通知注册非零值的连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 负责_lpEntryID_中传递的项标识符的地址簿提供程序无法注册相应的项的通知。 
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序负责标识_lpEntryID_参数中传递的项标识符的对象不支持通知。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 不能由任何配置文件中的地址簿提供程序处理_lpEntryID_中传递的项标识符。 
    
## <a name="remarks"></a>注解

客户端和服务提供商调用**Advise**方法注册特定类型或上的通讯簿条目的通知的类型。 通过使用_ulEventMask_参数传递的事件掩码表示通知的类型。 
  
MAPI 转发到的地址簿提供程序负责由_lpEntryID_参数中的项标识符的条目此**Advise**呼叫。 通讯簿提供程序处理的注册本身，或调用支持方法， [IMAPISupport::Subscribe](imapisupport-subscribe.md)，提示 MAPI 注册呼叫者。 返回非零值的连接数来表示成功注册。
  
当指示通知注册的类型的项发生更改时，通讯簿提供程序为_lpAdviseSink_参数中指定的 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 **OnNotify**方法包括作为输入参数包含数据描述该事件[通知](notification.md)结构。 
  
通讯簿提供程序，根据**OnNotify**调用紧跟更改对注册对象或更高版本时出现。 支持多个线程的执行系统，在调用**OnNotify**可以发生任何线程上。 客户端可以请求对这些通知通过调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来创建 advise 接收器对象传递给**Advise**发生在特定线程。 
  
因为通讯簿提供程序可以释放 advise 接收器对象中传递的客户端在任何时候**Advise**成功完成呼叫，并在[IAddrBook::Unadvise](iaddrbook-unadvise.md)前调用取消通知后，应释放客户端当**Advise**返回其 advise 接收器对象。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IAddrBook::Unadvise](iaddrbook-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[通知](notification.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

