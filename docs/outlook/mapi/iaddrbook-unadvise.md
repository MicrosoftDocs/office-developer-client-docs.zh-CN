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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436151"
---
# <a name="iaddrbookunadvise"></a>IAddrBook::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消以前为通讯簿条目建立的通知注册。
  
```cpp
HRESULT Unadvise(
  ULONG_PTR ulConnection
);
```

## <a name="parameters"></a>参数

 _ulConnection_
  
> [in]表示要取消的注册的连接号码。 _ulConnection_ 参数应包含之前调用 [IAddrBook：：Advise](iaddrbook-advise.md)方法时返回的值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册已成功取消。
    
## <a name="remarks"></a>备注

客户端调用 **Unadvise** 方法来停止接收有关对特定通讯簿条目的更改的通知。 当通知注册被取消时，通讯簿提供程序会释放指向呼叫者的建议接收器的指针。 但是，如果其他线程正在调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法，则版本可能会发生在 **Unadvise** 调用期间或稍后的一些时间点。 当通知正在进行时，发布将延迟到 **OnNotify 方法** 返回。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::Advise](iaddrbook-advise.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

