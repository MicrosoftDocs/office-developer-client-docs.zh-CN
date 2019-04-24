---
title: IMsgStoreUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.Unadvise
api_type:
- COM
ms.assetid: 1394039b-d509-49a5-8421-b7362d906879
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f85b662b7fe710c66a2e69dd3cd3db22e3283ddb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309721"
---
# <a name="imsgstoreunadvise"></a>IMsgStore::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消之前通过调用[IMsgStore:: Advise](imsgstore-advise.md)方法设置的通知发送。 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时与活动通知注册相关联的连接号码。 _ulConnection_的值必须已由以前对**IMsgStore:: Advise**方法的调用返回。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功取消注册。
    
## <a name="remarks"></a>注解

**IMsgStore:: Unadvise**方法取消注册通知。 **Unadvise**释放其指向呼叫者通知接收器的指针, 该接收器在用于注册的**通知**呼叫中收到。 
  
通常情况下, **Unadvise**在**Unadvise**调用过程中调用通知接收器的[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。 但是, 如果另一个线程正在调用通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则**释放**调用将延迟到**OnNotify**方法返回为止。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMsgStore::Advise](imsgstore-advise.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)

