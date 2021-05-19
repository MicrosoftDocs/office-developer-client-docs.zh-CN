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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98a5faca00f5877eb10110406875b46a69244d94
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335698"
---
# <a name="imapisessionunadvise"></a>IMAPISession::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消发送以前通过调用 [IMAPISession：：Advise](imapisession-advise.md) 方法设置的通知。 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]与活动通知注册关联的连接号。 _ulConnection 的值必须已_ 由上一次对 **IMAPISession：：Advise 的调用返回**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册已成功取消。
    
## <a name="remarks"></a>备注

**IMAPISession：：Unadvise** 方法取消通知注册。 **非advise** 将释放指向调用方的建议接收器的指针，它会在用于注册的 **Advise** 调用中收到通知接收器。 
  
通常 **，Unadvise** 在 **Unadvise** 调用期间调用通知接收器 [的 IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。 但是，如果另一个线程正在调用通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法， **则 Release** 调用将延迟到 **OnNotify** 方法返回。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Advise](imapisession-advise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

