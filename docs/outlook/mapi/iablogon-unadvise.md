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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fe87de4466413e317edea5d358c9e4769d0c5593
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348879"
---
# <a name="iablogonunadvise"></a>IABLogon::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消以前通过调用[IABLogon:: Advise](iablogon-advise.md)方法设置的通知。 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时与活动通知注册相关联的连接号码。 之前对 "**建议**" 的调用必须返回_ulConnection_的值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功取消。
    
## <a name="remarks"></a>注解

MAPI 调用**Unadvise**方法来取消对容器、邮件用户或通讯组列表对象的通知注册。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您的**Unadvise**实现将取决于您是否支持 MAPI 帮助或手动的通知。 如果 MAPI 提供支持, 请调用[IMAPISupport:: 退订](imapisupport-unsubscribe.md)方法取消注册。 如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则可以将其延迟到**OnNotify**返回为止。 
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法支持通知的信息, 请参阅[支持事件通知](supporting-event-notification.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

