---
title: IMAPISupportSubscribe
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Subscribe
api_type:
- COM
ms.assetid: e6baaff1-446e-431a-a09b-9b529153382b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a8c288e877078ece6ab2da8c6494d96e1714ad7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419924"
---
# <a name="imapisupportsubscribe"></a>IMAPISupport::Subscribe

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册通知接收器以通过 MAPI 接收通知。
  
```cpp
HRESULT Subscribe(
LPNOTIFKEY lpKey,
ULONG ulEventMask,
ULONG ulFlags,
LPMAPIADVISESINK lpAdviseSink,
ULONG FAR * lpulConnection
);
```

## <a name="parameters"></a>参数

 _lpKey_
  
> 实时指向表示 "通知源" 对象的通知密钥的指针。 _lpKey_参数不能为 NULL。 
    
 _ulEventMask_
  
> 实时指示呼叫者感兴趣且应包含在注册中的通知事件类型的值掩码。 以下值是有效的:
    
 _fnevCriticalError_
  
> 注册有关严重错误 (如内存不足) 的通知。
    
 _fnevExtended_
  
> 注册有关特定通讯簿或邮件存储提供程序特定的事件的通知。
    
 _fnevNewMail_
  
> 注册有关新邮件到达的通知。 
    
 _fnevObjectCreated_
  
> 注册有关创建新对象的通知。
    
 _fnevObjectCopied_
  
> 注册有关要复制的对象的通知。
    
 _fnevObjectDeleted_
  
> 注册有关要删除的对象的通知。
    
 _fnevObjectModified_
  
> 注册有关要修改的对象的通知。
    
 _fnevObjectMoved_
  
> 注册有关要移动的对象的通知。
    
 _fnevSearchComplete_
  
> 注册有关搜索操作完成的通知。
    
 _ulFlags_
  
> 实时用于控制通知发生方式的标志的位掩码。 可以设置以下标志:
    
NOTIFY_SYNC 
  
> 当呼叫者调用[IMAPISupport:: Notify](imapisupport-notify.md)方法为此通知接收器生成通知时, **Notify**应在返回之前进行所有必要的调用来通知接收器。 如果未设置此标志, 则通知是异步的, 并且回调会在这些进程获得对 CPU 的控制时订阅并启动的进程进行排队。 
    
 _lpAdviseSink_
  
> 实时指向建议接收器对象的指针。 
    
 _lpulConnection_
  
> 排除指向代表注册的非零连接号码的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册已成功。
    
## <a name="remarks"></a>说明

**IMAPISupport:: 订阅**方法是为所有服务提供程序支持对象实现的。 服务提供商从他们的一种**建议**方法中调用**订阅**, 以允许 MAPI 管理通知。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要将 MAPI 支持方法用于通知, 请为建议源创建一个注册表项, 以了解应生成的通知的对象。 键的值必须是唯一的, 并且应在每次对象更改时轻松地重新生成。 
  
MAPI 使用通知密钥搜索通过[HrAllocAdviseSink](hrallocadvisesink.md)函数为相应的建议源注册的任何回调函数。 将此项传递给**IMAPISupport::** 无论何时需要为相应的建议源生成通知, 都会发出通知。 
  
NOTIFY_SYNC 标志将影响后续调用以进行**通知**的操作。 设置 NOTIFY_SYNC 时,**通知**不会返回, 直到发送完所有必需的通知。 如果不设置 NOTIFY_SYNC, 则在**** 发送所有通知之前, 以异步方式运行 (可能返回)。 
  
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[NOTIFICATION](notification.md)
  
[NOTIFKEY](notifkey.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

