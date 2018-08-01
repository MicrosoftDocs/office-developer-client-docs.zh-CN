---
title: IMAPISupportUnsubscribe
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Unsubscribe
api_type:
- COM
ms.assetid: 3f2870f7-1c08-4d0f-b9d8-7644f5e55b78
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9ee071bb303c7518a23c5e57909f8618b7aebdde
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775679"
---
# <a name="imapisupportunsubscribe"></a>IMAPISupport::Unsubscribe

  
  
**适用于**： Outlook 
  
取消以前建立与调用[IMAPISupport::Subscribe](imapisupport-subscribe.md)方法发送通知的责任。 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]代表通过**IMAPISupport::Subscribe**以前建立通知注册的非零值的连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已取消。
    
MAPI_E_NOT_FOUND 
  
> 不存在_ulConnection_参数中传递的连接数。 
    
## <a name="remarks"></a>说明

**IMAPISupport::Unsubscribe**方法将执行所有服务提供商支持对象。 服务提供商调用**Unsubscribe**取消以前设置**订阅**通知注册。 **取消订阅**通过释放传入**Subscribe**呼叫的通知接收器指针取消注册。 
  
通常，调用通知接收器**IUnknown::Release**方法**取消**呼叫过程中。 但是，如果 advise 接收器对象调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法处于另一个线程，直至**OnNotify**方法返回延迟**释放**调用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

