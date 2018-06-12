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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db23d1801bf32fd947a77dfd887c56f75ded5681
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775634"
---
# <a name="imapisupportnotify"></a>IMAPISupport::Notify

**适用于**： Outlook 
  
将指定的事件的通知发送到最初通过[IMAPISupport::Subscribe](imapisupport-subscribe.md)方法通知注册的 advise 源。 
  
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
  
> [in]指向 advise 源对象的通知键的指针。 _LpKey_参数不能为 NULL。 
    
_cNotification_
  
> [in]通知结构_lpNotifications_参数指向的计数。 
    
_lpNotifications_
  
> [in]一个指向介绍挂起的通知的[通知](notification.md)结构的数组。 
    
_lpulFlags_
  
> [传入、 传出]位掩码的标志，用于控制通知过程。 在输入时，可以设置以下标记：
    
  - MAPI_UNICODE 
    
    > 由_lpNotifications_指向的通知结构中的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。 

    输出，MAPI 可以设置以下标记：
        
  - NOTIFY_CANCELED 
    
    > 回调函数取消同步的通知。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功生成通知。
    
## <a name="remarks"></a>备注

**IMAPISupport::Notify**方法将执行所有服务提供商支持对象。 服务提供商调用**Notify**请求 MAPI 生成**IMAPISupport::Subscribe**方法通过以前通知注册通知接收器的通知。 
  
**Notify**副本结构到内存_lpNotifications_参数指向和调用适当通知接收器的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法。 当**OnNotify**与通知完成后时，将释放所涉及的内存。 呼叫者不需要分配内存;MAPI 执行所有必要的内存分配。 
  
## <a name="notes-to-callers"></a>给调用方的说明

_LpKey_参数中传递的通知密钥应为到项中_lpKey_传递给**IMAPISupport::Subscribe**方法相同。 多个提供程序将 advise 源的项标识符用作键，但可使用其他数据，例如文件的路径。 MAPI 使用此项查找所有注册的标识的 advise 源上的通知。 
  
确保将通知结构的**lpEntryID**成员设置为长期的项标识符。 
  
如果您设置**Subscribe**的 NOTIFY_SYNC 标志调用的任何挂起的通知，**通知**调用**IMAPIAdviseSink::OnNotify**方法的回调函数返回之前。 手动方式或通过调用[HrAllocAdviseSink](hrallocadvisesink.md)，可以创建通知接收器。 使用**HrAllocAdviseSink**功能，其调用方指定一个回调函数的**Notify**呼叫通知的一部分。 符合[NOTIFCALLBACK](notifcallback.md)原型的回调函数。 始终由客户端实现的回调函数将返回 S_OK;服务提供程序实现的回调函数可以返回 CALLBACK_DISCONTINUE。 
  
如果回调函数返回 CALLBACK_DISCONTINUE，MAPI 停止发送通知，并返回 NOTIFY_CANCELED 中**Notify**方法的_lpulFlags_参数。 您可以假定过程已停用，停止生成通知的过程。 如果**Notify**中_lpulFlags_返回 0，则过程仍处于活动状态并根据需要发送通知，您应继续。
  
当您使用同步的通知时，请注意避免出现死锁的情况。
  
有关通知过程的详细信息，请参阅[MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::Subscribe](imapisupport-subscribe.md)  
- [IMAPISupport::Unsubscribe](imapisupport-unsubscribe.md)  
- [NOTIFCALLBACK](notifcallback.md) 
- [通知](notification.md)  
- [NOTIFKEY](notifkey.md)  
- [PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)  
- [IMAPISupport: IUnknown](imapisupportiunknown.md)

