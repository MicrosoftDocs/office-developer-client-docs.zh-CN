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
ms.openlocfilehash: ea72a6fd2a22fe87ad63bb9c8fa6c1416d876b66
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564246"
---
# <a name="iablogonadvise"></a>IABLogon::Advise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
注册呼叫者接收影响的容器，消息用户或通讯组列表的指定事件的通知。
  
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
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向有关哪些应生成通知的对象的项标识符的指针。
    
 _ulEventMask_
  
> [in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的位掩码。 没有相应的[通知](notification.md)结构，每种类型的包含有关事件的信息的事件相关联。 下表列出的有效值_ulEventMask_参数和与每个值的结构。 
    
|**通知事件类型**|**相应的**通知**结构**|
|:-----|:-----|
|**fnevCriticalError** <br/> |[ERROR_NOTIFICATION](error_notification.md) <br/> |
|**fnevObjectCreated** <br/> |[OBJECT_NOTIFICATION](object_notification.md) <br/> |
|**fnevObjectDeleted** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectModified** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectCopied** <br/> |**OBJECT_NOTIFICATION** <br/> |
|**fnevObjectMoved** <br/> |**OBJECT_NOTIFICATION** <br/> |
   
 _lpAdviseSink_
  
> [in]指向要接收随后进行通知 advise 接收器对象的指针。
    
 _lpulConnection_
  
> [输出]指向为非零值，该值代表通知注册的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> _LpEntryID_参数中传递的项标识符不在适当的格式。 
    
MAPI_E_NO_SUPPORT 
  
> 通讯簿提供程序不支持通知，原因可能是因为它不允许将对其对象进行更改。
    
MAPI_E_UNKNOWN_ENTRYID 
  
> 通讯簿提供程序无法处理_lpEntryID_中传递的项标识符。
    
## <a name="remarks"></a>注解

通讯簿提供程序实现**IABLogon::Advise**方法注册呼叫者到其容器之一对象发生更改时收到通知。 呼叫者可以注册通知消息的用户、 通讯组列表，或整个容器。 
  
客户端通常调用[IAddrBook::Advise](iaddrbook-advise.md)方法注册地址簿通知。 MAPI 然后调用**Advise**方法的地址簿提供程序负责_lpEntryID_中的项标识符所表示的对象。
  
对指定对象中_ulEventMask_表示的类型发生更改时, 调用了通知接收器所指的_lpAdviseSink_ **OnNotify**方法。 数据传递给**OnNotify**例程**通知**结构中介绍的事件。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以支持使用或不从 MAPI 帮助的通知。 MAPI 具有三个支持对象方法，以帮助服务提供商实现通知：
  
- [IMAPISupport::Subscribe](imapisupport-subscribe.md)
    
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)
    
- [IMAPISupport::Notify](imapisupport-notify.md)
    
如果您选择使用 MAPI 支持方法，调用**Advise**方法时调用**Subscribe**和释放_lpAdviseSink_指针。 
  
如果您选择自己支持通知，呼叫通知接收器由_lpAdviseSink_参数保留一份此指针的**AddRef**方法。 维护此副本，直到您[IABLogon::Unadvise](iablogon-unadvise.md)方法调用取消注册。 
  
无论如何支持通知，分配给通知注册的非零值的连接数并返回_lpulConnection_参数中。 被调用**Unadvise**方法之前不释放此连接数。 
  
## <a name="notes-to-callers"></a>给调用方的说明

_LpAdviseSink_参数中传递到**Advise** advise 接收器指针可以指向已创建或通过[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)函数创建 MAPI 的对象。 您可能需要使用**HrThisThreadAdviseSink** ，如果您支持多个线程的执行，并且想要确保您**OnNotify**方法的后续呼叫发生在相应的线程上适当的时间。 
  
为您 advise 接收器对象，必须释放到**Advise**和到**Unadvise**呼叫之前呼叫后随时准备。 因此，您应释放 advise 接收器对象后**Advise**返回，除非您有特定的长期使用它。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用**IMAPISupport**方法以支持通知的信息，请参阅[支持的事件通知](supporting-event-notification.md)。 有关详细信息多线程和 MAPI，请参阅[MAPI 中的线程](threading-in-mapi.md)。
  
## <a name="see-also"></a>另请参阅



[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IABLogon::Unadvise](iablogon-unadvise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[通知](notification.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

