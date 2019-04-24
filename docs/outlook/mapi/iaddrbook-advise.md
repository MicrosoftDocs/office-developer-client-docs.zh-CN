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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334753"
---
# <a name="iaddrbookadvise"></a>IAddrBook::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册客户端或服务提供商, 以接收有关通讯簿中的一个或多个条目的更改通知。
  
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
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向通讯簿容器、邮件用户或通讯组列表的条目标识符的指针, 在_ulEventMask_参数中所述的类型或类型发生更改时, 将生成通知。 
    
 _ulEventMask_
  
> 实时呼叫者注册接收的一个或多个通知事件。 每个事件都与特定的通知结构相关联, 其中包含有关所发生更改的信息。 下表列出了_ulEventMask_及其对应结构的有效值。 
    
|**通知事件**|**对应的结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectModified** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectCopied** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectMoved** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevTableModified** <br/> |[TABLE_NOTIFICATION](table_notification.md) <br/> |
   
 _lpAdviseSink_
  
> 实时指向在请求通知的事件发生时要调用的通知接收器对象的指针。
    
 _lpulConnection_
  
> 排除指向代表通知注册的非零连接号的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 负责_lpEntryID_中传递的条目标识符的通讯簿提供程序无法为相应条目注册通知。 
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持通知, 该通讯簿提供程序负责由_lpEntryID_参数中传递的条目标识符标识的对象。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_中传递的条目标识符不能由配置文件中的任何通讯簿提供程序处理。 
    
## <a name="remarks"></a>注解

客户端和服务提供程序调用**Advise**方法以在通讯簿条目上注册特定类型或通知类型。 通知的类型由通过_ulEventMask_参数传入的事件掩码指示。 
  
MAPI 将此**通知**调用转发给通讯簿提供程序, 该提供程序负责_lpEntryID_参数中的条目标识符所表示的条目。 通讯簿提供程序可以处理注册本身, 也可以调用支持方法[IMAPISupport:: 订阅](imapisupport-subscribe.md), 以提示 MAPI 注册呼叫者。 返回一个非零连接号码以表示成功注册。
  
每当通知注册所指示的类型的项发生更改时, 通讯簿提供程序都会为_lpAdviseSink_参数中指定的建议接收器对象调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 **OnNotify**方法包含一个[通知](notification.md)结构作为输入参数, 其中包含用于描述事件的数据。 
  
根据通讯簿提供程序, 对**OnNotify**的调用可以立即发生在对已注册对象的更改之后, 或在以后发生时。 在支持多个执行线程的系统上, 对**OnNotify**的调用可以出现在任何线程上。 客户端可以通过调用[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数来创建传递给**advise**的建议接收器对象, 从而请求在特定线程上发生这些通知。 
  
由于通讯簿提供程序可以在成功完成通知呼叫之后随时释放客户端传入的通知接收器对象, 并且在**** [IAddrBook:: Unadvise](iaddrbook-unadvise.md)调用取消通知之前, 客户端应释放**建议**返回时的通知接收器对象。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IAddrBook::Unadvise](iaddrbook-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[NOTIFICATION](notification.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

