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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6658f1c4bcfaf7557d9b53c5e70d87e124475580
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775694"
---
# <a name="imapisupportsubscribe"></a>IMAPISupport::Subscribe

  
  
**适用于**： Outlook 
  
注册以接收通知通过 MAPI 通知接收器。
  
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
  
> [in]指向代表 advise 源对象的通知键的指针。 _LpKey_参数不能为 NULL。 
    
 _ulEventMask_
  
> [in]指示呼叫者感兴趣，并应包含在注册通知事件的类型的值的掩码。 以下是有效值：
    
 _fnevCriticalError_
  
> 有关严重错误，例如内存不足通知注册。
    
 _fnevExtended_
  
> 有关特定于特定的通讯簿或消息的事件通知的 register 存储提供程序。
    
 _fnevNewMail_
  
> 有关新邮件的到达通知注册。 
    
 _fnevObjectCreated_
  
> 有关创建新对象的通知的注册。
    
 _fnevObjectCopied_
  
> 有关要复制的对象的通知的注册。
    
 _fnevObjectDeleted_
  
> 有关对象正在删除通知的注册。
    
 _fnevObjectModified_
  
> 有关修改对象的通知的注册。
    
 _fnevObjectMoved_
  
> 有关被移动对象通知注册。
    
 _fnevSearchComplete_
  
> 有关搜索操作完成通知注册。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何将出现通知。 可以设置以下标记：
    
NOTIFY_SYNC 
  
> 呼叫者呼叫时要为此通知接收器生成通知的[IMAPISupport::Notify](imapisupport-notify.md)方法， **Notify**应进行所有必需的呼叫告知接收器返回之前。 如果未设置此标志，通知是异步; 回调排队到已订阅并启动时的 CPU 控制这些过程的过程。 
    
 _lpAdviseSink_
  
> [in]指向 advise 接收器对象的指针。 
    
 _lpulConnection_
  
> [输出]一个指向代表注册非零值的连接数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知注册成功。
    
## <a name="remarks"></a>备注

**IMAPISupport::Subscribe**方法将执行所有服务提供商支持对象。 服务提供程序从其**Advise**方法之一来允许 MAPI 管理通知调用**订阅**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要使用通知 MAPI 支持方法，创建 advise 源应生成有关的通知的对象的键。 项的值必须是唯一的并应轻松地重新生成对象更改每次。 
  
MAPI 使用通知密钥来通过相应 advise 源的[HrAllocAdviseSink](hrallocadvisesink.md)函数注册任何回调函数中搜索。 无论何时需要生成相应的 advise 源通知，请将此参数传递给**IMAPISupport::Notify** 。 
  
NOTIFY_SYNC 标志会影响后续调用**Notify**的操作。 NOTIFY_SYNC 设置时，才完发送的所有必要通知会返回**通知**。 时不设置 NOTIFY_SYNC，**通知**的操作以异步方式，可能返回之前已发送的所有通知。 
  
## <a name="see-also"></a>另请参阅



[HrAllocAdviseSink](hrallocadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISupport::Notify](imapisupport-notify.md)
  
[通知](notification.md)
  
[NOTIFKEY](notifkey.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

