---
title: IAddrBookUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Unadvise
api_type:
- COM
ms.assetid: e0db9e86-9528-43de-b8ba-a5af8b7bda4b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e06f78317a1e98d47a37cb7059042b254567fe8b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573682"
---
# <a name="iaddrbookunadvise"></a>IAddrBook::Unadvise

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
取消以前建立的通讯簿条目的通知注册。
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]代表要取消注册连接数。 _UlConnection_参数应包含以前调用[IAddrBook::Advise](iaddrbook-advise.md)方法返回的值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功取消注册。
    
## <a name="remarks"></a>注解

客户端调用**Unadvise**方法停止接收有关到特定的通讯簿条目的更改的通知。 取消通知注册时，它的指针到呼叫者的建议接收器地址簿提供程序版本。 但是，发布**Unadvise**呼叫过程中或在某些更高版本的时候，如果出现另一个线程正在调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 通知时，直至**OnNotify**方法返回延迟版本。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Advise](iaddrbook-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

