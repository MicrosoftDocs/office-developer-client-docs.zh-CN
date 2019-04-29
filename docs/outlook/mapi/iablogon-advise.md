---
title: IABLogonAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Advise
api_type:
- COM
ms.assetid: 375d65b1-607d-4e2a-8052-9bcbf08fc2ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4ab0e4b023e6af19f650abf421aed122dcc21879
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428226"
---
# <a name="iablogonadvise"></a>IABLogon::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册调用方, 以接收影响容器、邮件用户或通讯组列表的指定事件的通知。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> 实时由_lpEntryID_参数指向的条目标识符中的字节数。 
    
 _lpEntryID_
  
> 实时一个指针, 指向有关应生成其通知的对象的条目标识符。
    
 _ulEventMask_
  
> 实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值的位掩码。 有与每种类型的事件相关联的相应[通知](notification.md)结构, 其中包含有关该事件的信息。 下表列出了_ulEventMask_参数的有效值以及与每个值关联的结构。 
    
|**通知事件类型**|**相应的**通知**结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectModified** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectCopied** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectMoved** <br/> |**OBJECT_NOTIFICATION** <br/> |
   
 _lpAdviseSink_
  
> 实时指向接收后续通知的通知接收器对象的指针。
    
 _lpulConnection_
  
> 排除指向表示通知注册的非零值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 在_lpEntryID_参数中传递的条目标识符的格式不正确。 
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持通知, 可能是因为它不允许对其对象进行更改。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通讯簿提供程序无法处理在_lpEntryID_中传递的条目标识符。
    
## <a name="remarks"></a>说明

通讯簿提供程序实现**IABLogon:: Advise**方法, 以注册呼叫者在其某个容器中的对象发生更改时收到通知。 呼叫者可以注册有关邮件用户、通讯组列表或整个容器的通知。 
  
客户端通常调用[IAddrBook:: Advise](iaddrbook-advise.md)方法注册通讯簿通知。 然后, MAPI 调用通讯簿提供程序的**Advise**方法, 该提供程序负责_lpEntryID_中的条目标识符所代表的对象。
  
当_ulEventMask_中表示的类型的指定对象发生更改时, 将对_lpAdviseSink_所指向的通知接收器的**OnNotify**方法进行调用。 **通知**结构中传递给**OnNotify**例程的数据描述了该事件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

你可以在 MAPI 中支持带有或没有帮助的通知。 MAPI 具有三个用于帮助服务提供程序实现通知的支持对象方法:
  
- [IMAPISupport::Subscribe](imapisupport-subscribe.md)
    
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
    
- [IMAPISupport::Notify](imapisupport-notify.md)
    
如果选择使用 MAPI 支持方法, 请在调用**Advise**方法时呼叫**订阅**, 并释放_lpAdviseSink_指针。 
  
如果选择自己支持通知, 请调用由_lpAdviseSink_参数表示的通知接收器的**AddRef**方法, 以保留此指针的副本。 维护此副本, 直到调用[IABLogon:: Unadvise](iablogon-unadvise.md)方法以取消注册。 
  
无论您如何支持通知, 请为通知注册分配非零连接号码, 并将其返回到_lpulConnection_参数中。 在调用**Unadvise**方法之前, 请勿释放此连接号码。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您在_lpAdviseSink_参数中传递给**建议**的建议接收器指针可指向您创建的对象, 或者 MAPI 已通过[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数创建。 如果您支持多个执行线程, 并且想确保对您的**OnNotify**方法的后续调用在适当的线程上的适当时间发生, 则您可能需要使用**HrThisThreadAdviseSink** 。 
  
在调用 " **Unadvise**" 之前, 请先为您的建议接收器对象做好**** 准备, 以随时释放通知对象。 因此, 您应在**建议**返回后释放您的建议接收器对象, 除非您对其有特定的长期使用。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用**IMAPISupport**方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。 有关多线程和 MAPI 的详细信息, 请参阅[MAPI 中的线程处理](threading-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IABLogon::Unadvise](iablogon-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[NOTIFICATION](notification.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

