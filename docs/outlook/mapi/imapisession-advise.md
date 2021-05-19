---
title: IMAPISessionAdvise
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.Advise
api_type:
- COM
ms.assetid: a6a6b6b1-31e2-4899-a5fe-74d5d1c2ccfc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5d87d7be9cb3524445107e975a298d4afd5bf98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419833"
---
# <a name="imapisessionadvise"></a>IMAPISession::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册以接收影响会话的指定事件的通知。
  
```cpp
HRESULT Advise(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulEventMask,
  LPMAPIADVISESINK lpAdviseSink,
  ULONG_PTR lpulConnection
);
```

## <a name="parameters"></a>参数

 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向有关应生成通知的通讯簿或邮件存储对象的条目标识符的指针或 NULL，指示客户端正在注册以接收有关仅影响会话的事件的通知。 
    
 _ulEventMask_
  
> [in]指示客户端感兴趣的通知事件类型且应包含在注册中的值的掩码。 如果  _lpEntryID_ 为 NULL，MAPI 会自动为仅影响会话的关键错误事件注册客户端。 当  _lpEntryID_ 指向条目标识符时，以下值对  _ulEventMask_ 参数有效： 
    
fnevCriticalError 
  
> 注册有关严重错误（如内存不足）的通知。
    
fnevExtended 
  
> 注册有关特定于特定通讯簿或邮件存储提供程序的事件以及会话关闭的通知。
    
fnevNewMail 
  
> 注册有关新邮件到达的通知。 
    
fnevObjectCreated 
  
> 注册有关新建对象的通知。
    
fnevObjectCopied
  
> 注册有关正在复制的对象的通知。
    
fnevObjectDeleted
  
> 注册有关要删除的对象的通知。
    
fnevObjectModified
  
> 注册有关要修改的对象的通知。
    
fnevObjectMoved
  
> 注册有关要移动的对象的通知。
    
fnevSearchComplete
  
> 注册有关搜索操作完成的通知。
    
 _lpAdviseSink_
  
> [in]指向通知接收接收对象以接收后续通知的指针。 此通知接收器对象必须已分配。
    
 _lpulConnection_
  
> [out]指向非零数字的指针，该数字代表呼叫者的建议接收对象和会话之间的连接。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 注册成功。
    
MAPI_E_INVALID_ENTRYID 
  
> _lpEntryID_ 指向的条目标识符不表示有效的条目标识符。 
    
MAPI_E_NO_SUPPORT 
  
> 负责  _lpEntryID_ 指向的条目标识符的服务提供商要么不支持  _ulEventMask_ 参数中指定的事件类型，要么不支持通知。 
    
MAPI_E_UNKNOWN_ENTRYID 
  
> _lpEntryID_ 指向的条目标识符无法由配置文件中的任一服务提供商处理。 
    
## <a name="remarks"></a>备注

**IMAPISession：：Advise** 方法在调用方的 advise 接收器对象、会话和（可选）服务提供商之间建立连接。 当  _ulEventMask_ 参数中指定的一个或多个事件发生到  _lpEntryID_ 指向的对象时，此连接用于向通知接收器发送通知。 当  _lpEntryID 为_ NULL 时，目标对象为会话，并且仅针对关键错误和扩展事件发送通知。 
  
当  _lpEntryID_ 指向有效的条目标识符时，MAPI 将调用属于负责服务提供商的登录对象的 **Advise** 方法。 例如，如果  _lpEntryID_ 指向通讯组列表的条目标识符，MAPI 将调用相应的通讯簿提供程序的 [IABLogon：：Advise](iablogon-advise.md) 方法。 
  
若要发送通知，服务提供商或 MAPI 调用注册的通知接收器 [的 IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。 通知结构 **OnNotify** 的参数之一包含描述特定事件的信息。
  
## <a name="notes-to-callers"></a>给调用方的说明

在支持多个执行线程的系统上， **对 OnNotify** 的调用也随时可以在任何线程上发生。 如果你需要保证通知将仅在特定线程上的某个特定时间发生，请调用 [HrThisThreadAdviseSink](hrthisthreadadvisesink.md) 函数以生成传递给 **Advise** 方法的建议接收器对象。 
  
若要确定客户端何时注销，请通过调用 _lpEntryID_ 设置为 NULL 且 _cbEntryID_ 设置为 0 的 **Advise** 在服务提供商中注册通知。 注销时，你将收到 fnevExtended 通知。 
  
在成功调用 **Advise** 之后，在 [调用 IMAPISession：：Unadvise](imapisession-unadvise.md) 以取消注册之前，请释放通知接收器对象，除非你具有特定的长期用途。 
  
有关通知过程的概述，请参阅 [MAPI 中的事件通知](event-notification-in-mapi.md)。 
  
有关处理通知的信息，请参阅处理 [通知](handling-notifications.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|BaseDialog.cpp  <br/> |CBaseDialog：：OnNotificationsOn  <br/> |MFCMAPI 使用 **IMAPISession：：Advise** 方法针对会话注册通知。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IABLogon::Advise](iablogon-advise.md)
  
[HrThisThreadAdviseSink](hrthisthreadadvisesink.md)
  
[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)
  
[IMAPISession::Unadvise](imapisession-unadvise.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 中的事件通知](event-notification-in-mapi.md)

