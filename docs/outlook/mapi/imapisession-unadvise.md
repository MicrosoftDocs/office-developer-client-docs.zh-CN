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
ms.openlocfilehash: 3b582b48773b9f6f1a6f46f9c0e4c6dcb9782b86
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592064"
---
# <a name="imapisessionunadvise"></a>IMAPISession::Unadvise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
    
## <a name="remarks"></a>注解

**IMAPISession::Unadvise**方法取消注册的通知。 呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。 
  
通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。 但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Advise](imapisession-advise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

