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
  
> [in]指向表示建议源对象的通知键的指针。 _lpKey_ 参数不能为 NULL。 
    
 _ulEventMask_
  
> [in]指示调用方感兴趣的通知事件类型且应包含在注册中的值的掩码。 以下值有效：
    
 _fnevCriticalError_
  
> 注册有关严重错误（如内存不足）的通知。
    
 _fnevExtended_
  
> 注册有关特定于特定通讯簿或邮件存储提供程序的事件的通知。
    
 _fnevNewMail_
  
> 注册有关新邮件到达的通知。 
    
 _fnevObjectCreated_
  
> 注册有关新建对象的通知。
    
 _fnevObjectCopied_
  
> 注册有关正在复制的对象的通知。
    
 _fnevObjectDeleted_
  
> 注册有关要删除的对象的通知。
    
 _fnevObjectModified_
  
> 注册有关要修改的对象的通知。
    
 _fnevObjectMoved_
  
> 注册有关要移动的对象的通知。
    
 _fnevSearchComplete_
  
> 注册有关搜索操作完成的通知。
    
 _ulFlags_
  
> [in]控制通知发生方式的标志位掩码。 可以设置以下标志：
    
NOTIFY_SYNC 
  
> 当调用方调用 [IMAPISupport：：Notify](imapisupport-notify.md) 方法为此通知接收器生成通知时 **，Notify** 应在返回之前执行所有必要的调用来通知接收器。 如果未设置此标志，则通知是异步的，当这些进程获得 CPU 控制权时，回调将排队到已订阅和启动的进程。 
    
 _lpAdviseSink_
  
> [in]指向建议接收对象的指针。 
    
 _lpulConnection_
  
> [out]指向代表注册的非零连接号的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
## <a name="remarks"></a>备注

**IMAPISupport：：Subscribe** 方法针对所有服务提供商支持对象实现。 服务提供商从 **他们的 Advise** 方法之一调用 **Subscribe，** 以允许 MAPI 管理通知。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要使用 MAPI 支持通知方法，请为建议源创建一个键，以通知源应生成有关哪些通知的对象。 键的值必须是唯一的，并且应轻松地每次对象更改时重新生成。 
  
MAPI 使用通知键搜索通过 [HrAllocAdviseSink](hrallocadvisesink.md) 函数注册的任何回调函数，以查找相应的建议源。 每当需要为相应的建议源生成通知时，将此密钥传递到 **IMAPISupport：：Notify。** 
  
the NOTIFY_SYNC flag affects the operation of subsequent calls to **Notify**. 当您设置NOTIFY_SYNC时 **，Notify** 不会返回，直到它发送完所有必需的通知。 当您未设置NOTIFY_SYNC时 **，Notify** 将异步运行，可能在发送所有通知之前返回。 
  
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[NOTIFICATION](notification.md)
  
[NOTIFKEY](notifkey.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

