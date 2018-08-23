---
title: IABLogonUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.Unadvise
api_type:
- COM
ms.assetid: 3e506b29-c7e3-40d6-a08b-22fa87088c2d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3fbf8b423cfd4206a0143b5639c85dbcacce2fae
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570980"
---
# <a name="iablogonunadvise"></a>IABLogon::Unadvise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
取消以前已设置为[IABLogon::Advise](iablogon-advise.md)方法的调用的通知。 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]与活动通知注册连接数。 必须具有以前调用**Advise**返回_ulConnection_的值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功取消通知注册。
    
## <a name="remarks"></a>注解

MAPI 调用**Unadvise**方法取消容器，通知注册消息用户或通讯组列表对象。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**Unadvise**的实现将取决于是否支持 MAPI 的帮助或手动通知。 如果 MAPI 提供了您的支持，调用[IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)方法取消注册。 如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，可返回了**OnNotify**之前延迟。 
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法以支持通知，请参阅[支持的事件通知](supporting-event-notification.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

