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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f27da216b9c474aa31503917a6d3c7a74eab9c4b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341263"
---
# <a name="imapisupportunsubscribe"></a>IMAPISupport::Unsubscribe

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消发送以前通过调用[IMAPISupport:: 订阅](imapisupport-subscribe.md)方法建立的通知的责任。 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时表示以前通过**IMAPISupport:: 订阅**建立的通知注册的非零连接号码。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已取消。
    
MAPI_E_NOT_FOUND 
  
> 在_ulConnection_参数中传递的连接号码不存在。 
    
## <a name="remarks"></a>注解

**IMAPISupport:: 退订**方法是为所有服务提供程序支持对象实现的。 服务提供商呼叫**取消订阅**以取消之前通过**订阅**设置的通知注册。 **取消订阅**通过释放在**订阅**呼叫中传递的通知接收器指针来取消注册。 
  
通常情况下, 在**取消订阅**呼叫过程中会调用通知接收器的**IUnknown:: Release**方法。 但是, 如果另一个线程在调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的建议接收器对象的过程中, 则**释放**调用将延迟到**OnNotify**方法返回为止。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

