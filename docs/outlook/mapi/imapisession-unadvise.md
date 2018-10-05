---
title: IMAPISessionUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Unadvise
api_type:
- COM
ms.assetid: 5e608cb0-808d-4418-8521-71dcbce8cdff
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 98a5faca00f5877eb10110406875b46a69244d94
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397889"
---
# <a name="imapisessionunadvise"></a>IMAPISession::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消发送通知之前设置与对[IMAPISession::Advise](imapisession-advise.md)方法的调用。 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]与活动通知注册的连接号码。 必须通过以前调用**IMAPISession::Advise**返回_ulConnection_的值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功取消注册。
    
## <a name="remarks"></a>说明

**IMAPISession::Unadvise**方法取消注册的通知。 呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。 
  
通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。 但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Advise](imapisession-advise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

