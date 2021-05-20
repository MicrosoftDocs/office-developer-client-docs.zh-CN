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
  
将指定事件的通知发送到最初通过 [IMAPISupport：：Subscribe](imapisupport-subscribe.md) 方法注册的通知源。 
  
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
  
> [in]指向建议源对象的通知键的指针。 _lpKey_ 参数不能为 NULL。 
    
_cNotification_
  
> [in]  _lpNotifications_ 参数指向的通知结构计数。 
    
_lpNotifications_
  
> [in]指向描述挂起通知的 [NOTIFICATION](notification.md) 结构的数组的指针。 
    
_lpulFlags_
  
> [in， out]控制通知过程的标记位掩码。 在输入时，可以设置以下标志：
    
  - MAPI_UNICODE 
    
    > _lpNotifications_ 指向的通知结构中字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。 

    在输出上，MAPI 可以设置以下标志：
        
  - NOTIFY_CANCELED 
    
    > 回调函数取消了同步通知。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功生成通知。
    
## <a name="remarks"></a>备注

所有 **服务提供商支持对象都实现了 IMAPISupport：：Notify** 方法。 服务提供商调用 **Notify** 以请求 MAPI 为之前通过 **IMAPISupport：：Subscribe** 方法注册的通知接收生成通知。 
  
**Notify** 将  _lpNotifications_ 参数指向的结构复制到内存中，并调用相应的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 当 **OnNotify** 完成通知后，它将释放涉及的内存。 调用方不需要分配内存;MAPI 执行所有必要的内存分配。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在  _lpKey_ 参数中传递的通知键应该与  _在 lpKey_ 中传递给 **IMAPISupport：：Subscribe** 方法的键相同。 许多提供程序使用建议源的条目标识符作为键，但可以使用其他数据（如文件路径）。 MAPI 使用此密钥查找标识的建议源上通知的所有注册。 
  
请确保将通知结构的 **lpEntryID** 成员设置为长期条目标识符。 
  
如果在 Subscribe 调用上为任何挂起的通知设置NOTIFY_SYNC 标志 **，Notify** 将在返回之前调用 **IMAPIAdviseSink：：OnNotify** 方法回调函数。 建议接收器可以手动创建，也可以调用 [HrAllocAdviseSink 创建](hrallocadvisesink.md)。 **HrAllocAdviseSink** 函数允许其调用方指定一个回调函数，以通知调用作为通知的一部分。 回调函数符合 [NOTIFCALLBACK](notifcallback.md) 原型。 客户端实现的回调函数始终返回S_OK;由服务提供商实现的回调函数可以返回CALLBACK_DISCONTINUE。 
  
如果回调函数返回 CALLBACK_DISCONTINUE，MAPI 将停止发送通知，NOTIFY_CANCELED **Notify** 方法  _的 lpulFlags_ 参数中返回通知。 你可以假设进程处于非活动状态，并停止为该进程生成通知。 如果 **Notify** 在  _lpulFlags_ 中返回 0，则进程仍处于活动状态，您应该继续根据情况发送通知。
  
使用同步通知时，请注意避免死锁情况。
  
有关通知过程详细信息，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::Subscribe](imapisupport-subscribe.md)  
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)  
- [NOTIFCALLBACK](notifcallback.md) 
- [NOTIFICATION](notification.md)  
- [NOTIFKEY](notifkey.md)  
- [PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)  
- [IMAPISupport : IUnknown](imapisupportiunknown.md)

