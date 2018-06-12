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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 516de39d721c532c003775bd366a52ed8144ab88
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775910"
---
# <a name="imsgstoreunadvise"></a>IMsgStore::Unadvise

  
  
**适用于**： Outlook 
  
取消发送通知之前设置与对[IMsgStore::Advise](imsgstore-advise.md)方法的调用。 
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]与活动通知注册连接数。 必须在之前调用**IMsgStore::Advise**方法返回的_ulConnection_值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功取消注册。
    
## <a name="remarks"></a>备注

**IMsgStore::Unadvise**方法取消注册的通知。 呼叫者到其指针告知接收器，它用于注册的**Advise**调用中接收**Unadvise**版本。 
  
通常， **Unadvise** **Unadvise**呼叫过程中调用通知接收器[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法。 但是，如果另一个线程的过程中调用通知接收器[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，直至**OnNotify**方法返回延迟**释放**调用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMsgStore::Advise](imsgstore-advise.md)
  
[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)

