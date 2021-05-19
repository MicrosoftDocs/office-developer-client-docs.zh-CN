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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421212"
---
# <a name="imapisupportunsubscribe"></a>IMAPISupport::Unsubscribe

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消发送之前通过调用 [IMAPISupport：：Subscribe](imapisupport-subscribe.md) 方法建立的通知的责任。 
  
```cpp
HRESULT Unsubscribe(
ULONG ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]非零连接号，表示之前通过 **IMAPISupport：：Subscribe 建立的通知注册**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已取消。
    
MAPI_E_NOT_FOUND 
  
> ulConnection 参数中  _传递的连接_ 号不存在。 
    
## <a name="remarks"></a>备注

**IMAPISupport：：Unsubscribe** 方法为所有服务提供商支持对象实现。 服务提供商调用 **Unsubscribe** 以取消之前由 Subscribe 设置 **的通知注册**。 **取消** 订阅通过释放 Subscribe 调用中传递的建议接收器指针 **来取消注册** 。 
  
通常，在取消订阅调用期间调用通知接收器 **的 IUnknown：：Release** 方法。  但是，如果另一个线程正在调用通知接收器对象的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法， **则 Release** 调用将延迟到 **OnNotify** 方法返回。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Subscribe](imapisupport-subscribe.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

