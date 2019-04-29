---
title: IMAPISupportNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Notify
api_type:
- COM
ms.assetid: c16c668e-2c8b-4759-bbca-d0c5662b62e9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6160b8e75bdc9059965c2358b9fe7d296e1f66d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435934"
---
# <a name="imapisupportnotify"></a>IMAPISupport::Notify

**适用于**：Outlook 2013 | Outlook 2016 
  
将指定事件的通知发送到最初通过[IMAPISupport:: 订阅](imapisupport-subscribe.md)方法为通知注册的通知源。 
  
```cpp
HRESULT Notify(
LPNOTIFKEY lpKey,
ULONG cNotification,
LPNOTIFICATION lpNotifications,
ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>参数

_lpKey_
  
> 实时一个指针, 指向通知源对象的通知密钥。 _lpKey_参数不能为 NULL。 
    
_cNotification_
  
> 实时由_lpNotifications_参数指向的通知结构的计数。 
    
_lpNotifications_
  
> 实时指向描述挂起通知的[通知](notification.md)结构数组的指针。 
    
_lpulFlags_
  
> [in, out]控制通知过程的标志的位掩码。 在输入时, 可以设置以下标志:
    
  - MAPI_UNICODE 
    
    > 由_lpNotifications_指向的通知结构中的字符串是 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。 

    在输出时, MAPI 可以设置以下标志:
        
  - NOTIFY_CANCELED 
    
    > 回调函数取消了同步通知。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功生成通知。
    
## <a name="remarks"></a>说明

为所有服务提供程序支持对象实现了**IMAPISupport:: Notify**方法。 服务提供程序调用**通知**请求 MAPI 为已通过**IMAPISupport:: 订阅**方法注册通知的通知接收器生成通知。 
  
**通知**将_lpNotifications_参数指向的结构复制到内存中, 并调用相应的通知接收器的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。 当**OnNotify**完成通知后, 它会释放涉及的内存。 调用方不需要分配内存;MAPI 执行所有必要的内存分配。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在_lpKey_参数中传递的通知密钥应与在_lpKey_中传递给**IMAPISupport:: 订阅**方法的密钥相同。 许多提供程序将建议源的条目标识符用作密钥, 但可以使用其他数据 (如文件路径)。 MAPI 使用此密钥在确定的建议源上查找所有通知注册。 
  
确保将通知结构的**lpEntryID**成员设置为长期条目标识符。 
  
如果您在**订阅**呼叫中为任何挂起的通知设置 NOTIFY_SYNC 标志, 请在返回之前**通知**调用**IMAPIAdviseSink:: OnNotify**方法回调函数。 可以手动或通过调用[HrAllocAdviseSink](hrallocadvisesink.md)创建通知接收器。 **HrAllocAdviseSink**函数允许其调用方指定一个回调函数, 用于将调用作为通知的一部分进行**通知**。 回调函数符合[NOTIFCALLBACK](notifcallback.md)原型。 客户端实现的回调函数始终返回 S_OK;服务提供程序实现的回调函数可返回 CALLBACK_DISCONTINUE。 
  
如果回调函数返回 CALLBACK_DISCONTINUE, MAPI 将停止发送通知, 并在**NOTIFY**方法的_lpulFlags_参数中返回 NOTIFY_CANCELED。 您可以假定该进程处于非活动状态, 并停止为该进程生成通知。 如果**通知**在_lpulFlags_中返回 0, 则该进程仍处于活动状态, 应根据需要继续发送通知。
  
使用同步通知时, 请注意避免死锁情况。
  
有关通知过程的详细信息, 请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::Subscribe](imapisupport-subscribe.md)  
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)  
- [NOTIFCALLBACK](notifcallback.md) 
- [NOTIFICATION](notification.md)  
- [NOTIFKEY](notifkey.md)  
- [PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)  
- [IMAPISupport : IUnknown](imapisupportiunknown.md)

