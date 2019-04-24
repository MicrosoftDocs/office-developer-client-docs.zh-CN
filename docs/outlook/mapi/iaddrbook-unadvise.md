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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2988f1fc149bbfc2d724b62b12bd12ae4f4664a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286981"
---
# <a name="iaddrbookunadvise"></a>IAddrBook::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消之前为通讯簿条目建立的通知注册。
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> 实时一个代表要取消的注册的连接号。 _ulConnection_参数应包含以前调用[IAddrBook:: Advise](iaddrbook-advise.md)方法返回的值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功取消注册。
    
## <a name="remarks"></a>注解

客户端调用**Unadvise**方法以停止接收有关特定通讯簿条目更改的通知。 当取消通知注册时, 通讯簿提供程序释放其指向呼叫者的通知接收器的指针。 但是, 如果另一个线程正在调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法, 则可以在**Unadvise**调用过程中或在稍后的某个时间点进行释放。 当通知正在进行时, 释放将延迟到**OnNotify**方法返回。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Advise](iaddrbook-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

