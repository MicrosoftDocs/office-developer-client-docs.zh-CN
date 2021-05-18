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
ms.openlocfilehash: 7abafafd3d4bd9618d85a7dac34e4556545167bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406274"
---
# <a name="iaddrbookadvise"></a>IAddrBook::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册客户端或服务提供商以接收有关通讯簿中一个或多个条目更改的通知。
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向通讯簿容器、邮件传递用户或通讯组列表的条目标识符的指针，当  _ulEventMask_ 参数中描述的类型发生更改时将生成通知。 
    
 _ulEventMask_
  
> [in]呼叫者要注册以接收的一个或多个通知事件。 每个事件都与一个特定的通知结构相关联，其中包含有关发生的更改的信息。 下表列出了  _ulEventMask_ 的有效值及其相应的结构。 
    
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
  
> [in]指向通知接收器对象的指针，当发生请求通知的事件时将调用该对象。
    
 _lpulConnection_
  
> [out]指向表示通知注册的非零连接号的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 负责在  _lpEntryID_ 中传递的条目标识符的通讯簿提供程序无法为相应的条目注册通知。 
    
MAPI_E_NO_SUPPORT 
  
> 负责由传入  _lpEntryID_ 参数中的条目标识符标识的对象的通讯簿提供程序不支持通知。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_ 中传递的条目标识符无法由配置文件中的任一通讯簿提供程序处理。 
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **Advise** 方法，以注册通讯簿条目上的特定通知类型。 通知类型由使用  _ulEventMask_ 参数传入的事件掩码指示。 
  
MAPI 将 **此 Advise** 调用转发到负责条目的通讯簿提供程序，如  _lpEntryID_ 参数中的条目标识符所指示。 通讯簿提供程序要么处理注册本身，要么调用支持方法 [IMAPISupport：：Subscribe](imapisupport-subscribe.md)来提示 MAPI 注册呼叫者。 返回非零连接号以表示注册成功。
  
每当通知注册所指示类型的条目发生变化时，通讯簿提供程序都会为 _lpAdviseSink_ 参数中指定的通知接收器对象调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法。 **OnNotify** 方法包括 [NOTIFICATION](notification.md)结构作为输入参数，其中包含用于描述事件的数据。 
  
根据通讯簿提供程序，对 **OnNotify** 的调用可以在注册对象更改后立即发生，或稍后发生。 在支持多个执行线程的系统上，对 **OnNotify** 的调用可以在任何线程上发生。 客户端可以通过调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数来创建传递给 Advise 的建议接收对象，来请求这些通知出现在特定 **线程上**。 
  
由于通讯簿提供程序可以在 **Advise** 调用成功完成后 [、IAddrBook：：Unadvise](iaddrbook-unadvise.md) 调用取消通知之前随时释放客户端传入的建议接收对象，因此当 **Advise** 返回时，客户端应释放其通知接收器对象。 
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IAddrBook::Unadvise](iaddrbook-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[NOTIFICATION](notification.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

