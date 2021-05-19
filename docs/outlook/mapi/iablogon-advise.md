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
  
注册呼叫者以接收影响容器、消息传送用户或通讯组列表的指定事件的通知。
  
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
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节数。 
    
 _lpEntryID_
  
> [in]指向应生成通知的对象的条目标识符的指针。
    
 _ulEventMask_
  
> [in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的位掩码。 有一个与 [每种](notification.md) 事件类型关联的相应 NOTIFICATION 结构，用于保存有关事件的信息。 下表列出了  _ulEventMask_ 参数的有效值以及与每个值关联的结构。 
    
|**通知事件类型**|**相应的 **NOTIFICATION** 结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectModified** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectCopied** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectMoved** <br/> |**OBJECT_NOTIFICATION** <br/> |
   
 _lpAdviseSink_
  
> [in]指向通知接收接收对象以接收后续通知的指针。
    
 _lpulConnection_
  
> [out]指向表示通知注册的非零值的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> 在  _lpEntryID_ 参数中传递的条目标识符格式不适当。 
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持通知，可能是因为它不允许更改其对象。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通讯簿提供程序无法处理在  _lpEntryID 中传递的条目标识符_。
    
## <a name="remarks"></a>备注

通讯簿提供程序实现 **IABLogon：：Advise** 方法，以注册呼叫者，以在对象其中一个容器中发生更改时收到通知。 呼叫者可以注册有关邮件用户、通讯组列表或整个容器的通知。 
  
客户端通常调用 [IAddrBook：：Advise](iaddrbook-advise.md) 方法来注册通讯簿通知。 然后，MAPI 调用通讯簿提供程序的 **Advise** 方法，该通讯簿提供程序负责  _由 lpEntryID_ 中的条目标识符表示的对象。
  
当 _对 ulEventMask_ 中表示的类型所指示的对象发生更改时，将调用 _lpAdviseSink_ 指向的建议接收器的 **OnNotify** 方法。 在 NOTIFICATION **结构中传递给** **OnNotify** 例程的数据描述事件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 MAPI 的帮助下，你都可以支持通知，也可以不提供帮助。 MAPI 具有三种支持对象方法，可帮助服务提供商实现通知：
  
- [IMAPISupport::Subscribe](imapisupport-subscribe.md)
    
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
    
- [IMAPISupport::Notify](imapisupport-notify.md)
    
如果选择使用 MAPI 支持方法，在 **调用 Advise** 方法时调用 **Subscribe** 并释放 _lpAdviseSink_ 指针。 
  
如果选择自己支持通知，请调用 _由 lpAdviseSink_ 参数表示的建议接收器的 **AddRef** 方法以保留此指针的副本。 保留此副本， [直到调用 IABLogon：：Unadvise](iablogon-unadvise.md) 方法来取消注册。 
  
无论您如何支持通知，都将非零连接号分配给通知注册，并将其返回到  _lpulConnection_ 参数中。 在调用 **Unadvise** 方法之前不要释放此连接号。 
  
## <a name="notes-to-callers"></a>给调用方的说明

将  _lpAdviseSink_ 参数传递给 **Advise** 的建议接收器指针可以指向已创建的对象或 MAPI 通过 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数创建的对象。 如果您支持多个执行线程，并且希望确保对 **OnNotify** 方法的后续调用在相应线程上的合适时间发生，您可能需要使用 **HrThisThreadAdviseSink。** 
  
准备好在调用 **Advise** 之后和调用 **Unadvise** 之前随时释放建议接收对象。 因此，您应在 **Advise** 返回后释放通知接收器对象，除非您具有特定的长期用途。 
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用 **IMAPISupport** 方法支持通知的信息，请参阅 [Supporting Event Notification。](supporting-event-notification.md) 有关多线程和 MAPI 的信息，请参阅 [MAPI 中的线程](threading-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IABLogon::Unadvise](iablogon-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[NOTIFICATION](notification.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

