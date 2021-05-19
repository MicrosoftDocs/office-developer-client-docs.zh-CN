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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424075"
---
# <a name="iablogonunadvise"></a>IABLogon::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消之前通过调用 [IABLogon：：Advise](iablogon-advise.md) 方法设置的通知。 
  
```cpp
HRESULT Unadvise(
  ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]与活动通知注册关联的连接号。 之前对 **Advise** 的调用必须已返回  _ulConnection 的值_。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功取消。
    
## <a name="remarks"></a>备注

MAPI 调用 **Unadvise** 方法以取消容器、邮件传递用户或通讯组列表对象的通知注册。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

非企业 **实现将取决于** 是支持使用 MAPI 的帮助通知，还是支持手动通知。 如果 MAPI 提供支持，请调用 [IMAPISupport：：Unsubscribe](imapisupport-unsubscribe.md) 方法来取消注册。 如果另一个线程正在调用通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法，则它会延迟到 **OnNotify** 返回。 
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 有关如何使用 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 方法支持通知的信息，请参阅 [Supporting Event Notification](supporting-event-notification.md)。
  
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

